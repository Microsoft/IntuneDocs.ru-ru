---
title: "Руководство для разработчиков по пакету SDK для приложений Microsoft Intune для Android | Microsoft Intune"
description: 
keywords: "Пакет SDK"
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: edbc701effb3817c2f9a160f05e7b5bc8ad0070e
ms.openlocfilehash: ee3a668a5415d14eb82e64e6bb16d9621bb13b57


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Руководство по пакету SDK для приложений Intune для разработчиков под Android

> [!NOTE]
> При желании прочтите статью [Обзор пакета SDK для приложений Intune](intune-app-sdk.md), в которой рассмотрены актуальные функции пакета SDK и описана подготовка к интеграции на каждой поддерживаемой платформе. 

Пакет SDK для приложений Microsoft Intune для Android позволяет встроить в ваше приложение Android функции управления мобильными приложениями (MAM). Приложение с поддержкой MAM интегрировано с пакетом SDK для приложений Intune и позволяет ИТ-администраторам развертывать политики для мобильного приложения во время активного управления им с помощью Intune.

# <a name="whats-in-the-sdk"></a>Состав пакета SDK 

Пакет SDK для приложений Intune для Android представляет собой стандартную библиотеку Android без внешних зависимостей. Пакет SDK состоит из следующих компонентов:  

* **Microsoft.Intune.MAM.SDK.jar**: интерфейсы, необходимые для включения MAM, а также для взаимодействия с приложением корпоративного портала Microsoft Intune. Приложения должны указывать его как ссылку на библиотеку Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 4.  Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 7. Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл.

* **Каталог ресурсов**: ресурсы (например строки), на которых основан пакет SDK. 

* **Microsoft.Intune.MAM.SDK.aar**: компоненты пакета SDK, за исключением JAR-файлов Support.V4 и Support.V7. Этот файл можно использовать вместо отдельных компонентов, если система сборки поддерживает AAR-файлы.

* **AndroidManifest.xml**: дополнительные точки входа и требования к библиотекам. 

* **THIRDPARTYNOTICES.TXT**: примечание об атрибуции, где указан сторонний код и (или) код OSS, который будет скомпилирован в ваше приложение. 

# <a name="requirements"></a>Requirements (Требования) 

Пакет SDK для приложений Intune представляет собой скомпилированный проект Android. Поэтому он сильно зависит от версии Android, используемой приложением для минимальных или целевых версий API. Пакет SDK поддерживает Android API с 14 (Android 4.0+) до 24. 

Для включения политики MAM пакету SDK для приложений Intune для Android требуется, чтобы на устройстве присутствовало приложение [корпоративного портала](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). Для MAM без регистрации устройства пользователю **не** нужно регистрировать устройство на корпоративном портале.


# <a name="how-the-intune-app-sdk-works"></a>Принцип работы пакета SDK для приложений Intune 

##<a name="entry-points"></a>Точки входа

Для включения политик управления приложениями пакету SDK для приложений Intune требуется внести изменения в исходный код приложения. Это осуществляется путем замены базовых классов Android на эквивалентные базовые классы Intune с префиксом **MAM**. Классы пакета SDK располагаются между базовым классом Android и производной версией этого класса в самом приложении.  Используя действие в качестве примера, вы получаете иерархию наследования, которая выглядит следующим образом: Activity > MAMActivity > AppSpecificActivity.

Например, если **AppSpecificActivity** взаимодействует со своим родительским классом (например, вызывает `super.onCreate()`), **MAMActivity** является суперклассом. 

Типичные приложения Android имеют одиночный режим и получают доступ ко всей системе через свой объект [Context](https://developer.android.com/reference/android/content/Context.html).  С другой стороны, приложения с внедренным пакетом SDK для приложений Intune имеют двойной режим. Такие приложения по-прежнему получают доступ к системе через объект Context, однако в зависимости от используемого базового действия объект Context будет либо предоставляться системой Android, либо интеллектуально мультиплексироваться между ограниченным представлением системы и объектом Context, предоставленным системой Android.

При использовании [точки входа](https://developer.android.com/guide/components/fundamentals.html) Android, которая была переопределена ее эквивалентом MAM, необходимо использовать MAM-версию жизненного цикла точки входа (за исключением класса **MAMApplication**).

Например, при наследовании от **MAMActivity** вместо переопределения `onCreate` и вызова `super.onCreate` действию необходимо переопределить `onMAMCreate` и вызвать `super.onMAMCreate`. Это позволяет Intune (кроме прочего) ограничивать запуск действия в определенных случаях. 


##<a name="sdk-permissions"></a>Разрешения пакета SDK

Пакету SDK для приложений Intune требуются три [разрешения системы Android](https://developer.android.com/guide/topics/security/permissions.html) в отношении приложений, в которые он интегрируется:

* `android.permission.GET_ACCOUNTS` [запрашивается во время выполнения при необходимости]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

Эти разрешения требуются библиотеке проверки подлинности Active Directory Azure ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) для проверки подлинности через посредника. Если эти разрешения приложению не предоставлены или отменены пользователем, проверка подлинности, для которой требуется посредник (приложение корпоративного портала), будет отключена.


##<a name="company-portal"></a>Company Portal (Портал компании)

Для чего нужно приложение корпоративного портала? Когда корпоративный портал устанавливается на устройство и получает политику ограничения использования приложений для пользователя из службы Intune, точки входа SDK инициализируются асинхронно. Инициализация необходима только при первоначальном создании процесса системой Android. Во время инициализации устанавливается подключение к приложению корпоративного портала, а затем из приложения загружается политика ограничений.  

> [!NOTE]
> Если приложение корпоративного портала на устройстве не установлено, поведение приложения с поддержкой MAM не изменится, и оно будет работать точно так же, как и обычное приложение.


# <a name="how-to-integrate-with-the-intune-app-sdk"></a>Интеграция с пакетом SDK для приложений Intune
 
Как уже говорилось, для включения политик управления приложениями пакету SDK требуется внести изменения в исходный код приложения. Ниже приведены шаги, необходимые для включения MAM в приложении: 

## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Замена классов, методов и действий на их эквивалент MAM (обязательно) 

Базовые классы Android необходимо заменить соответствующими эквивалентами MAM. Для этого найдите все экземпляры классов, перечисленных в следующей таблице, и замените их эквивалентом пакета SDK для приложений Intune. 

| Базовый класс Android | Аналог в пакете SDK для приложений Intune |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | **MAMPendingIntent** * |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | **MAMBinder** (требуется только в тех случаях, если модуль привязки на основе интерфейса AIDL не сформирован) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppилиt.v4.jar**:

| Класс Android | Аналог в пакете SDK для приложений Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
    
**Microsoft.Intune.MAM.SDK.Suppилиt.v7.jar**:

|Класс Android | Аналог в пакете SDK для приложений Intune |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Помните, что при использовании [точки входа](https://developer.android.com/guide/components/fundamentals.html) Android, которая была переопределена ее эквивалентом MAM, необходимо использовать MAM-версию жизненного цикла точки входа (за исключением класса **MAMApplication**).
>
>Например, при наследовании от **MAMActivity** вместо переопределения `onCreate` и вызова `super.onCreate` действию необходимо переопределить `onMAMCreate` и вызвать `super.onMAMCreate`. Это позволяет Intune (кроме прочего) ограничивать запуск действия в определенных случаях. 

### <a name="pendingintents-and-renamed-methods"></a>PendingIntents и переименованные методы 

После наследования от одной из точек входа MAM можно использовать объект Context обычным образом для запуска действий, использования **PackageManager** и т. п.  

**PendingIntents** являются исключением из этого правила. При вызове таких классов необходимо изменить имя класса. Например, вместо `PendingIntent.get*` необходимо применять метод `MAMPendingIntents.get*`. Полученный в результате **PendingIntents** можно использовать обычным образом.

Иногда метод, доступный в классе Android, может быть помечен как окончательный в замещающем классе MAM. В этом случае замещающий класс MAM предоставляет метод с таким же именем (обычно добавляется суффикс "MAM"), который должен быть переопределен вместо исходного. Например, вместо переопределения `ContentProvider.query`нужно переопределить `MAMContentProvider.queryMAM`. Компилятор Java должен налагать окончательные ограничения во избежание случайного переопределения исходного метода вместо его эквивалента MAM. 

##<a name="enable-features-that-require-app-participation"></a>Включение функций, требующих содействия со стороны приложения 

Существуют некоторые политики, которые пакет SDK не может реализовать самостоятельно. Приложение может управлять своим поведением для выполнения этих функций, используя несколько интерфейсов API, которые находятся в указанном ниже интерфейсе **AppPolicy**.  

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 * 
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 * 
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 * 
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

## <a name="enable-it-control-over-app-saving-behavior"></a>Предоставление ИТ-администратору возможности управления поведением сохранения приложений

Во многих приложениях реализованы функции, позволяющие конечным пользователям сохранять файлы локально или в облачном хранилище. Пакет SDK для приложений Intune позволяет ИТ-администраторам защититься от утечки данных за счет применения ограничений политик, уместных для их организации.  Одной из политик, которой может управлять администратор, является возможность конечного пользователя сохранять данные в личном хранилище. Сюда входит сохранение в локальной папке, на SD-карте или в сторонних службах резервного копирования. 

**Для включения этой функции требуется содействие со стороны приложения.** Если приложение позволяет сохранять данные в личное или облачное расположение непосредственно из приложения, необходимо реализовать эту функцию, чтобы предоставить ИТ-администратору возможность разрешать сохранение в расположение. Указанные ниже API позволяют приложению узнать, разрешено ли в текущей политике администрирования Intune сохранение в личном хранилище. После этого приложение может применить политику, так как ему известно о том, что хранилище личных данных доступно конечному пользователю через это приложение.  

Чтобы определить, применяется ли политика, приложение может сделать следующий вызов: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Примечание**. `MAMComponents.get(AppPolicy.class)` всегда будет возвращать политику приложений, отличную от NULL, даже если устройство или приложение не являются управляемыми. 

## <a name="allow-app-to-detect-if-pin-policy-is-required"></a>Разрешение определения потребности в политике ПИН-кода для приложения
 
Для реализации некоторых ограничений Intune можно отключить некоторые функции приложения, чтобы избежать дублирования функций пакета SDK для приложений Intune. Например, если приложение имеет собственный пользовательский интерфейс для использования ПИН-кодов, возможно, его потребуется отключить, если пакет SDK настроен на запрос ПИН-кода у конечного пользователя. 

Чтобы определить, настроена ли политика ПИН-кода Intune на запрос ПИН-кода при запуске, приложение может сделать следующий вызов: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## <a name="registering-for-notifications-from-the-sdk"></a>Регистрация для получения уведомлений из пакета SDK  

Пакет SDK для приложений Intune позволяет приложению управлять поведением определенных политик, таких как политики выборочной очистки, развернутых ИТ-администратором. Когда ИТ-администратор развертывает такую политику, служба Intune отправляет уведомление пакету SDK.

Чтобы приложение могло получать уведомления из пакета SDK, его необходимо зарегистрировать, создав класс **MAMNotificationReceiver** и зарегистрировав его с помощью **MAMNotificationReceiverRegistry**. Для этого укажите получателя, а также тип необходимых уведомлений в `App.onCreate`, как показано в следующем примере:

``` 
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

**MAMNotificationReceiver** просто получает уведомления из службы Intune. Некоторые уведомления обрабатываются непосредственно пакетом SDK, другие требуют участия со стороны приложения. 

Приложение **должно** возвращать для уведомления значение true или false. 

Оно должно всегда возвращать значение true, за исключением случаев, когда какое-либо действие, которое приложение пыталось выполнить в результате уведомления, завершилось со сбоем. 

* Этот сбой может быть зарегистрирован в службе Intune. Подобная ситуация может возникнуть, например, в случае, если приложение не смогло очистить данные пользователя после того, как ИТ-администратор запустил очистку. 

Можно безопасно осуществить блокировку в `MAMNotificationReceiver.onReceive`, так как его обратный вызов не выполняется в потоке пользовательского интерфейса. 

Ниже интерфейс **MAMNotificationReceiver** приведен в том виде, в каком он определен в пакете SDK: 

```
/**
 * The SDK is signaling that a WG event has occurred. 
 * 
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     * 
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in 
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

##<a name="types-of-notifications"></a>Типы уведомлений
Следующие уведомления отправляются в приложение, и некоторые из них могут потребовать содействия со стороны приложения: 

* **`WIPE_USER_DATA`**: это уведомление отправляется в классе **MAMUserNotification**. При получении этого уведомления приложение должно удалить все данные, связанные с "корпоративным" удостоверением, переданным с классом **MAMUserNotification**. В настоящее время это уведомление отправляется во время отмены регистрации службы Intune. Первичное имя пользователя обычно указывается во время регистрации. В случае регистрации для этого уведомления приложению необходимо убедиться, что все данные пользователя удалены. Если регистрация для него не выполняется, применяется поведение выборочной очистки по умолчанию.

* **`WIPE_USER_AUXILIARY_DATA`**: приложения могут регистрироваться для этого уведомления, если им необходимо, чтобы пакет SDK для приложений Intune выполнял выборочную очистку по умолчанию, но при этом требуется удалить некоторые дополнительные данные.  

* **`REFRESH_POLICY`**: это уведомление отправляется в классе **MAMUserNotification**. При получении этого уведомления все кэшированные политики Intune должны быть признаны недействительными и обновлены. Обычно это осуществляется пакетом SDK, однако это может сделать и приложение, если политика имеет сохраняемый характер. 



## <a name="protecting-backup-data"></a>Защита данных резервной копии 

Начиная с Android Marshmallow (API 23), система Android предоставляет два способа резервного копирования данных приложением. Каждый вариант доступен в приложении и требует разных действий для правильного обеспечения защиты данных Intune. Действия, необходимые для защиты данных, указаны в приведенной ниже таблице.  Дополнительные сведения о способах резервного копирования см. в [справочнике по API Android](http://developer.android.com/guide/topics/data/backup.html). 

### <a name="auto-backup-for-apps"></a>Автоматическое резервное копирование для приложений

Начиная с устройств Android Marshmallow, система Android начала предлагать [автоматическое полное резервное копирование](https://developer.android.com/guide/topics/data/autobackup.html) приложений независимо от целевого API. Если в файле AndroidManifest.xml задать для атрибута `android:allowBackup` значение **false**, Android не будет добавлять приложение в очереди на резервное копирование, а корпоративные данные останутся в приложении. В этом случае никаких дополнительных действий не требуется.

Однако по умолчанию атрибут `android:allowBackup` имеет значение true, даже если `android:allowBackup` не указан в файле манифеста. Это означает, что для всех приложений автоматически создаются резервные копии в учетной записи пользователя на диске Google, т. е. используется поведение по умолчанию, связанное с **риском утечки данных**. В связи с этим для защиты данных в пакет SDK необходимо внести описанные ниже изменения.  Если вы хотите, чтобы ваше приложение работало на устройствах Android Marshmallow, выполните представленные ниже рекомендации по защите клиентских данных.  

*  Если ваш агент резервного копирования не предусматривает резервное копирование вашего приложения с использованием **MAMBackupAgent** или **MAMBackupAgentHelper**, продумайте, каким образом служба автоматической архивации будет загружать данные вашего приложения. Intune позволяет использовать все [функции автоматической архивации](https://developer.android.com/guide/topics/data/autobackup.html), доступные в системе Android, включая возможность настройки правил в формате XML, однако для защиты данных необходимо выполнить следующие действия:

    1. Разрешите полное автоматическое резервное копирование, соответствующее политике Intune, с помощью MAMBackupAgent по умолчанию. Вставьте `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` в манифест своего приложения. 
    2. Выберите тип полного резервного копирования для своего приложения (без фильтра, с фильтром или нет), задав для атрибута `android:fullBackupContent` значение true или false либо указав XML-ресурс в своем приложении. Скопируйте все, что необходимо вставить в атрибут `android:fullBackupContent`, в тег метаданных с именем `com.microsoft.intune.mam.FullBackupContent`.

    **Примеры**. Если вы хотите, чтобы для приложения создавались полные резервные копии в соответствии с правилами, заданными в XML-файле, укажите имя этого файла в манифесте, используя тег метаданных `com.microsoft.intune.mam.FullBackupContent` следующим образом: 
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



### <a name="keyvalue-backup"></a>Резервные копии "ключ-значение"

Эта возможность доступна для всех API и использует `BackupAgent` и `BackupAgentHelper`. 

#### <a name="using-backupagenthelper"></a>Использование BackupAgentHelper

`BackupAgentHelper` гораздо проще, чем `BackupAgent` , как с точки зрения собственных функций Android, так и с точки зрения интеграции MAM. `BackupAgentHelper` позволяет разработчику регистрировать целые файлы и общие настройки в `FileBackupHelper` или `SharedPreferencesBackupHelper`соответственно, которые затем добавляются в `BackupAgentHelper` при создании. 

#### <a name="using-backupagent"></a>Использование BackupAgent

`BackupAgent` позволяет более явно задать, какие именно данные следует копировать. Однако этот вариант не позволяет воспользоваться преимуществами платформы резервного копирования Android.  Поскольку вы отвечаете за реализацию, существуют дополнительные шаги, необходимые для обеспечения защиты данных из MAM. Поскольку большая часть работы возложена на вас как разработчика, интеграция MAM играет более важную роль. 

##### <a name="app-does-not-have-a-backup-agent"></a>У приложения нет агента резервного копирования
  
Это варианты, доступные разработчику при `android:allowBackup =true`:

###### <a name="full-back-up-according-to-a-configuration-file"></a>Полное резервное копирование в соответствии с файлом конфигурации: 

Укажите ресурс в теге метаданных `com.microsoft.intune.mam.FullBackupContent` в манифесте. Например:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Добавьте следующий атрибут в тег `<application>` : `android:fullBackupContent="@xml/my_scheme"`, где `my_scheme` является XML-ресурсом в приложении. 

###### <a name="full-back-dup-without-exclusions"></a>Полное резервное копирование без исключений 

Укажите тег в манифесте, например `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Добавьте атрибут `android:fullBackupContent="true"` в тег `<application>`.

##### <a name="app-has-a-backup-agent"></a>У приложения есть агент резервного копирования

Следуйте рекомендациям из разделов по `BackupAgent` и `BackupAgentHelper` выше. 

Рассмотрите возможность использования нашего `MAMDefaultFullBackupAgent`, который обеспечивает простое и удобное резервное копирование в Android M. 

#### <a name="before-your-backup"></a>Подготовка к резервному копированию

Перед началом резервного копирования необходимо проверить, что буферы файлов или данных, которые вы планируете для резервного копирования, действительно могут копироваться. Чтобы определить это, мы предоставляем функцию `isBackupAllowed` в `MAMFileProtectionManager` и `MAMDataProtectionManager` . Если буфер данных или файлов не разрешен для резервного копирования, вам не следует использовать его в рамках резервного копирования.

Если в определенный момент во время архивации вам потребуется выполнить архивацию удостоверений для файлов, проверенных на шаге 1, необходимо вызвать `backupMAMFileIdentity(BackupDataOutput data, File … files)` с файлами, из которых вы планируете извлекать данные. При этом автоматически создаются новые сущности резервного копирования, которые записываются в `BackupDataOutput` . Эти сущности будут автоматически использоваться при восстановлении. 

### <a name="configure-azure-directory-authentication-library-adal"></a>Настройка параметров библиотеки проверки подлинности Azure Directory (ADAL)  

Пакет SDK использует из библиотеки ADAL сценарии проверки подлинности и условного запуска сценариев, что требует включения в приложения определенной конфигурации Azure Active Directory. Значения конфигурации передаются в пакет SDK через метаданные `AndroidManifest` . Чтобы настроить приложение и реализовать надлежащую проверку подлинности, добавьте следующий код в узел приложения в `AndroidManifest`. Некоторые из этих конфигураций нужны только тогда, когда приложение использует библиотеку ADAL для общей проверки подлинности; в этом случае вам потребуются эти конкретные значения, используемые вашим приложением для регистрации в AAD. Это позволяет предотвратить ситуацию, когда пользователь получает два запроса проверки подлинности, так как AAD распознает два отдельных значения регистрации: одно из приложения и одно из пакета SDK. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

Идентификаторы GUID не должны иметь начальные или конечные фигурные скобки.

#### <a name="common-adal-configurations"></a>Распространенные конфигурации ADAL 

Ниже приведена распространенная конфигурация для описанных выше значений. 

##### <a name="app-does-not-integrate-adal"></a>Приложение не интегрируется с ADAL

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи AAD.

* SkipBroker необходимо присвоить значение true.

##### <a name="app-integrates-adal"></a>Приложение интегрируется с ADAL

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи AAD.

* Client ID необходимо присвоить идентификатор клиента.

* `NonBrokerRedirectURI` необходимо присвоить допустимый URI перенаправления для приложения.
    * Or `urn:ietf:wg:oauth:2.0:oob` как допустимый URI перенаправления AAD.

* SkipBroker необходимо присвоить значение false (либо значение должно отсутствовать).

* AAD необходимо настроить на прием URI перенаправления брокера.

##### <a name="app-integrates-adal-but-does-not-support-the-aad-authenticator-app"></a>Приложение интегрируется с ADAL, но не поддерживает приложение проверки подлинности AAD Authenticator.

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи AAD.

* Client ID необходимо присвоить идентификатор клиента.

* `NonBrokerRedirectURI` необходимо присвоить допустимый URI перенаправления для приложения.

    * Or `urn:ietf:wg:oauth:2.0:oob` как допустимый URI перенаправления AAD.

### <a name="how-to-enable-logging-in-the-sdk"></a>Включение ведения журнала в пакете SDK 

Ведение журнала осуществляется посредством платформы `java.util.logging` . Чтобы получать журналы, настройте глобальное ведение журналов, как описано в [техническом руководстве по Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). В зависимости от конкретного приложения оптимальным местом для инициации ведения журналов обычно является `App.onCreate` . Обратите внимание на то, что сообщения журнала идентифицируются по имени класса, что может создавать некоторую путаницу.

##<a name="multiidentity"></a>Множественная идентификация
###<a name="overview"></a>Обзор
По умолчанию пакет SDK для приложений Intune применяет политику для всего приложения. Множественное удостоверение — это функция MAM, которую можно включить, чтобы разрешить применение политики на уровне удостоверения.  Для этого требуется намного больше содействия со стороны приложения, чем для других функций MAM. Приложение должно информировать пакет SDK приложений о намерении изменить активное удостоверения, а пакет SDK, в свою очередь, будет уведомлять приложение о том, что удостоверение необходимо заменить. Сейчас поддерживается только одно управляемое удостоверение. После регистрации приложения или устройства пользователем пакет SDK использует это удостоверение, считая его основным управляемым удостоверением. Другие пользователи в приложении будут рассматриваться как неуправляемые и не будут иметь ограничения для параметров политик. 

Обратите внимание, что удостоверение определяется просто в виде строки. Удостоверения задаются без учета регистра, и запросы удостоверения, направляемые к пакету SDK, могут возвращать удостоверения с регистром, отличным от изначального.

###<a name="enabling-multiidentity"></a>Включение множественного удостоверения
По умолчанию все приложения считаются приложениями с одним удостоверением. Приложение объявляет о своей поддержке множественных удостоверений, добавляя в манифест Android следующие метаданные:

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###<a name="setting-the-identity"></a>Задание удостоверения

Разработчики могут задать удостоверение приложения на следующих уровнях: 
1. Уровень процесса. 
2. Уровень контекста (как правило, действия). 
3. Уровень потока. 

Удостоверение, заданное на уровне потока, заменяет удостоверение, заданное на уровне контекста, которое, в свою очередь, заменяет удостоверение, заданное на уровне процесса. Удостоверение, заданное в контексте, используется только в определенных ситуациях. Например, с операциями ввода-вывода файлов никакой контекст не связан. Следующие методы в MAMPolicyManager позволяют задавать удостоверение и получать значения удостоверений, заданные ранее:

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Удостоверение приложения можно сбросить, присвоим ему нулевое значение. В качестве удостоверения можно использовать пустую строку, в случае чего в нему не будут относиться никакие ограничения. Все методы задания удостоверений возвращают соответствующие значения с помощью атрибута ``` MAMIdentitySwitchResult```. Возвращаться могут четыре значения:

1.**SUCCEEDED**: удостоверение успешно изменено. 2.**NOT_ALLOWED**: изменить удостоверение нельзя. Это значение возвращается при попытке переключиться на другого корпоративного пользователя, который относится к той же компании, что и зарегистрированный пользователь. Кроме того, оно выдается при попытке задать удостоверение на уровне пользовательского интерфейса (контекста), в то время как в текущем потоке задано другое удостоверение.
3.**CANCELLED**: пользователь отменил изменение удостоверения (обычно это значение выдается при нажатии кнопки возврата в запросе PIN-кода или авторизации).
4.**FAILED**: не удалось изменить удостоверение по неизвестной причине.

Если удостоверение задается на уровне контекста, результаты передаются асинхронно. Если контекстом является действие, успешность изменения удостоверения нельзя проверить, пока не будет выполнен условный запуск, для чего пользователю может потребоваться ввести PIN-код или полные данные корпоративной учетной записи. Для получения этого результата приложение должно реализовать ```MAMSetUIIdentityCallback```, хотя для данного параметра допускается передача пустого значения.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

Удостоверения на уровне действия можно также задать, не вызывая ``` MAMPolicyManager.setUIPolicyIdentity```, а с помощью метода в MAMActivity. Для этого используется следующий командлет:

 ```public final void switchMAMIdentity(final String newIdentity);```

Приложения могут также переопределять метод в MAMActivity, чтобы получать уведомления о результатах попыток изменения удостоверений на уровне действия. 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Примечание.** Для переключения удостоверения может потребоваться повторное создание действия. В этом случае обратный вызов ```onSwitchMAMIdentityComplete``` осуществляется в новый экземпляр действия.

###<a name="implicit-identity-changes"></a>Неявные изменения удостоверений

Задавать удостоверения могут не только приложения. Удостоверение на уровне потока или контекста может быть изменено с учетом данных, поступивших из другого приложения с поддержкой MAM. Например, если действие запускается при отправке намерения другим приложением MAM, удостоверение этого действия задается в зависимости от удостоверения, действующего в другом приложении на момент отправки намерения.
Для служб удостоверение на уровне потока задается аналогично на время вызова метода onStart или onBind. Вызовы в средство привязки, возвращенные из onBind, также временно задают удостоверение на уровне потока.
Вызовы в ```ContentProvider``` задают удостоверение на уровне потока на время своего действия аналогичным образом.
Кроме того, взаимодействие пользователя с действием может вызвать неявное переключение удостоверения.
Например, если пользователь нажмет кнопку отмены в запросе проверки подлинности во время выполнения действия ```Resume```, произойдет неявное переключение на пустое удостоверение.
Приложение получает возможность узнавать о таких изменениях, а в некоторых случаях и запрещать их, если возникнет такая необходимость. ```MAMService``` и ```MAMContentProvider``` предоставляют следующий метод, который подклассы могут переопределять:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
При использовании ```MAMActivity``` в метод добавляется еще один параметр: 
```
public void onMAMIdentitySwitchRequired(final String identity, 
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
```AppIdentitySwitchReason``` фиксирует источник неявного переключения и может принимать значения ```CREATE```, ```RESUME_CANCELLED``` и ```NEW_INTENT```.  Если действие Resume вызывает отображение запроса PIN-кода, проверки подлинности или других элементов пользовательского интерфейса, связанных с соответствием, а пользователь пытается их отменить (обычно используя кнопку возврата), используется причина ```RESUME_CANCELLED```.
```AppIdentitySwitchResultCallback``` выглядит следующим образом:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
Здесь ```AppIdentitySwitchResult``` имеет значение ```SUCCESS``` или ```FAILURE```. 

Метод ```onMAMIdentitySwitchRequired``` вызывается для всех неявных изменений удостоверения, кроме связанных с возвратом средства привязки из ```MAMService.onMAMBind```. Реализации ```onMAMIdentitySwitchRequired``` по умолчанию незамедлительно вызывают ```reportIdentitySwitchResult(FAILURE)```, если причиной является ```RESUME_CANCELLED```; во всех остальных случаях вызывается ```reportIdentitySwitchResult(SUCCESS)```. 

Предполагается, что большинству приложений не требуется блокировать или откладывать переключение удостоверений каким-либо другим образом, однако если это не так, следует принимать во внимание следующие моменты: *если переключение удостоверения блокируется, результат будет точно таким же, как если бы параметры общего доступа для действия ```Receive``` запрещали передачу данных. *Если служба работает в основном потоке, ```reportIdentitySwitchResult``` **необходимо** вызывать асинхронно, иначе пользовательский интерфейс может зависнуть. 
*Для создания ```Activity``` параметр ```onMAMIdentitySwitchRequired``` будет вызываться до вызова метода ```onMAMCreate```. Если приложение должно отображать интерфейс пользователя, чтобы определить, необходимо ли разрешить переключение удостоверения, интерфейс необходимо отображать, используя другое действие. *Если действие запрашивает переключение на пустое удостоверение по причине ```RESUME_CANCELLED```, приложение должно изменить возобновленное действие таким образом, чтобы отобразить данные, связанные с переключением удостоверения.  Если это невозможно, приложение должно запретить переключение и отобразить повторный запрос для соблюдения политики в отношении возобновления удостоверения (например, вывести экран для ввода PIN-кода). 

**Примечание.** Приложение с несколькими удостоверениями всегда получает входящие данные как из управляемых, так и из неуправляемых приложений. Приложение должно обрабатывать данные из управляемых удостоверений управляемым образом. Если запрошенным удостоверением управляет ```(MAMPolicyManager.getIsIdentityManaged)```, но приложение не может использовать эту учетную запись (например, потому, что учетные записи, такие как учетные записи электронной почты, должны быть сначала настроены в приложении), в переключении удостоверения будет отказано.

##<a name="file-protection"></a>Защита файлов
При создании каждого файла к нему привязывается удостоверение потока или процесса. Оно будет использоваться и для шифрования файлов, и для выборочной очистки. Шифруются только те файлы, удостоверение которых имеет политику, которая требует шифрования. Выборочная очистка пакета SDK по умолчанию удаляет только файлы, связанные с удостоверением, для которого была запрошена очистка. Приложение может запросить или изменить удостоверение файла с помощью ```MAMFileProtectionManager```.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     * 
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     * 
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

**Примечание.** Удостоверение файла маркируется как чувствительное к автономному режиму. Необходимо учитывать указанные ниже моменты.
* Если корпоративный портал не установлен, удостоверения файлов маркировать нельзя. 
* Если корпоративный портал установлен, но приложение не имеет политики, надежная маркировка удостоверений для файлов невозможна.
* Если маркировка удостоверений файлов становится доступной, все созданные ранее файлы считаются личными (относящимися к удостоверению с пустой строкой), однако, если приложение было установлено как управляемое приложение с одним удостоверением, такие файлы будут считаться принадлежащими зарегистрированному пользователю.

###<a name="data-protection"></a>Защита данных
Маркировать файл как принадлежащий нескольким удостоверениям нельзя. Приложения, которые должны сохранять данные, принадлежащие разным пользователям, в один файл, могут делать это с помощью функций, предоставляемых ```MAMDataProtectionManager```. Он позволяет приложению шифровать данные и привязывать их к определенному пользователю. Зашифрованные данные можно сохранять на диск в файле. Вы можете запросить связанные с удостоверением данные и зашифровать их позднее. 

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected 
 * input.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function 
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The 
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original 
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method. 
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the 
 * unprotected input.
     * 
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     * 
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input stream to get information on. Either this input 
 *            stream must have been returned by a previous call to 
     *            protect OR input.markSupported() must return true. 
 *            Otherwise it will be impossible to get protection info 
 *            without advancing the stream position. The stream must be 
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input bytes to get information on. These must be bytes 
 *            returned by a previous call to protect() or a copy of 
 *            such bytes.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
##<a name="content-providers"></a>Поставщики содержимого
Если приложение не предоставляет потенциально корпоративные данные, отличные от ```ParcelFileDescriptor```, через ```ContentProvider```, приложение должно вызывать метод ```MAMContentProvider``` ```isProvideContentAllowed(String)```, передающий владельцу ```UPN``` для содержимого. Если эта функция возвращает значение false, содержимое не может быть возвращено вызывающему. Дескрипторы файлов, возвращенные с помощью поставщика содержимого, обрабатываются автоматически, исходя из удостоверения файла.

##<a name="selective-wipe"></a>выборочная очистка;
Если приложение регистрируется для получения уведомлений ```WIPE_USER_DATA```, оно не получит возможности выборочной очистки, доступные пакету SDK по умолчанию. Для приложений, поддерживающих несколько удостоверений, это может быть существенно, поскольку выборочная очистка MAM по умолчанию удаляет только файлы, соответствующие удостоверению. Если вы разрабатываете приложение с поддержкой нескольких удостоверений, вы можете зарегистрироваться для получения уведомления ```WIPE_USER_AUXILIARY_DATA```, что позволит вам использовать функции очистки пакета SDK по умолчанию. Это уведомление будет отправляться непосредственно перед применением выборочной очистки пакета SDK по умолчанию. Обратите внимание, что одновременно регистрировать приложение для получения уведомлений ```WIPE_USER_DATA``` и ```WIPE_USER_AUXILIARY_DATA``` нельзя.

## <a name="known-platform-limitations"></a>Известные ограничения платформы 

### <a name="file-size-limitations"></a>Ограничения размера файла 

В Android ограничения формата исполняемого файла Dalvik могут вызывать проблемы для больших баз кода, работающих без ProGuard. В частности, могут возникнуть следующие ограничения: 

* Предел в 65 тысяч для полей.

* Предел в 65 тысяч для методов.

При наличии множества проектов каждый android:package получает копию R, что значительно увеличивает число полей при добавлении библиотек. Следующие рекомендации могут помочь устранить это ограничение:
 
* Все проекты библиотеки должны по мере возможности совместно использовать один и тот же android:package. Это приведен к эпизодическим сбоям в рабочей среде, так как данная проблема возникает исключительно во время сборки.   Кроме того, более новые версии пакета SDK для Android будут предварительно обрабатывать файлы DEX, чтобы удалить некоторую избыточность. Это еще больше сокращает расстояние до полей.

* Используйте самые новые из доступных средств сборки пакета SDK для Android.

* Удалите все ненужные и неиспользуемые библиотеки (например, `android.support.v4`).

### <a name="policy-enforcement-limitations"></a>Ограничения применения политики

**Снимок экрана**: пакет SDK не может применить новое значение параметра для снимка экрана в действиях, которые уже прошли через Activity.onCreate. Это может привести к тому, что в течение определенного времени, когда приложение настроено на отключение снимков экрана, снимки экрана по-прежнему могут создаваться.

**Использование сопоставителей содержимого*: политика передачи или получения может полностью или частично блокировать использование сопоставителя содержимого для доступа к поставщику содержимого в другом приложении. Это приводит к тому, что методы ContentResolver возвращают значение NULL или выдают значение сбоя (например, при блокировке `openOutputStream` выдает исключение `FileNotFoundException` ). Приложение может определить, вызван ли (и может ли быть вызван) сбой записи данных через сопоставитель политики, выполнив вызов:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Экспортированные службы**: файл `AndroidManifest.xml` , входящий в состав пакета SDK для приложений Intune, содержит `MAMNotificationReceiverService`, который должен быть экспортированной службой, чтобы разрешить корпоративному порталу отправлять уведомления в приложение с расширенными возможностями. Служба проверяет вызывающий объект, чтобы убедиться, что корпоративный портал может отправлять уведомления. 

## <a name="recommended-android-best-practices"></a>Рекомендации и советы для Android 

Пакет SDK Intune поддерживает контракт, предоставляемый API Android, хотя состояния сбоя могут возникать чаще в результате применения политики. Эти рекомендации для Android позволяют снизить вероятность сбоя: 

* Функции пакета SDK для Android, которые могут возвращать значение NULL, теперь с большей вероятностью равны NULL.  Чтобы свести число возникающих проблем к минимуму, обеспечьте наличие проверок значений NULL в нужных местах.

* Функции, которые могут быть проверены, следует проверять посредством их интерфейсов API из пакета SDK.

* Любые производные функции следует вызвать через их версии суперкласса.

* Избегайте неоднозначного использования любых API. Например, `Activity.startActivityForResult/onActivityResult` без проверки requestCode вызывает нестандартное поведение.






<!--HONumber=Oct16_HO5-->


