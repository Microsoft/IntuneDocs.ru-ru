---
title: "Руководство по пакету SDK для приложений Microsoft Intune для разработчиков под Android | Документация Майкрософт"
description: 
keywords: "Пакет SDK"
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 7d6ac9de7dbfee4336121be69a38600448af2b68


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Руководство по пакету SDK для приложений Intune для разработчиков под Android

> [!NOTE]
> При желании прочтите статью [Обзор пакета SDK для приложений Intune](intune-app-sdk.md), в которой рассмотрены актуальные функции пакета SDK и описана подготовка к интеграции на каждой поддерживаемой платформе.

Пакет SDK для приложений Microsoft Intune для Android позволяет встроить в ваше приложение Android функции управления мобильными приложениями (MAM). Приложение, использующее MAM, — это приложение, интегрированное с пакетом SDK для приложений Intune. Оно позволяет ИТ-администраторам развертывать политики, регулирующие работу мобильного приложения, если Intune управляет им.

## <a name="whats-in-the-sdk"></a>Состав пакета SDK

Пакет SDK для приложений Intune для Android представляет собой стандартную библиотеку Android без внешних зависимостей. Пакет SDK включает в себя следующее:  

* **Microsoft.Intune.MAM.SDK.jar**: интерфейсы, необходимые для включения MAM, а также для взаимодействия с приложением корпоративного портала Microsoft Intune. Приложения должны указывать его как ссылку на библиотеку Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 4. Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 7. Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл.

* **Каталог ресурсов**: ресурсы (например, строки), на которых основан пакет SDK.

* **Microsoft.Intune.MAM.SDK.aar**: компоненты пакета SDK, за исключением JAR-файлов Support.V4 и Support.V7. Этот файл можно использовать вместо отдельных компонентов, если система сборки поддерживает AAR-файлы.

* **AndroidManifest.xml**: дополнительные точки входа и требования к библиотекам.

* **THIRDPARTYNOTICES.TXT**: примечание об атрибуции, где указан сторонний код и (или) код OSS, который будет скомпилирован в ваше приложение.

## <a name="requirements"></a>Requirements (Требования)

Пакет SDK для приложений Intune представляет собой скомпилированный проект Android. Поэтому он слабо зависит от версии Android, используемой приложением для минимальных или целевых версий API. Пакет SDK поддерживает Android API с 14 (Android 4.0+) до 24.

Для включения политики MAM пакету SDK для приложений Intune для Android требуется, чтобы на устройстве присутствовало приложение [корпоративного портала](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). Для MAM без регистрации устройства пользователю *не* нужно регистрировать устройство в приложении корпоративного портала.


## <a name="how-the-intune-app-sdk-works"></a>Принцип работы пакета SDK для приложений Intune

###<a name="entry-points"></a>Точки входа

Для включения политик управления приложениями пакету SDK для приложений Intune требуется внести изменения в исходный код приложения. Это осуществляется путем замены базовых классов Android на эквивалентные базовые классы Intune с префиксом `MAM`. Классы пакета SDK располагаются между базовым классом Android и производной версией этого класса в самом приложении. Используя действие в качестве примера, вы получаете иерархию наследования, которая выглядит следующим образом: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Например, если `AppSpecificActivity` взаимодействует со своим родительским элементом (например, вызывая `super.onCreate()`), `MAMActivity` является суперклассом.

Типичные приложения Android имеют одиночный режим и получают доступ ко всей системе через свой объект [Context](https://developer.android.com/reference/android/content/Context.html). С другой стороны, приложения с внедренным пакетом SDK для приложений Intune имеют двойной режим. Эти приложения по-прежнему получают доступ к системе через объект `Context`. В зависимости от используемого базового `Activity` объект `Context` будет предоставляться системой Android или будет интеллектуально мультиплексирован между ограниченным представлением системы и `Context`, предоставляемым системой Android.

При переопределении [точки входа](https://developer.android.com/guide/components/fundamentals.html) Android ее эквивалентом MAM следует использовать MAM-версию жизненного цикла точки входа (за исключением класса `MAMApplication`).

Например, при наследовании от `MAMActivity` вместо переопределения `onCreate` и вызова `super.onCreate` объекту `Activity` необходимо переопределить `onMAMCreate` и вызвать `super.onMAMCreate`. Это позволяет Intune ограничить запуск `Activity` (среди прочего) в некоторых случаях.


###<a name="sdk-permissions"></a>Разрешения пакета SDK

Пакету SDK для приложений Intune требуются три [разрешения системы Android](https://developer.android.com/guide/topics/security/permissions.html) в отношении приложений, в которые он интегрируется:

* `android.permission.GET_ACCOUNTS` (запрашивается во время выполнения при необходимости)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Эти разрешения требуются библиотеке проверки подлинности Active Directory Azure ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) для проверки подлинности через посредника. Если эти разрешения приложению не предоставлены или отменены пользователем, проверка подлинности, для которой требуется посредник (приложение корпоративного портала), будет отключена.


###<a name="company-portal-app"></a>Приложение корпоративного портала

Для чего нужно приложение корпоративного портала? Когда приложение корпоративного портала устанавливается на устройство и получает политику ограничения использования приложений для пользователя из службы Intune, точки входа SDK инициализируются асинхронно. Инициализация требуется только в том случае, когда процесс изначально создается Android. Во время инициализации устанавливается подключение к приложению корпоративного портала, а затем из приложения загружается политика ограничений.  

> [!NOTE]
> Если приложение корпоративного портала на устройстве не установлено, поведение приложения с поддержкой MAM не изменится, и оно будет работать точно так же, как и обычное приложение.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Интеграция с пакетом SDK для приложений Intune

Как уже говорилось, для включения политик управления приложениями пакету SDK требуется внести изменения в исходный код приложения. Ниже приведены шаги, необходимые для включения MAM в приложении.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Замена классов, методов и действий на их эквивалент MAM (обязательно)

Базовые классы Android необходимо заменить соответствующими эквивалентами MAM. Для этого найдите все экземпляры классов, перечисленных в следующей таблице, и замените их эквивалентом из пакета SDK для приложений Intune.

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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (требуется только в тех случаях, если модуль привязки не сформирован на основе интерфейса AIDL) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppилиt.v4.jar**:

| Класс Android в Intune MAM | Аналог в пакете SDK для приложений Intune |
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
>Помните, что при переопределении [точки входа](https://developer.android.com/guide/components/fundamentals.html) Android ее эквивалентом MAM следует использовать MAM-версию жизненного цикла точки входа (за исключением класса `MAMApplication`).
>
>Например, при наследовании от `MAMActivity` вместо переопределения `onCreate` и вызова `super.onCreate` объекту `Activity` необходимо переопределить `onMAMCreate` и вызвать `super.onMAMCreate`. Это позволяет Intune ограничить запуск `Activity` (среди прочего) в некоторых случаях.

#### <a name="pendingintent-classes-and-renamed-methods"></a>Классы PendingIntents и переименованные методы

После наследования от одной из точек входа MAM можно безопасно использовать `Context` обычным образом, например формируя `Activity` классы и используя `PackageManager`.  

Классы `PendingIntent` являются исключением из этого правила. При вызове таких классов необходимо изменить имя класса. Например, вместо `PendingIntent.get*` следует использовать метод `MAMPendingIntent.get*`. После этого можно использовать полученный `PendingIntent` обычным образом.

Иногда метод, доступный в классе Android, может быть помечен как окончательный в замещающем классе MAM. В этом случае замещающий класс MAM предоставляет метод с таким же именем (обычно добавляется суффикс `MAM`), который должен быть переопределен вместо исходного. Например, вместо переопределения `ContentProvider.query`нужно переопределить `MAMContentProvider.queryMAM`. Компилятор Java должен налагать окончательные ограничения во избежание случайного переопределения исходного метода вместо его эквивалента MAM.

###<a name="enable-features-that-require-app-participation"></a>Включение функций, требующих содействия со стороны приложения

Некоторые политики пакет SDK не может реализовать самостоятельно. Приложение может управлять своим поведением для выполнения этих функций, используя несколько интерфейсов API, которые находятся в указанном ниже интерфейсе `AppPolicy`.

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

### <a name="enable-it-control-over-app-saving-behavior"></a>Предоставление ИТ-администратору возможности управления поведением сохранения приложений

Во многих приложениях реализованы функции, позволяющие пользователям сохранять файлы локально или в облачном хранилище. Пакет SDK для приложений Intune позволяет ИТ-администраторам защититься от утечки данных за счет применения ограничений политик, уместных для их организации.  Одной из политик, которой может управлять администратор, является возможность пользователя сохранять данные в личном хранилище. Сюда входит сохранение в локальной папке, на SD-карте или в сторонних службах резервного копирования.

Для включения этой функции требуется содействие со стороны приложения. Если приложение позволяет сохранять данные в личное или облачное расположение непосредственно из приложения, необходимо реализовать эту функцию, чтобы предоставить ИТ-администратору возможность разрешать и запрещать сохранение в расположение.   

Чтобы определить, применяется ли политика, приложение может сделать следующий вызов. Этот вызов позволяет приложению узнать, допускает ли политика текущего администратора Intune сохранение данных в личном хранилище. После этого приложение может применить политику, так как ему известно о том, что хранилище личных данных доступно пользователю через это приложение.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` всегда будет возвращать политику приложений, отличную от NULL, даже если устройство или приложение не управляются Intune.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Разрешение определения потребности в политике ПИН-кодов для приложения

Для реализации некоторых ограничений Intune можно отключить некоторые функции приложения, чтобы избежать дублирования функций пакета SDK для приложений Intune. Например, если приложение имеет собственный пользовательский интерфейс для использования ПИН-кодов, возможно, его потребуется отключить, если пакет SDK настроен для запроса ПИН-кода у пользователя.

Чтобы определить, настроена ли политика ПИН-кода Intune для запроса ПИН-кода при запуске, приложение может сделать следующий вызов:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Регистрация для получения уведомлений из пакета SDK  

Пакет SDK для приложений Intune позволяет приложению управлять поведением определенных политик, таких как политики выборочной очистки, развернутых ИТ-администратором. Когда ИТ-администратор развертывает такую политику, служба Intune отправляет уведомление пакету SDK.

Ваше приложение должно зарегистрироваться для получения уведомлений из пакета SDK, создав класс `MAMNotificationReceiver` и зарегистрировав его с помощью `MAMNotificationReceiverRegistry`. Для этого укажите получателя, а также тип необходимых уведомлений в `App.onCreate`, как показано в следующем примере:

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

`MAMNotificationReceiver` просто получает уведомления из службы Intune. Пакет SDK обрабатывает некоторые уведомления самостоятельно. Для других уведомлений требуется участие приложения.

Приложение *должно* возвращать для уведомления значение true или false. Оно должно всегда возвращать значение true, за исключением случаев, когда какое-либо действие, которое приложение пыталось выполнить в результате уведомления, завершилось со сбоем. Этот сбой может быть зарегистрирован в службе Intune. Подобная ситуация может возникнуть, например, в случае, если приложение не смогло очистить данные пользователя после того, как ИТ-администратор запустил очистку.

Можно безопасно осуществить блокировку в `MAMNotificationReceiver.onReceive`, так как его обратный вызов не выполняется в потоке пользовательского интерфейса.

Следующий интерфейс `MAMNotificationReceiver` определен в пакете SDK:

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

###<a name="types-of-notifications"></a>Типы уведомлений

В приложение отправляются указанные ниже уведомления. Некоторые из них могут потребовать участия приложения.

* **`WIPE_USER_DATA`**: это уведомление отправляется в классе `MAMUserNotification`. При получении этого уведомления приложение должно удалить все данные, связанные с "корпоративным" удостоверением, переданным с классом `MAMUserNotification`. Сейчас это уведомление отправляется во время отмены регистрации службы Intune. Первичное имя пользователя обычно указывается во время регистрации. В случае регистрации для этого уведомления приложению необходимо убедиться, что все данные пользователя удалены. Если регистрация для него не выполняется, приложение использует поведение выборочной очистки по умолчанию.

* **`WIPE_USER_AUXILIARY_DATA`**: приложения могут регистрироваться для этого уведомления, если им необходимо, чтобы пакет SDK для приложений Intune выполнял выборочную очистку по умолчанию, но при этом требуется удалить некоторые дополнительные данные.  

* **`REFRESH_POLICY`**: это уведомление отправляется в `MAMUserNotification`. При получении этого уведомления все кэшированные политики Intune должны быть признаны недействительными и обновлены. Пакет SDK обычно обрабатывает эту задачу. Однако если политика используется каким-либо постоянным образом, эту задачу должно обрабатывать приложение.



### <a name="protection-of-backup-data"></a>Защита резервных данных

Начиная с Android Marshmallow (API 23), система Android предоставляет два способа резервного копирования данных приложением. Каждый вариант доступен в приложении и требует разных действий для правильного обеспечения защиты данных Intune. Дополнительные сведения о способах резервного копирования см. в [справочнике по API Android](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Автоматическое резервное копирование для приложений

Начиная с устройств Android Marshmallow, система Android начала предлагать [автоматическое полное резервное копирование](https://developer.android.com/guide/topics/data/autobackup.html) приложений независимо от целевого API. Если в файле AndroidManifest.xml явно задать для атрибута `android:allowBackup` значение false, Android не будет добавлять приложение в очереди на резервное копирование, а корпоративные данные останутся в приложении. В этом случае никаких дополнительных действий не требуется.

По умолчанию атрибут `android:allowBackup` имеет значение true, даже если `android:allowBackup` не указан в файле манифеста. Это означает, что для всех приложений автоматически создаются резервные копии в учетной записи пользователя на диске Google, т. е. используется поведение по умолчанию, связанное с *риском утечки данных*. Для защиты данных в пакет SDK следует внести описанные ниже изменения. Если вы хотите, чтобы ваше приложение работало на устройствах Android Marshmallow, выполните представленные ниже рекомендации по защите клиентских данных.  

Если вы не создавали агент резервного копирования с помощью `MAMBackupAgent` или `MAMBackupAgentHelper`, необходимо учитывать и контролировать способ отправки данных приложения функцией автоматического резервного копирования. Intune позволяет использовать все доступные [функции автоматического резервного копирования](https://developer.android.com/guide/topics/data/autobackup.html) в Android, включая возможность определения настраиваемых правил в формате XML. Однако для обеспечения безопасности данных требуется выполнить следующие действия:

1. Разрешите полное автоматическое резервное копирование, соответствующее политике Intune, с помощью `MAMBackupAgent` по умолчанию. Вставьте `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` в манифест своего приложения.

2. Выберите тип полного резервного копирования для своего приложения (без фильтра, с фильтром или отсутствует), задав для атрибута `android:fullBackupContent` значение true или false либо указав XML-ресурс в своем приложении. Скопируйте все, что необходимо вставить в атрибут `android:fullBackupContent`, в тег метаданных с именем `com.microsoft.intune.mam.FullBackupContent`.

    Например, если вы хотите, чтобы для приложения создавались полные резервные копии в соответствии с правилами, заданными в XML-файле, укажите имя этого файла в манифесте, используя тег метаданных `com.microsoft.intune.mam.FullBackupContent` следующим образом:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Резервное копирование пар "ключ-значение"

Возможность резервного копирования пар "ключ-значение" доступна для всех API и использует `BackupAgentHelper` и `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` гораздо проще, чем `BackupAgent`, как с точки зрения собственных функций Android, так и с точки зрения интеграции MAM. `BackupAgentHelper` позволяет регистрировать целые файлы и общие настройки в `FileBackupHelper` или `SharedPreferencesBackupHelper`, соответственно. После создания они добавляются в `BackupAgentHelper`.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent` позволяет более явно задать, какие именно данные следует копировать. Однако этот вариант не позволяет воспользоваться преимуществами платформы резервного копирования Android. Поскольку вы отвечаете за реализацию, существуют дополнительные шаги, необходимые для обеспечения защиты данных из MAM. Поскольку большая часть работы возложена на вас как разработчика, интеграция MAM играет более важную роль.

###### <a name="app-does-not-have-a-backup-agent"></a>У приложения нет агента резервного копирования

Это варианты, доступные разработчику при `android:allowBackup =true`:

####### <a name="full-backup-according-to-a-configuration-file"></a>Полное резервное копирование в соответствии с файлом конфигурации

Укажите ресурс в теге метаданных `com.microsoft.intune.mam.FullBackupContent` в манифесте. Пример:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Добавьте следующий атрибут в тег `<application>` : `android:fullBackupContent="@xml/my_scheme"`, где `my_scheme` является XML-ресурсом в приложении.

####### <a name="full-backup-without-exclusions"></a>Полное резервное копирование без исключений

Укажите тег в манифесте, например `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Добавьте атрибут `android:fullBackupContent="true"` в тег `<application>`.

###### <a name="app-has-a-backup-agent"></a>У приложения есть агент резервного копирования

Следуйте рекомендациям, приведенным ранее в этом руководстве для `BackupAgent` и `BackupAgentHelper`.

Рассмотрите возможность использования `MAMDefaultFullBackupAgent`, который обеспечивает простое и удобное резервное копирование в Android Marshmallow.

##### <a name="before-your-backup"></a>Подготовка к резервному копированию

Перед началом резервного копирования следует убедиться, что буферы файлов или данных, которые вы планируете копировать, разрешены для резервного копирования. Для этого мы предоставили функцию `isBackupAllowed` в `MAMFileProtectionManager` и `MAMDataProtectionManager`. Если буфер данных или файлов не разрешен для резервного копирования, вам не следует использовать его в рамках резервного копирования.

Если в определенный момент во время резервного копирования вам потребуется выполнить резервное копирование удостоверений для файлов, проверенных на шаге 1, следует вызвать `backupMAMFileIdentity(BackupDataOutput data, File … files)` с файлами, из которых вы планируете извлекать данные. При этом автоматически создаются новые сущности резервного копирования, которые записываются в `BackupDataOutput`. Эти сущности будут автоматически использоваться при восстановлении.

#### <a name="azure-directory-authentication-library-setup"></a>Настройка библиотеки проверки подлинности Azure Active Directory  

Пакет SDK использует ADAL в рамках своих процедур проверки подлинности и условного запуска. Эти сценарии требуют, чтобы приложения использовали некоторую часть конфигурации Azure Active Directory (Azure AD). Значения конфигурации передаются в пакет SDK через метаданные `AndroidManifest` .

Чтобы настроить приложение и реализовать надлежащую проверку подлинности, добавьте следующий код в узел приложения в `AndroidManifest`. Некоторые из этих конфигураций необходимы только тогда, когда приложение использует ADAL для общей проверки подлинности. В этом случае потребуются конкретные значения, использованные приложением при регистрации в Azure AD. Это позволяет предотвратить ситуацию, когда пользователь получает два запроса проверки подлинности, так как Azure AD распознает два отдельных значения регистрации: одно из приложения и одно из пакета SDK.

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

##### <a name="common-adal-configurations"></a>Распространенные конфигурации ADAL

Ниже приведены распространенные конфигурации для описанных выше значений.

###### <a name="app-does-not-integrate-adal"></a>Приложение не интегрируется с ADAL

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи Azure AD.

* SkipBroker необходимо присвоить значение true.

###### <a name="app-integrates-adal"></a>Приложение интегрируется с ADAL

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи Azure AD.

* Client ID необходимо присвоить идентификатор клиента.

* `NonBrokerRedirectURI` необходимо присвоить допустимый URI перенаправления для приложения. Или `urn:ietf:wg:oauth:2.0:oob` должен быть настроен в качестве допустимого URI перенаправления Azure AD.

* SkipBroker необходимо присвоить значение false (либо значение должно отсутствовать).

* Azure AD необходимо настроить для приема URI перенаправления брокера.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>Приложение интегрируется с ADAL, но не поддерживает приложение проверки подлинности Azure AD Authenticator

* Полномочия должны быть присвоены требуемой среде, где были настроены учетные записи Azure AD.

* Client ID необходимо присвоить идентификатор клиента.

* `NonBrokerRedirectURI` необходимо присвоить допустимый URI перенаправления для приложения. Или `urn:ietf:wg:oauth:2.0:oob` должен быть настроен в качестве допустимого URI перенаправления Azure AD.

#### <a name="logging-in-the-sdk"></a>Ведение журнала в пакете SDK

Ведение журнала осуществляется посредством платформы `java.util.logging` . Чтобы получать журналы, настройте глобальное ведение журналов, как описано в [техническом руководстве по Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). В зависимости от конкретного приложения оптимальным местом для инициации ведения журналов обычно является `App.onCreate`. Обратите внимание на то, что сообщения журнала идентифицируются по имени класса, которое может быть скрыто.

###<a name="multi-identity"></a>Множественная идентификация

По умолчанию пакет SDK для приложений Intune применяет политику ко всему приложению. Использование нескольких удостоверений — это функция MAM, которую можно включить для применения политики на уровне удостоверения. Для этого требуется намного больше содействия со стороны приложения, чем для других функций MAM. Приложение должно уведомить пакет SDK о том, что оно собирается заменить активное удостоверение. Пакет SDK также должен уведомлять приложение, когда требуется заменить удостоверение.

Сейчас поддерживается только одно управляемое удостоверение. После регистрации приложения или устройства пользователем пакет SDK использует это удостоверение, считая его основным управляемым удостоверением. Другие пользователи в приложении рассматриваются как неуправляемые и не имеют ограничений для параметров политик.

Обратите внимание, что удостоверение определяется просто в виде строки. В удостоверениях не учитывается регистр. Запросы удостоверения, направляемые пакету SDK, могут возвращать удостоверения с регистром, отличным от изначального.

####<a name="enabling-multi-identity"></a>Включение множественного удостоверения

По умолчанию все приложения считаются приложениями с одним удостоверением. Приложение объявляет о своей поддержке множественных удостоверений, добавляя в манифест Android следующие метаданные.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Задание удостоверения

Вы можете задать удостоверение приложения на следующих уровнях:

1. Уровень процесса.

2. Уровень контекста (как правило, `Activity`).

3. Уровень потока.

Удостоверение, заданное на уровне потока, заменяет удостоверение, заданное на уровне `Context`, которое, в свою очередь, заменяет удостоверение, заданное на уровне процесса. Удостоверение, заданное в `Context`, используется только в случае необходимости. Например, с задачами файлового ввода-вывода никакой `Context` не связан. Вы можете использовать следующие методы в `MAMPolicyManager`, чтобы задать удостоверение и получить значения удостоверений, заданные ранее:

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
Удостоверение приложения можно сбросить, присвоим ему нулевое значение. В качестве удостоверения можно использовать пустую строку, в случае чего в нему не будут относиться никакие ограничения. Все методы задания удостоверений возвращают соответствующие значения с помощью атрибута ``` MAMIdentitySwitchResult```. Могут быть возвращены четыре значения:

* **SUCCEEDED**: изменение удостоверения выполнено успешно.

* **NOT_ALLOWED**: изменение удостоверения запрещено. Это значение возвращается при попытке переключиться на другого корпоративного пользователя, который относится к той же организации, что и зарегистрированный пользователь. Кроме того, оно выдается при попытке задать удостоверение на уровне пользовательского интерфейса (`Context`), в то время как в текущем потоке задано другое удостоверение.

* **CANCELLED**: пользователь отменил изменение удостоверения (обычно это значение выдается при нажатии кнопки возврата в запросе PIN-кода или авторизации).

* **FAILED**: не удалось изменить удостоверение по неизвестной причине.

Если удостоверение задается на уровне `Context`, результаты передаются асинхронно. Если `Context` является классом `Activity`, сведения о том, было ли изменение удостоверения успешным, становятся доступны только после условного запуска. При условном запуске пользователю может потребоваться ввести ПИН-код или полные корпоративные учетные данные. Для получения этого результата приложение должно реализовать ```MAMSetUIIdentityCallback```, хотя для данного параметра допускается передача пустого значения.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Удостоверения на уровне действия можно также задать, не вызывая ```MAMPolicyManager.setUIPolicyIdentity```, а с помощью метода в `MAMActivity`. Для этого используется следующий командлет:

 ```public final void switchMAMIdentity(final String newIdentity);```

Приложения могут также переопределять метод в `MAMActivity`, чтобы получать уведомления о результатах попыток изменения удостоверений на уровне действия.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Для переключения удостоверения может потребоваться повторное создание действия. В этом случае обратный вызов ```onSwitchMAMIdentityComplete``` осуществляется в новый экземпляр действия.


####<a name="implicit-identity-changes"></a>Неявные изменения удостоверений

Задавать удостоверения могут не только приложения. Удостоверение на уровне потока или контекста может быть изменено с учетом данных, поступивших из другого приложения с поддержкой MAM. Например, если действие запускается из класса `Intent`, отправленного другим приложением MAM, удостоверение этого действия задается в зависимости от удостоверения, действующего в другом приложении на момент отправки класса `Intent`.

Для служб удостоверение на уровне потока задается аналогично на время вызова метода `onStart` или `onBind`. Вызовы в `Binder`, возвращенные из `onBind`, также временно задают удостоверение на уровне потока. Вызовы в ```ContentProvider``` задают удостоверение на уровне потока на время своего действия аналогичным образом.

Кроме того, взаимодействие пользователя с действием может вызвать неявное переключение удостоверения. Например, если пользователь нажмет кнопку отмены в запросе проверки подлинности во время выполнения действия ```Resume```, произойдет неявное переключение на пустое удостоверение.
Приложение может узнавать о таких изменениях, а в некоторых случаях и запрещать их, если возникнет такая необходимость. ```MAMService``` и ```MAMContentProvider``` предоставляют следующий метод, который подклассы могут переопределять:

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
Часть ```AppIdentitySwitchReason``` фиксирует источник неявного переключения. Она может принимать значения ```CREATE```, ```RESUME_CANCELLED``` и ```NEW_INTENT```.  Если возобновление действия вызывает отображение запроса PIN-кода, проверки подлинности или других элементов пользовательского интерфейса, связанных с соответствием, а пользователь пытается их отменить (обычно с помощью кнопки возврата), используется причина ```RESUME_CANCELLED```.
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
```AppIdentitySwitchResult``` имеет значение ```SUCCESS``` или ```FAILURE```.

Метод ```onMAMIdentitySwitchRequired``` вызывается для всех неявных изменений удостоверения, кроме связанных с классом `Binder`, возвращенным из ```MAMService.onMAMBind```. Реализация ```onMAMIdentitySwitchRequired``` по умолчанию незамедлительно вызывает ```reportIdentitySwitchResult(FAILURE)```, если причиной является ```RESUME_CANCELLED```; во всех остальных случаях вызывается ```reportIdentitySwitchResult(SUCCESS)```.

Большинству приложений, вероятнее всего, не потребуется блокировать или откладывать переключение удостоверения иным образом. Однако если приложению это нужно, необходимо учитывать следующее:

* Если переключение удостоверения заблокировано, результат аналогичен случаю, когда параметры общего доступа ```Receive``` запрещают входящие данные.

* Если служба работает в основном потоке, ```reportIdentitySwitchResult``` *необходимо* вызывать асинхронно, иначе пользовательский интерфейс может зависнуть.

* Для создания ```Activity``` параметр ```onMAMIdentitySwitchRequired``` будет вызываться до вызова метода ```onMAMCreate```. Если приложение должно отображать интерфейс пользователя, чтобы определить, необходимо ли разрешить переключение удостоверения, интерфейс необходимо отображать, используя другое действие.

* Если в ```Activity``` запрашивается переключение на пустое удостоверение по причине ```RESUME_CANCELLED```, приложение должно изменить возобновленное действие таким образом, чтобы отобразить данные, связанные с переключением удостоверения. Если это невозможно, приложение должно запретить переключение. Кроме того, нужно отобразить пользователю повторный запрос для соблюдения политики в отношении возобновления удостоверения (например, вывести экран для ввода PIN-кода).

> [!NOTE]
> Приложение с несколькими удостоверениями всегда получает входящие данные как из управляемых, так и из неуправляемых приложений. Приложение должно обрабатывать данные из управляемых удостоверений управляемым образом. Если запрошенным удостоверением управляет ```(MAMPolicyManager.getIsIdentityManaged)```, но приложение не может использовать эту учетную запись (например, потому, что учетные записи, такие как учетные записи электронной почты, должны быть сначала настроены в приложении), в переключении удостоверения должно быть отказано.

###<a name="file-protection"></a>Защита файлов

При создании каждого файла к нему привязывается удостоверение потока или процесса. Оно используется и для шифрования файлов, и для выборочной очистки. Шифруются только те файлы, удостоверение которых имеет политику, требующую шифрование. Выборочная очистка пакета SDK по умолчанию удаляет только файлы, связанные с удостоверением, для которого была запрошена очистка. Приложение может запросить или изменить удостоверение файла с помощью ```MAMFileProtectionManager```.
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

> [!NOTE]
> Удостоверение файла маркируется как чувствительное к автономному режиму. Примите во внимание следующее:
> * Если приложение корпоративного портала не установлено, удостоверения файлов маркировать нельзя.
>
> * Если приложение корпоративного портала установлено, но приложение не имеет политики, надежная маркировка удостоверений для файлов невозможна.
>
> * Если маркировка удостоверений файлов становится доступной, все созданные ранее файлы считаются личными (относящимися к удостоверению с пустой строкой), если только приложение не было установлено как управляемое приложение с одним удостоверением. В этом случае они считаются принадлежащими зарегистрированному пользователю.

####<a name="data-protection"></a>Защита данных

Маркировать файл как принадлежащий нескольким удостоверениям нельзя. Приложения, которые должны сохранять данные, принадлежащие разным пользователям, в один файл, позволяют сделать это вручную с помощью функций, предоставляемых ```MAMDataProtectionManager```. Это позволяет приложению шифровать данные и привязывать их к определенному пользователю. Зашифрованные данные можно сохранять на диск в файле. Вы можете запросить связанные с удостоверением данные и зашифровать их позднее.

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
###<a name="content-providers"></a>Поставщики содержимого

Если приложение не предоставляет потенциально корпоративные данные, отличные от ```ParcelFileDescriptor```, через ```ContentProvider```, оно должно вызывать метод ```isProvideContentAllowed(String)``` ```MAMContentProvider```, передающий владельцу ```UPN``` для содержимого. Если эта функция возвращает значение false, содержимое не может быть возвращено вызывающему. Дескрипторы файлов, возвращенные с помощью поставщика содержимого, обрабатываются автоматически с учетом удостоверения файла.

###<a name="selective-wipe"></a>Selective wipe (Выборочная очистка)

Если приложение регистрируется для получения уведомлений ```WIPE_USER_DATA```, оно не получит возможности выборочной очистки, доступные пакету SDK по умолчанию. Для приложений, поддерживающих несколько удостоверений, это может быть существенно, поскольку выборочная очистка MAM по умолчанию удаляет только файлы, соответствующие удостоверению.

Если вы создаете приложение с поддержкой нескольких удостоверений, можно зарегистрироваться для получения ```WIPE_USER_AUXILIARY_DATA```. Это уведомление позволяет использовать преимущества очистки по умолчанию в пакете SDK. Оно будет отправляться непосредственно перед применением выборочной очистки по умолчанию в пакете SDK. Обратите внимание, что одновременно регистрировать приложение для получения уведомлений ```WIPE_USER_DATA``` и ```WIPE_USER_AUXILIARY_DATA``` нельзя.

### <a name="known-platform-limitations"></a>Известные ограничения платформы

#### <a name="file-size-limitations"></a>Ограничения размера файла

В Android ограничения формата файлов Dalvik Executable могут вызывать проблемы для больших баз кода, работающих без ProGuard. В частности, могут налагаться следующие ограничения:

* Предел в 65 тысяч для полей.

* Предел в 65 тысяч для методов.

При наличии множества проектов каждый `android:package` получает копию R, что значительно увеличивает число полей при добавлении библиотек. Следующие рекомендации могут помочь устранить это ограничение:

* Все проекты библиотеки должны по мере возможности совместно использовать один и тот же `android:package`. Это не приведет к эпизодическим сбоям в рабочей среде, так как данная проблема возникает исключительно во время сборки. Кроме того, более новые версии пакета SDK для Android будут предварительно обрабатывать файлы DEX, чтобы удалить некоторую избыточность. Это еще больше сокращает расстояние до полей.

* Используйте самые новые из доступных средств сборки пакета SDK для Android.

* Удалите все ненужные и неиспользуемые библиотеки (например, `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Ограничения применения политики

**Снимок экрана**: пакет SDK не может применить новое значение параметра для снимка экрана в классах `Activity`, которые уже прошли через `Activity.onCreate`. Это может привести к тому, что в течение определенного времени, когда приложение настроено на отключение снимков экрана, снимки экрана по-прежнему могут создаваться.

**Сопоставители содержимого**: политика передачи или получения может полностью или частично блокировать использование сопоставителя содержимого для доступа к поставщику содержимого в другом приложении. В результате методы `ContentResolver` возвращают значение NULL или выдают значение сбоя. (Например, `openOutputStream` в случае блокировки выдает `FileNotFoundException`.) Приложение может выполнить этот вызов, чтобы проверить, вызвала ли (или могла ли вызвать) политика сбой при записи данных через сопоставитель содержимого:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Экспортированные службы**: файл `AndroidManifest.xml`, включенный в пакет SDK для приложений Intune, имеет `MAMNotificationReceiverService`. Чтобы приложение корпоративного портала могло отправлять уведомления в поддерживающее приложение, это должна быть экспортированная служба. Служба проверяет вызывающий объект, чтобы убедиться, что приложение корпоративного портала может отправлять уведомления.

### <a name="android-best-practices"></a>Рекомендации для Android

Пакет SDK Intune поддерживает контракт, предоставляемый API Android, хотя состояния сбоя могут возникать чаще в результате применения политики. Эти рекомендации для Android позволяют снизить вероятность сбоя:

* Функции пакета SDK для Android, которые могут возвращать значение NULL, теперь с большей вероятностью равны NULL. Чтобы свести число возникающих проблем к минимуму, обеспечьте наличие проверок значений NULL в нужных местах.

* Для функций, которые можно проверить, используйте в этих целях интерфейсы API пакета SDK.

* Любые производные функции следует вызвать через их версии суперкласса.

* Избегайте неоднозначного использования любых API. Например, `Activity.startActivityForResult/onActivityResult` без проверки `requestCode` вызывает нестандартное поведение.



<!--HONumber=Dec16_HO2-->


