---
title: "Руководство по пакету SDK для приложений Intune для разработчиков под Android"
description: "Пакет SDK для приложений Microsoft Intune для Android позволяет встроить в ваше приложение Android функции управления мобильными приложениями (MAM)."
keywords: "Пакет SDK"
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: b5ad9cc6c03712090398cacb3d4bb653deb1d2a4
ms.openlocfilehash: 7dfcc0bf8f3da1e600df59927db6e78ec2021e0f
ms.contentlocale: ru-ru
ms.lasthandoff: 06/12/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Руководство по пакету SDK для приложений Intune для разработчиков под Android

> [!NOTE]
> При желании прочтите статью [Обзор пакета SDK для приложений Intune](app-sdk.md), в которой рассмотрены актуальные функции пакета SDK и описана подготовка к интеграции на каждой поддерживаемой платформе.

Пакет SDK для приложений Microsoft Intune для Android позволяет встроить в ваше собственное приложение для Android **политики защиты приложений — APP** (или политики управления мобильными приложениями — MAM). В приложение с поддержкой MAM интегрирован пакет SDK для приложений Intune. Администраторы Intune могут развертывать политики защиты приложений в вашем мобильном приложении с поддержкой Intune, когда Intune активно управляет им.


## <a name="whats-in-the-sdk"></a>Состав пакета SDK

Пакет SDK для приложений Intune состоит из следующих файлов:  

* **Microsoft.Intune.MAM.SDK.aar**: компоненты пакета SDK, за исключением JAR-файлов Support.V4 и Support.V7. Этот файл можно использовать вместо отдельных компонентов, если система сборки поддерживает AAR-файлы.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 4. Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: интерфейсы, необходимые для включения MAM в приложениях, использующих библиотеку поддержки Android версии 7. Приложения, которым требуется такая поддержка, должны ссылаться непосредственно на JAR-файл.
* **proguard.txt**: содержит правила ProGuard, которые должны применяться при создании с помощью ProGuard.
* **CHANGELOG.txt**: содержит запись изменений, внесенных в каждую версию пакета SDK.
* **THIRDPARTYNOTICES.TXT**: примечание об атрибуции, где указан сторонний код и (или) код OSS, который будет скомпилирован в ваше приложение.

Если система сборки не поддерживает файлы AAR, можно использовать вместо Microsoft.Intune.MAM.SDK.aar следующие файлы.
* **Microsoft.Intune.MAM.SDK.jar**: интерфейсы, необходимые для включения MAM и взаимодействия с приложением корпоративного портала Microsoft Intune. Приложения должны указывать его как ссылку на библиотеку Android.
* **Каталог ресурсов**: ресурсы (например, строки), которые использует пакет SDK.
* **AndroidManifest.xml**: точки входа и требования к библиотекам.


## <a name="requirements"></a>Requirements (Требования)

Пакет SDK для приложений Intune представляет собой скомпилированный проект Android. Поэтому он практически не зависит от версии Android, используемой приложением для минимальных или целевых версий API. Пакет SDK поддерживает API Android начиная с версии 14 (Android 4.0+) и заканчивая версией 25 (Android 7.1).



### <a name="company-portal-app"></a>Приложение корпоративного портала
Для включения политик защиты приложений пакету SDK для приложений Intune для Android требуется наличие на устройстве приложения [корпоративного портала](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). Корпоративный портал извлекает политики защиты приложения из службы Intune. При инициализации приложения политики и код загружаются для реализации этой политики на корпоративном портале.

> [!NOTE]
> Если приложение корпоративного портала отсутствует на устройстве, приложение с поддержкой Intune будет работать так же, как обычное приложение, не поддерживающее политики защиты приложений Intune.

Чтобы включить защиту приложений без регистрации устройства, пользователю _**не**_ нужно регистрировать устройство с помощью приложения корпоративного портала.

## <a name="sdk-integration"></a>Интеграция пакета SDK

### <a name="build-integration"></a>Интеграция сборки

Пакет SDK для приложений Intune — это стандартная библиотека Android без внешних зависимостей. **Microsoft.Intune.MAM.SDK.jar** содержит оба интерфейса, необходимых для включения политики защиты приложений, а также код, необходимый для взаимодействия с приложением корпоративного портала Microsoft Intune.

**Microsoft.Intune.MAM.SDK.jar** нужно указать как ссылку на библиотеки Android. Чтобы сделать это, откройте проект приложения в Android Studio и выберите **File > New > New module** (Файл > Создать > Новый модуль), а затем щелкните **Import .JAR/.AAR Package** (Импорт пакета .JAR/AAR). Выберите наш пакет Android с архивом Microsoft.Intune.MAM.SDK.aar.

Кроме того, **Microsoft.Intune.MAM.SDK.Support.v4** и **Microsoft.Intune.MAM.SDK.Support.v7** содержат варианты Intune `android.support.v4` и `android.support.v7` соответственно. Они не встроены в Microsoft.Intune.MAM.SDK.aar, если приложение не должно включать библиотеки поддержки. Это стандартные файлы JAR, используемые вместо проектов библиотек Android.

#### <a name="proguard"></a>ProGuard

Если на этапе сборки используется [ProGuard](http://proguard.sourceforge.net/) (или любой другой механизм сжатия или маскировки), классы Intune SDK должны быть исключены. Для ProGuard это можно сделать, включив правила из файла proguard.txt, входящего в состав пакета SDK.

Для библиотек ADAL могут быть предусмотрены собственные ограничения ProGuard. Если приложение включает ADAL, необходимо следовать инструкциям из документации по ADAL в отношении этих ограничений.

### <a name="entry-points"></a>Точки входа
======= Эти разрешения требуются библиотеке проверки подлинности Active Directory Azure ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) для проверки подлинности через посредника. Если эти разрешения приложению не предоставлены или отменены пользователем, проверка подлинности, для которой требуется посредник (приложение корпоративного портала), будет отключена.

Чтобы включить политики защиты приложений, пакету SDK для приложений Intune нужно внести изменения в исходный код приложения. Это осуществляется путем замены базовых классов Android на эквивалентные базовые классы Intune с префиксом **MAM**. Классы пакета SDK располагаются между базовым классом Android и производной версией этого класса в самом приложении. Используя действие в качестве примера, вы получаете иерархию наследования, которая выглядит следующим образом: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Например, если `AppSpecificActivity` взаимодействует со своим родительским элементом (например, вызывая `super.onCreate()`), `MAMActivity` является суперклассом.

Типичные приложения Android работают в одиночном режиме и обращаются к системе через свой объект [**Context**](https://developer.android.com/reference/android/content/Context.html). С другой стороны, приложения с внедренным пакетом SDK для приложений Intune работают в двойном режиме. Эти приложения по-прежнему получают доступ к системе через объект `Context`. В зависимости от используемого базового `Activity` объект `Context` будет предоставляться системой Android или будет интеллектуально мультиплексирован между ограниченным представлением системы и `Context`, предоставляемым системой Android.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Замена классов, методов и действий их эквивалентом MAM

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
| android.app.PendingIntent | MAMPendingIntent (см. примечания ниже) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (требуется, только если модуль привязки на основе интерфейса AIDL не создан) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Класс Android | Аналог в пакете SDK для приложений Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Класс Android | Аналог в пакете SDK для приложений Intune |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


### <a name="renamed-methods"></a>Переименованные методы
Унаследовав от одной из точек входа MAM, вы можете безопасно использовать `Context` обычным образом, например создавая `Activity` классы и используя `PackageManager`.

Часто метод, доступный в классе Android, отмечается как окончательный в замещающем классе MAM. В этом случае замещающий класс MAM предоставляет метод с таким же именем (обычно добавляется суффикс `MAM`), который должен быть переопределен вместо исходного. Например, при наследовании от `MAMActivity` вместо переопределения `onCreate()` и вызова `super.onCreate()` объекту `Activity` необходимо переопределить `onMAMCreate()` и вызвать `super.onMAMCreate()`. Компилятор Java должен налагать окончательные ограничения во избежание случайного переопределения исходного метода вместо его эквивалента MAM.

### <a name="pendingintent"></a>PendingIntent
Вместо `PendingIntent.get*` следует использовать метод `MAMPendingIntent.get*`. После этого можно использовать полученный `PendingIntent` обычным образом.

### <a name="manifest-replacements"></a>Замены в манифесте
Обратите внимание, что вам может потребоваться выполнить некоторые описанные выше замены класса в манифесте и коде Java. Примечание.
* Ссылки на манифест `android.support.v4.content.FileProvider` необходимо заменить `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.


## <a name="sdk-permissions"></a>Разрешения пакета SDK

Пакету SDK для приложений Intune требуются три [разрешения системы Android](https://developer.android.com/guide/topics/security/permissions.html) в отношении приложений, в которые он интегрируется:

* `android.permission.GET_ACCOUNTS` (запрашивается во время выполнения при необходимости)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Эти разрешения требуются библиотеке проверки подлинности Active Directory Azure ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) для проверки подлинности через посредника. Если эти разрешения приложению не предоставлены или отменены пользователем, проверка подлинности, для которой требуется посредник (приложение корпоративного портала), будет отключена.

## <a name="logging"></a>Logging

Чтобы получить максимальную пользу из регистрируемых данных, ведение журнала нужно инициализировать как можно раньше. Как правило, `Application.onMAMCreate()` — это наилучший вариант для инициализации ведения журнала.

Для получения журналов MAM в приложении, создайте [обработчик Java](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) и добавьте его в `MAMLogHandlerWrapper`. Это будет вызывать `publish()` в обработчике приложения для каждого сообщения журнала.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Включение функций, требующих содействия со стороны приложения

Есть несколько политик защиты приложений, которые пакет SDK не может реализовать самостоятельно. Приложение может управлять своим поведением для выполнения этих функций, используя несколько интерфейсов API, которые находятся в указанном ниже интерфейсе `AppPolicy`.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
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

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` всегда будет возвращать политику приложений, отличную от NULL, даже если устройство или приложение не управляются Intune.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Пример. Определение необходимости использования ПИН-кода в приложении

Если в приложении есть соответствующий интерфейс, вы можете отключить необходимость ввода ПИН-кода, если ИТ-администратор настроил это в пакете SDK. Чтобы определить, развернул ли ИТ-администратор политику использования ПИН-кода в приложении для текущего пользователя, вызовите следующий метод:

```java
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Пример. Определение основного пользователя Intune

В дополнение к API-интерфейсам, предоставляемых в AppPolicy, имя участника-пользователя (**UPN**) также предоставляется API `getPrimaryUser()`, определенным в интерфейсе `MAMUserInfo`. Чтобы получить имя участника-пользователя, вызовите следующее:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

Полное определение интерфейса MAMUserInfo приведено ниже:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Пример. Определение разрешения на сохранение данных на устройстве или в облачном хранилище

Во многих приложениях реализованы функции, позволяющие конечным пользователям сохранять файлы локально или в облачном хранилище. Пакет SDK для приложений Intune позволяет ИТ-администраторам защититься от утечки данных за счет применения ограничений политик, уместных для их организации.  Одной из политик, которой может управлять администратор, является возможность конечного пользователя сохранять данные в личном хранилище. Сюда входит сохранение в локальной папке, на SD-карте или в сторонних службах резервного копирования.

**Для включения этой функции требуется содействие со стороны приложения.** Если приложение позволяет сохранять данные в личное или облачное расположение непосредственно из приложения, необходимо реализовать эту функцию, чтобы предоставить ИТ-администратору возможность разрешать сохранение в расположение. Указанные ниже API позволяют приложению узнать, разрешено ли в текущей политике администрирования Intune сохранение в личном хранилище. После этого приложение может применить политику, так как ему известно о том, что хранилище личных данных доступно конечному пользователю через это приложение.  

Чтобы определить, применяется ли политика, выполните следующий вызов:

```java
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

Где `service` может иметь одно из следующих значений SaveLocations:


    * SaveLocation.ONEDRIVE_FOR_BUSINESS
    * SaveLocation.LOCAL
    * SaveLocation.OTHER

Предыдущий метод, с помощью которого можно определить, разрешает ли пользовательская политика сохранять данные в разных расположениях, представлен `getIsSaveToPersonalAllowed()` в рамках того же класса **AppPolicy**. Эта функция сейчас является **устаревшей** и не должна больше использоваться; следующий вызов эквивалентен `getIsSaveToPersonalAllowed()`:

```java

MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Используйте `SaveLocation.OTHER`, если рассматриваемое расположение не включено в перечисление **SaveLocations**.


## <a name="register-for-notifications-from-the-sdk"></a>Регистрация для получения уведомлений из пакета SDK

### <a name="overview"></a>Обзор
Пакет SDK для приложений Intune позволяет приложению управлять поведением определенных политик, включая политики выборочной очистки, развернутых ИТ-администратором. Когда ИТ-администратор развертывает такую политику, служба Intune отправляет уведомление пакету SDK.

Ваше приложение следует зарегистрировать для получения уведомлений из пакета SDK. Для этого нужно создать класс `MAMNotificationReceiver` и зарегистрировать его с помощью `MAMNotificationReceiverRegistry`. Для этого укажите получателя, а также тип необходимых уведомлений в `App.onCreate`, как показано в следующем примере:

```java
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
        .registerReceiver(
            new ToastNotificationReceiver(),
            MAMNotificationType.WIPE_USER_DATA);
    }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

Интерфейс `MAMNotificationReceiver` просто получает уведомления из службы Intune. Некоторые уведомления обрабатываются непосредственно пакетом SDK, другие требуют участия со стороны приложения. Приложение **должно** возвращать для уведомления значение true или false. Оно должно всегда возвращать значение true, за исключением случаев, когда какое-либо действие, которое приложение пыталось выполнить в результате уведомления, завершилось со сбоем.

* Этот сбой может быть зарегистрирован в службе Intune. Подобная ситуация может возникнуть, например, в случае, если приложение не смогло очистить данные пользователя после того, как ИТ-администратор запустил очистку.

>[!NOTE]
> Можно безопасно осуществить блокировку в `MAMNotificationReceiver.onReceive`, так как его обратный вызов не выполняется в потоке пользовательского интерфейса.

Интерфейс `MAMNotificationReceiver`, как определено в пакете SDK, включен ниже:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
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

### <a name="types-of-notifications"></a>Типы уведомлений

Следующие уведомления отправляются в приложение, и некоторые из них могут потребовать содействия со стороны приложения:

* **WIPE_USER_DATA**: это уведомление отправляется в классе `MAMUserNotification`. При получении этого уведомления приложение должно удалить все данные, связанные с корпоративным удостоверением, переданным с классом `MAMUserNotification`. Сейчас это уведомление отправляется при отмене регистрации службы APP-WE. Первичное имя пользователя обычно указывается во время регистрации. В случае регистрации для этого уведомления приложению необходимо убедиться, что все данные пользователя удалены. Если регистрация для него не выполняется, применяется поведение выборочной очистки по умолчанию.

* **WIPE_USER_AUXILIARY_DATA**: приложения можно регистрировать для этого уведомления, если необходимо, чтобы пакет SDK для приложений Intune выполнял выборочную очистку по умолчанию, удаляя некоторые дополнительные данные.

* **REFRESH_POLICY**: это уведомление отправляется в классе `MAMUserNotification`. При получении этого уведомления все кэшированные политики Intune должны быть признаны недействительными и обновлены. Обычно это осуществляется пакетом SDK, однако это может сделать и приложение, если политика имеет сохраняемый характер.

* **MANAGEMENT_REMOVED**: это уведомление отправляется в `MAMUserNotification`. Оно сообщает приложению о переходе в неуправляемое состояние. Перейдя в неуправляемое состояние, приложение больше не сможет читать зашифрованные файлы и данные, зашифрованные с использованием MAMDataProtectionManager, а также взаимодействовать с зашифрованным буфером обмена или состоять в экосистеме управляемого приложения.


> [!NOTE]
> Одновременно регистрировать приложение для получения уведомлений `WIPE_USER_DATA` и `WIPE_USER_AUXILIARY_DATA` нельзя.


## <a name="configure-azure-active-directory-authentication-library-adal"></a>Настройка библиотеки проверки подлинности Azure Active Directory (ADAL)

Во-первых, следует ознакомиться с рекомендациями по интеграции ADAL, доступными в [репозитории ADAL в GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).

Для [аутентификации](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/) пакет SDK использует библиотеки [ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/) и сценарии условного запуска. Для этого в приложении должна быть определенная конфигурация [Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/). Значения конфигурации передаются в пакет SDK с метаданными AndroidManifest.

Чтобы настроить приложение и включить надлежащий тип аутентификации, добавьте следующий код в узел приложения в AndroidManifest.xml. Некоторые из этих конфигураций нужны, только если приложение использует библиотеку ADAL для общей аутентификации. В этом случае вам потребуются эти конкретные значения, используемые вашим приложением для регистрации в AAD. Это позволяет предотвратить ситуацию, когда пользователь получает два запроса на аутентификацию, так как AAD распознает два отдельных значения регистрации: одно из приложения и одно из пакета SDK.

```xml
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
```

### <a name="adal-metadata"></a>Метаданные ADAL

* **Authority** — это текущий используемый центр AAD. Сейчас вам нужно использовать свою среду, в которой настроены учетные записи AAD. Если это значение отсутствует, используется значение по умолчанию для Intune.

* **ClientID** — это используемый идентификатор ClientID AAD. Вам нужно использовать идентификатор ClientID своего приложения, если оно зарегистрировано в Azure AD. Если это значение отсутствует, используется значение по умолчанию для Intune.

* **NonBrokerRedirectURI** — это URI перенаправления AAD, используемый в ситуациях без брокера. Если это значение не указано, используется стандартное значение `urn:ietf:wg:oauth:2.0:oob`. Это значение подходит для большинства приложений.

* **SkipBroker** используется, если идентификатор ClientID не настроен для использования URI перенаправления брокера. Значение по умолчанию — false.
    * Для приложений, которые **не включают ADAL** и **не будут участвовать в процедурах аутентификации и единого входа с помощью брокера на уровне устройства**, это свойство должно иметь значение true. Когда это значение равно true, будет использоваться только URI перенаправления NonBrokerRedirectURI.

    * Для приложений, которые поддерживают процедуру единого входа с помощью брокера на уровне устройства, это свойство должно иметь значение false. При значении false пакет SDK выберет брокера между результатом [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) и NonBrokerRedirectURI, учитывая доступность брокера в системе. В общем случае брокер будет доступен из приложения корпоративного портала или приложения аутентификации Azure.

### <a name="common-adal-configurations"></a>Распространенные конфигурации ADAL

Ниже приведены стандартные способы настройки приложения с использованием ADAL. Определите конфигурацию приложения и присвойте параметрам метаданных ADAL (см. выше) необходимые значения.

1. **Приложение не интегрируется с ADAL**

    | Обязательный параметр ADAL | Значение |
    |--|--|
    | Authority | Желаемая среда, в которой настроены учетные записи AAD. |
    | SkipBroker | True |

2. **Приложение интегрируется с ADAL**

    |Обязательный параметр ADAL| Значение |
    |--|--|
    | Authority | Желаемая среда, в которой настроены учетные записи AAD. |
    | ClientID | Идентификатор ClientID приложения (созданный в Azure AD при регистрации приложения). |
    | NonBrokerRedirectURI | Допустимый URI перенаправления для приложения или стандартное значение `urn:ietf:wg:oauth:2.0:oob`. <br><br> Значение должно быть определено как допустимый URI перенаправления для идентификатора ClientID приложения.
    | SkipBroker | False |


3. **Приложение включает ADAL, но не поддерживает аутентификацию и единый вход с помощью брокера на уровне устройства**

    |Обязательный параметр ADAL| Значение |
    |--|--|
    | Authority | Желаемая среда, в которой настроены учетные записи AAD. |
    | ClientID | Идентификатор ClientID приложения (созданный в Azure AD при регистрации приложения). |
    | NonBrokerRedirectURI | Допустимый URI перенаправления для приложения или стандартное значение `urn:ietf:wg:oauth:2.0:oob`. <br><br> Значение должно быть определено как допустимый URI перенаправления для идентификатора ClientID приложения.
    | SkipBroker | **True** |

## <a name="app-protection-policy-without-device-enrollment"></a>Политика защиты приложений без регистрации устройства

### <a name="overview"></a>Обзор
Политика защиты приложений без регистрации устройств Intune, также известная как APP-WE или MAM-WE, позволяет управлять приложениями с помощью Intune без необходимости регистрации устройств в Intune MDM. APP-WE работает с регистрацией устройств и без нее. Корпоративный портал по-прежнему должен быть установлен на устройстве, но пользователю не нужно входить на портал компании и регистрировать это устройство.

> [!NOTE]
> Все приложения должны поддерживать политику защиты приложений без регистрации устройства.

### <a name="workflow"></a>Рабочий процесс

Когда приложение создает учетную запись пользователя, оно должно зарегистрировать учетную запись для управления с использованием пакета SDK для приложений Intune. Пакет SDK будет обрабатывать сведения о регистрации приложения в службе APP-WE. В случае ошибки процесс регистрации повторится через определенные промежутки времени.

Приложение также может обратиться к пакету SDK для приложений Intune, запросив статус зарегистрированного пользователя. Это нужно, чтобы определить, будет ли пользователю заблокирован доступ к корпоративному содержимому. Хотя для управления можно зарегистрировать несколько учетных записей, одновременно зарегистрировать с использованием службы APP-WE можно только одну учетную запись. Это означает, что политика защиты приложения может одновременно применяться только к одной учетной записи в приложении.

Для приложения необходимо выполнить обратный вызов, чтобы получить маркер доступа из библиотеки ADAL от имени пакета SDK. Предполагается, что приложение уже использует ADAL для аутентификации пользователей и получения маркеров доступа.

Для учетной записи, полностью удаляемой приложением, необходимо отменить регистрацию. Так приложение больше не будет применять политику для этого пользователя. Для зарегистрированного в службе MAM пользователя регистрация будет отменена, а приложение будет очищено.


### <a name="overview-of-app-requirements"></a>Обзор требований приложения

Чтобы реализовать интеграцию APP-WE, приложение должно зарегистрировать учетную запись пользователя с помощью пакета SDK для MAM:

1. Приложение _должно_ реализовать и зарегистрировать экземпляр интерфейса `MAMServiceAuthenticationCallback`. Экземпляр обратного вызова должен быть зарегистрирован как можно раньше в жизненном цикле приложения (обычно в методе `onMAMCreate()` класса приложения).

2. Когда учетная запись пользователя будет создана, а сам пользователь войдет с использованием ADAL, приложение _должно_ вызвать `registerAccountForMAM()`.

3. Когда учетная запись пользователя полностью удаляется, приложение должно вызвать `unregisterAccountForMAM()`, чтобы удалить учетную запись из системы управления Intune.

    > [!NOTE]
    > Если пользователь временно выходит из приложения, приложению не нужно вызывать `unregisterAccountForMAM()`. Вызов может инициировать очистку для полного удаления корпоративных данных для пользователя.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Все необходимые процедуры аутентификации и регистрации API-интерфейсов можно найти в интерфейсе `MAMEnrollmentManager`. Ссылку на `MAMEnrollmentManager` можно получить так:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

Возвращаемый экземпляр `MAMEnrollmentManager` гарантированно не будет иметь нулевое значение. Методы API можно разделить на две категории: **аутентификация** и **регистрация учетной записи**.

> [!NOTE]
> `MAMEnrollmentManager` содержит некоторые методы API, которые скоро станут устаревшими. Для ясности в блоке кода ниже отображаются только соответствующие методы и коды результатов.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Аутентификация учетной записи

В этом разделе описываются методы аутентификации API в `MAMEnrollmentManager` и способы их использования.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Приложение должно реализовать интерфейс `MAMServiceAuthenticationCallback`, позволяющий пакету SDK запрашивать маркер ADAL для определенного пользователя и идентификатора ресурсов. Экземпляр обратного вызова должен предоставляться `MAMEnrollmentManager` при вызове его метода `registerAuthenticationCallback()`. Маркер может понадобится очень рано в жизненном цикле приложения для повторных попыток регистрации или проверок обновления политики защиты приложений. Поэтому лучше всего регистрировать обратный вызов в методе `onMAMCreate()` подкласса `MAMApplication` приложения.

2. Метод `acquireToken()` должен получить маркер доступа для запрошенного идентификатора ресурса для определенного пользователя. Если он не может получить запрошенный маркер, должно быть возвращено нулевое значение.

3. Если приложению не удается предоставить маркер, когда пакет SDK вызывает `acquireToken()` (например, если происходит сбой автоматической аутентификации, и это несвоевременно для отображения пользовательского интерфейса), приложение может сделать это позже, вызвав метод `updateToken()`. Запрошенные предыдущим вызовом `acquireToken()` идентификаторы имени участника-пользователя, AAD и ресурсов должны быть переданы `updateToken()` вместе с полученным маркером. Приложение, получившее нулевое значение из предоставленного обратного вызова, должно вызвать этот метод как можно быстрее.

> [!NOTE]
> Пакет SDK будет периодически вызывать `acquireToken()`, чтобы получить маркер, поэтому вызов `updateToken()` не является обязательным. Тем не менее это рекомендуемая процедура, которая помогает своевременно завершить проверки регистрации и применения политики защиты приложений.


### <a name="account-registration"></a>Регистрация учетной записи

В этом разделе описываются методы регистрации API в `MAMEnrollmentManager` и способы их использования.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Чтобы зарегистрировать учетную запись для управления, приложение должно вызвать `registerAccountForMAM()`. Учетная запись пользователя идентифицируется по его имени участника-пользователя и идентификатора пользователя AAD. Идентификатор клиента также требуется для связывания данных регистрации с пользовательским клиентом AAD. Пакет SDK может попытаться зарегистрировать приложение для определенного пользователя в службе MAM. В случае сбоя регистрации он будет периодически повторять эту процедуру, пока регистрация учетной записи не будет отменена. Интервал повторных попыток обычно составляет 12–24 ч. Пакет SDK предоставляет сведения о состоянии попыток регистрации асинхронно с помощью уведомлений.

2. Так как аутентификация AAD обязательна, лучше всего регистрировать учетную запись после того, как пользователь вошел в приложение и прошел аутентификацию с использованием ADAL.
    * Идентификатор пользователя AAD и идентификатор клиента возвращаются из вызова аутентификации ADAL как часть объекта [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android). Идентификатор клиента предоставляется из метода `AuthenticationResult.getTenantID()`.
    * Сведения о пользователе находятся в дочернем объекте типа `UserInfo`, который предоставляется вместе с `AuthenticationResult.getUserInfo()`, а идентификатор пользователя AAD извлекается из этого объекта при вызове `UserInfo.getUserId()`.

3. Чтобы отменить регистрацию учетной записи в системе управления Intune, приложение должно вызвать `unregisterAccountForMAM()`. Если учетная запись зарегистрирована и является управляемой, пакет SDK отменит ее регистрацию и очистит связанные данные. Периодические повторные попытки регистрации учетной записи будут остановлены. Пакет SDK предоставляет сведения о состоянии запроса на отмену регистрации асинхронно с помощью уведомлений.

### <a name="important-implementation-notes"></a>Примечания, связанные с реализацией

#### <a name="authentication"></a>Проверка подлинности

* Когда приложение вызывает метод `registerAccountForMAM()`, вскоре после этого оно может получить обратный вызов в своем интерфейсе `MAMServiceAuthenticationCallback` в другом потоке. В идеале приложение получает собственный маркер из ADAL до регистрации учетной записи для ускорения процесса получения **маркера MAMService**. Если приложение возвращает действительный маркер из обратного вызова, регистрация продолжится, и приложение получит результат в уведомлении.

* Если приложение не возвращает допустимый токен AAD, результатом попытки регистрации будет `AUTHENTICATION_NEEDED`. Если приложение получает этот результат в уведомлении, процесс регистрации может быть ускорен. Для этого создается запрос **маркера MAMService** и осуществляется вызов метода `updateToken()`, что снова инициирует процесс регистрации. Но это _не_ является жестким требованием, так как пакет SDK периодически повторяет попытку регистрации и выполняет обратный вызов для получения маркера.

* Зарегистрированные `MAMServiceAuthenticationCallback` приложения также будут вызываться для получения маркера для периодической проверки обновления политики защиты приложений. Если приложению не удается предоставить маркер при запросе, оно не получит уведомление. Такое приложение должно попытаться получить маркер и вызвать `updateToken()` в удобное для этого время, чтобы ускорить процесс проверки. Если маркер не предоставлен, обратный вызов будет осуществляться при следующей попытке.

#### <a name="registration"></a>Регистрация

* Для удобства методы регистрации являются идемпотентными. Например, `registerAccountForMAM()` только зарегистрирует учетную запись и попытается зарегистрировать приложение, если учетная запись еще не зарегистрирована, а `unregisterAccountForMAM()` только отменит регистрацию учетной записи, если она уже зарегистрирована. Последующие вызовы не являются операциями, поэтому эти методы можно вызывать многократно. Кроме того, не гарантируется ни соответствие между вызовами этих методов, ни отправка уведомлений о результатах. То есть если `registerAccountForMAM` вызывается для удостоверения, которое уже зарегистрировано, уведомление для этого удостоверения может больше не отправляться. Вполне возможно, что отправленные уведомления просто не соответствуют вызовам этих методов, так как пакет SDK может периодически повторять попытки регистрации в фоновом режиме, а отмена регистрации может инициироваться запросами на очистку, полученными от службы Intune.

* Методы регистрации могут вызываться для любого числа различных удостоверений, но сейчас зарегистрировать можно только одну учетную запись пользователя. Если одновременно (или почти одновременно) регистрируется несколько учетных записей, лицензированных для использования Intune и предназначенных для применения политики защиты приложения, нельзя предсказать, какая из этих учетных записей будет в итоге зарегистрирована.

* В итоге вы можете выполнить запрос `MAMEnrollmentManager`, чтобы узнать, зарегистрирована ли определенная учетная запись, и получить сведения о ее текущем состоянии с помощью метода `getRegisteredAccountStatus`. Если предоставленная учетная запись не зарегистрирована, этот метод вернет значение **null**. Если учетная запись зарегистрирована, этот метод вернет состояние учетной записи как одного из членов перечисления `MAMEnrollmentManager.Result`.

### <a name="result-and-status-codes"></a>Коды результатов и состояния

При первой регистрации учетной записи она находится в состоянии `PENDING`. Это состояние указывает на то, что первоначальная попытка регистрации службы MAM не завершена. Когда попытка регистрации будет завершена, будет отправлено уведомление с одним из кодов результатов, перечисленных в таблице ниже. Кроме того, метод `getRegisteredAccountStatus()` вернет состояние учетной записи. Так приложение всегда сможет определить, заблокирован ли доступ к корпоративному содержимому для этого пользователя. Если попытка регистрации учетной записи не удается, состояние учетной записи может меняться по мере того, как пакет SDK будет совершать попытки регистрации в фоновом режиме.

|Код результата | Описание |
| -- | -- |
|AUTHORIZATION_NEEDED | Этот результат показывает, что токен не предоставлен зарегистрированным экземпляром `MAMServiceAuthenticationCallback` приложения или предоставленный токен недопустимый.  Приложение должно получить действительный маркер и вызвать метод `updateToken()`, если это возможно. |
| NOT_LICENSED | Пользователь не лицензирован для использования Intune или не удалось связаться со службой Intune MAM.  Приложение должно продолжать работу в неуправляемом (обычном) состоянии, а пользователь не должен быть заблокирован.  Попытки регистрации будут периодически повторяться, если у пользователя в будущем появится лицензия . |
| ENROLLMENT_SUCCEEDED | Попытка регистрации выполнена или пользователь уже зарегистрирован.  В случае успешной регистрации уведомление об обновлении политики будет отправлено до отправки этого уведомления.  Должен быть разрешен доступ к корпоративным данным. |
| ENROLLMENT_FAILED | Попытка регистрации не удалась.  Дополнительные сведения см. в журналах устройства.  Приложение в этом состоянии не должно разрешать доступ к корпоративным данным, так как ранее обнаружено, что у пользователя есть лицензия для использования Intune.|
| WRONG_USER | Только один пользователь устройства может зарегистрировать приложение с использованием службы MAM.  Для успешной регистрации от имени другого пользователя для всех зарегистрированных приложений сначала следует отменить регистрацию.  В противном случае это приложение необходимо зарегистрировать в качестве основного пользователя.  Такая проверка проводится после проверки лицензии, поэтому доступ пользователя к корпоративным данным будет заблокирован, пока приложение не будет зарегистрировано.|
| UNENROLLMENT_SUCCEEDED | Отмена регистрации выполнена.|
| UNENROLLMENT_FAILED | Отмена регистрации не удалась.  Дополнительные сведения см. в журналах устройства. |
| PENDING | Идет попытка первоначальной регистрации для пользователя.  Приложение может заблокировать доступ к корпоративным данным, пока не станет известен результат регистрации, но это не обязательно. |
| COMPANY_PORTAL_REQUIRED | У пользователя есть лицензия на использование Intune, но приложение нельзя зарегистрировать до установки приложения корпоративного портала на устройстве. Пакет SDK для приложений Intune попытается заблокировать доступ к приложению для определенного пользователя, предлагая установить приложение корпоративного портала (см. ниже). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Переопределение строки запроса для требований корпоративного портала (необязательно)

Если получен результат `COMPANY_PORTAL_REQUIRED`, пакет SDK будет блокировать действия, использующие удостоверение, для которого запрошена регистрация. Вместо этого пакет SDK вызовет для этих действий отображение строки запроса на скачивание корпоративного портала. Чтобы предотвратить такое поведение в приложении, действия могут реализовать `MAMActivity.onMAMCompanyPortalRequired`.

Этот метод вызывается до того, как пакет SDK отобразит стандартный пользовательский интерфейс блокировки. Если приложение изменяет удостоверение действия или отменяет регистрацию пользователя, пытающегося зарегистрироваться, пакет SDK не будет блокировать действия. В этом случае приложение отвечает за предотвращение утечки корпоративных данных.

### <a name="notifications"></a>Уведомления

Новый тип `MAMNotification` добавлен, чтобы оповещать приложение о выполнении запроса на регистрацию приложения.  `MAMEnrollmentNotification` будет получен через интерфейс `MAMNotificationReceiver`, как описано в разделе [Регистрация для получения уведомлений из пакета SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

Метод `getEnrollmentResult()` возвращает результат запроса на регистрацию.  Так как `MAMEnrollmentNotification` расширяет `MAMUserNotification`, также будет доступно удостоверение пользователя, для которого выполнена попытка регистрации. Приложение должно реализовать интерфейс `MAMNotificationReceiver` для получения этих уведомлений. Дополнительные сведения см. в разделе [Регистрация для получения уведомлений из пакета SDK](#Register-for-notifications-from-the-SDK).

Состояние учетной записи зарегистрированного пользователя может измениться при получении уведомления о регистрации, но в некоторых случаях это не происходит. Например, если уведомление `AUTHORIZATION_NEEDED` будет получено после возврата более информативного результата (`WRONG_USER`), такой результат будет использоваться в качестве состояния учетной записи.


## <a name="protecting-backup-data"></a>Защита данных резервной копии

Начиная с Android Marshmallow (API 23), система Android предоставляет два способа резервного копирования данных приложением. Каждый вариант доступен в приложении и требует разных действий для правильного обеспечения защиты данных Intune. Действия, необходимые для защиты данных, указаны в приведенной ниже таблице.  Дополнительные сведения о способах резервного копирования см. в [справочнике по API Android](http://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Автоматическое резервное копирование для приложений

Начиная с устройств Android Marshmallow, система Android начала предлагать [автоматическое полное резервное копирование](https://developer.android.com/guide/topics/data/autobackup.html) приложений Диска Google независимо от целевого API. Если в файле AndroidManifest.xml задать для атрибута `android:allowBackup` значение **false**, Android не будет добавлять приложение в очереди на резервное копирование, а корпоративные данные останутся в приложении. В этом случае никаких дополнительных действий не требуется.

Однако по умолчанию атрибут `android:allowBackup` имеет значение true, даже если `android:allowBackup` не указан в файле манифеста. Это означает, что для всех приложений автоматически создаются резервные копии в учетной записи пользователя на диске Google, т. е. используется поведение по умолчанию, связанное с **риском утечки данных**. В связи с этим для защиты данных в пакет SDK необходимо внести описанные ниже изменения.  Если вы хотите, чтобы ваше приложение работало на устройствах Android Marshmallow, выполните представленные ниже рекомендации по защите клиентских данных.  

Intune позволяет использовать все [функции автоматической архивации](https://developer.android.com/guide/topics/data/autobackup.html), доступные в системе Android, включая возможность настройки правил в формате XML, однако для защиты данных необходимо выполнить следующие действия:

1. Если приложение **не** использует собственный агент BackupAgent, разрешите полное автоматическое резервное копирование, соответствующее политике Intune, с помощью MAMBackupAgent по умолчанию. После этого можно игнорировать атрибут манифеста `android:fullBackupOnly`, так как он не применим для нашего агента резервного копирования. В манифесте приложения должно быть следующее:

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```

2. **[Необязательно]** Если реализуется необязательный пользовательский агент BackupAgent, необходимо использовать MAMBackupAgent или MAMBackupAgentHelper. См. следующие разделы. Рассмотрите возможность использования агента Intune **MAMDefaultFullBackupAgent** (см. шаг 1), который обеспечивает простое и удобное резервное копирование в Android версии M и выше.

3. Выберите тип полного резервного копирования для своего приложения (без фильтра, с фильтром или нет), задав для атрибута `android:fullBackupContent` значение true или false либо указав XML-ресурс в своем приложении.

4. Затем вы _**должны**_ скопировать все, что необходимо вставить в атрибут `android:fullBackupContent`, в тег метаданных с именем `com.microsoft.intune.mam.FullBackupContent`.

    **Пример 1.** Если приложение должно иметь полные резервные копии без исключений, присвойте атрибуту `android:fullBackupContent` и тегу метаданных `com.microsoft.intune.mam.FullBackupContent` значение **true**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Пример 2.** Если приложение должно использовать пользовательский агент BackupAgent, не прибегая к полному и совместимому с политиками Intune автоматическому резервному копированию, необходимо присвоить атрибуту и тегу метаданных значение **false**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Пример 3.** Если приложение должно иметь полные резервные копии в соответствии с пользовательскими правилами, определенными в XML-файле, укажите атрибут и тег метаданных в одном ресурсе XML:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Резервные копии "ключ-значение"

Параметр [Резервные копии "ключ-значение"](https://developer.android.com/guide/topics/data/keyvaluebackup.html) доступен для всех API-интерфейсов версии 8 и выше. Он позволяет передавать данные приложения в [службу резервного копирования Android](https://developer.android.com/google/backup/index.html). Объем данных для каждого пользователя приложения ограничивается 5 МБ. При использовании резервных копий "ключ-значение" необходимо использовать **BackupAgentHelper** или **BackupAgent**.

### <a name="backupagenthelper"></a>BackupAgentHelper

Реализовать BackupAgentHelper гораздо проще, чем BackupAgent. Это относится как к собственным функциям Android, так и к интеграции Intune MAM. BackupAgentHelper позволяет разработчику регистрировать целые файлы и общие настройки в **FileBackupHelper** или **SharedPreferencesBackupHelper** соответственно, которые затем добавляются в BackupAgentHelper при создании. Выполните следующие действия, чтобы использовать BackupAgentHelper с Intune MAM:

1. Для использования резервного копирования с множественной идентификацией с помощью BackupAgentHelper ознакомьтесь с руководством по [расширению BackupAgentHelper в Android](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).

2. Обеспечьте расширение класса эквивалента MAM для BackupAgentHelper, FileBackupHelper и SharedPreferencesBackupHelper.

|Класс Android | Эквивалент MAM |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Следуя этим рекомендациям, вы выполните резервное копирование и восстановление с множественной идентификацией.

### <a name="backupagent"></a>BackupAgent

Агент BackupAgent позволяет явно определить, какие именно данные следует копировать. Так как за реализацию отвечает разработчик, нужно выполнить дополнительные шаги для обеспечения защиты данных из Intune. Большая часть работы возложена на вас как разработчика, поэтому интеграция Intune играет более важную роль.

**Интеграция MAM**

1. Внимательно прочитайте руководство по [резервному копированию пар "ключ-значение" в Android](https://developer.android.com/guide/topics/data/keyvaluebackup.html), уделив особое внимание сведениям о [расширении BackupAgent ](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent). Так вы обеспечите соответствие вашей реализации BackupAgent рекомендациям Android.

2. Обеспечьте расширение класса `MAMBackupAgent`.

**Резервное копирование с множественной идентификацией**

1. Перед началом резервного копирования нужно определить, **разрешено ли ИТ-администратору создавать резервные копии** необходимых файлов или буферов данных в сценариях с использованием множественной идентификации. Для этого мы предоставляем функцию `isBackupAllowed` в `MAMFileProtectionManager` и `MAMDataProtectionManager`. Если для файла или буфера данных нельзя создавать резервную копию, вы не сможете использовать эти ресурсы в ходе резервного копирования.

2. Если в определенный момент во время резервного копирования вам нужно создать резервную копию удостоверений для файлов, проверенных на шаге 1, вызовите `backupMAMFileIdentity(BackupDataOutput data, File … files)` с файлами, из которых вы планируете извлекать данные. При этом автоматически создаются новые сущности резервного копирования, которые записываются в `BackupDataOutput` . Эти сущности будут автоматически использоваться при восстановлении.

**Восстановление с множественной идентификацией**

Руководство по резервному копированию данных определяет общий алгоритм для восстановления данных приложения и содержит пример кода в разделе о [расширении агента BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent). Для реализации успешного восстановления с множественной идентификацией вам нужно придерживаться общей структуры, представленной в примере кода. Также учтите следующее:

1.  Необходимо использовать цикл `while(data.readNextHeader())`*, чтобы проходить через резервные сущности.

2.  Необходимо вызвать `data.skipEntityData()`*, если `data.getKey()`* не соответствует ключу, созданному в `onBackup`. Без выполнения этого шага восстановление может завершиться ошибкой.

3.  Старайтесь не возвращать результат при использовании сущностей резервного копирования в конструкции `while(data.readNextHeader())`*, так как эти автоматически записываемые сущности будут утеряны.

* Где `data` — это имя локальной переменной для **BackupDataInput** (передается в приложение после восстановления).

## <a name="multi-identity-optional"></a>Использование нескольких удостоверений (необязательно)

### <a name="overview"></a>Обзор
По умолчанию пакет SDK для приложений Intune применяет политику для всего приложения. Множественная идентификация — это дополнительная функция защиты приложений Intune, которую можно включить, чтобы разрешить применять политики на уровне удостоверения. Для этого требуется намного больше действий со стороны приложения, чем при использовании других функций защиты приложений.

Приложение _должно_ информировать пакет SDK приложений о намерении изменить активное удостоверение, а пакет SDK, в свою очередь, будет уведомлять приложение о том, что удостоверение необходимо заменить. Когда приложение или устройство будет зарегистрировано пользователем, пакет SDK будет использовать это удостоверение, считая его основным управляемым удостоверением Intune. Другие пользователи в приложении будут рассматриваться как неуправляемые и не имеющие ограничений для параметров политик.

> [!NOTE]
> Сейчас поддерживается только одно управляемое удостоверение Intune на устройство.

Обратите внимание, что удостоверение определяется просто в виде строки. Удостоверения задаются **без учета регистра**, а запросы удостоверения, направляемые к пакету SDK, могут возвращать удостоверения с использованием другого регистра.


### <a name="enabling-multi-identity"></a>Включение множественной идентификации

По умолчанию все приложения считаются приложениями с одним удостоверением. Вы можете объявить для приложения поддержку множественной идентификации, добавив следующие метаданные в AndroidManifest.xml.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Задание удостоверения

Разработчики могут определять удостоверение пользователя приложения на следующих уровнях (в порядке убывания):

  1. Уровень потока.
  2. Уровень контекста (как правило, действия).
  3. Уровень процесса.

Удостоверение, определенное на уровне потока, заменяет удостоверение, определенное на уровне контекста, которое, в свою очередь, заменяет удостоверение, определенное на уровне процесса. Удостоверение, определенное на уровне контекста, используется только в соответствующих связанных сценариях. Операции ввода-вывода файлов, например, не имеют связанного контекста. Вы можете использовать следующие методы в `MAMPolicyManager`, чтобы определить удостоверение и получить значения удостоверений, определенные ранее.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
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

>[!NOTE]
> Удостоверение приложения можно сбросить, присвоив ему нулевое значение.
>
> В качестве удостоверения можно использовать пустую строку. В этом случае политики защиты приложений применяться больше не будут.

#### <a name="results"></a>Результаты
Все методы определения удостоверений возвращают соответствующие значения с помощью атрибута `MAMIdentitySwitchResult`. Возвращаться могут четыре значения:

| Возвращаемое значение | Сценарий |
|--|--|
| SUCCEEDED | Удостоверение изменено. |
| NOT_ALLOWED | Изменение удостоверения запрещено. <br><br>Это происходит при попытке переключиться на другого управляемого пользователя, который относится к той же организации, что и зарегистрированный пользователь. Это также происходит при попытке определить удостоверение на уровне пользовательского интерфейса (контекста), когда в текущем потоке указано другое удостоверение. |
| CANCELLED | Пользователь отменил изменение удостоверения (как правило, при нажатии кнопки возврата в запросе PIN-кода или аутентификации). |
| FAILED | Изменить удостоверение не удалось по неизвестной причине.|


Если удостоверение задается на уровне контекста, результаты передаются асинхронно. Если контекстом является действие, пакет SDK не сможет проверить изменение удостоверения, пока не будет выполнен условный запуск. Для этого пользователю может потребоваться ввести PIN-код или данные корпоративной учетной записи. Для получения этого результата приложение должно реализовать `MAMSetUIIdentityCallback`, хотя вы можете передать пустое значение для этого параметра.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Удостоверения на уровне действия можно также задать, не вызывая `MAMPolicyManager.setUIPolicyIdentity`, а с помощью метода в `MAMActivity`. Используйте для этого следующий метод:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

Приложения могут также переопределять метод в `MAMActivity`, чтобы получать уведомления о результатах попыток изменения удостоверений на уровне действия.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Для переключения удостоверения может потребоваться повторно создать действие. В этом случае обратный вызов `onSwitchMAMIdentityComplete` осуществляется в новый экземпляр действия.


### <a name="implicit-identity-changes"></a>Неявные изменения удостоверений

Определить удостоверение может не только приложение. Удостоверение на уровне потока или контекста может быть изменено с учетом данных, поступивших из другого приложения с поддержкой Intune, имеющего политику защиты приложений.

#### <a name="examples"></a>Примеры

  1. Если действие запускается из `Intent` при отправке другому приложению MAM, удостоверение этого действия определяется с учетом удостоверения, действующего в другом приложении на момент отправки `Intent`.

  2.  Для служб удостоверение на уровне потока определяется аналогично на время вызова метода `onStart` или `onBind`. Вызовы в `Binder`, возвращенные из `onBind`, также временно определяют удостоверение на уровне потока.

  3. Вызовы в `ContentProvider` задают удостоверение на уровне потока на время своего действия аналогичным образом.


  Кроме того, взаимодействие пользователя с действием может вызвать неявное переключение удостоверения.

  **Пример**. Если пользователь нажмет кнопку отмены в запросе на аутентификацию во время выполнения действия `Resume`, произойдет неявное переключение на пустое удостоверение.

  Приложение сможет узнавать о таких изменениях, а в некоторых случаях и запрещать их при необходимости. `MAMService` и `MAMContentProvider` предоставляют следующий метод, который подклассы могут переопределять:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  При использовании класса `MAMActivity` в метод добавляется еще один параметр:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * `AppIdentitySwitchReason` фиксирует источник неявного переключения и может принимать значения `CREATE`, `RESUME_CANCELLED` и `NEW_INTENT`.  Если действие Resume вызывает отображение запроса PIN-кода, проверки подлинности или других элементов пользовательского интерфейса, связанных с соответствием, а пользователь пытается их отменить (обычно используя кнопку возврата), используется причина `RESUME_CANCELLED`.


  * `AppIdentitySwitchResultCallback` выглядит так:

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    Где ```AppIdentitySwitchResult``` имеет значение SUCCESS или FAILURE.

Метод `onMAMIdentitySwitchRequired` вызывается для всех неявных изменений удостоверения, кроме связанных с возвратом средства привязки из `MAMService.onMAMBind`. Стандартные реализации `onMAMIdentitySwitchRequired` вызываются сразу же:

*  `reportIdentitySwitchResult(FAILURE)`, если причина — значение RESUME_CANCELLED.

*  `reportIdentitySwitchResult(SUCCESS)` — во всех остальных случаях.

  Предполагается, что большинству приложений не требуется блокировать или откладывать переключение удостоверений каким-либо другим образом. Но если это не так, следует принимать во внимание следующие моменты:

  * Если переключение удостоверения заблокировано, результат аналогичен случаю, когда параметры общего доступа `Receive` запрещают входящие данные.

  * Если служба работает в основном потоке, `reportIdentitySwitchResult` **необходимо** вызывать асинхронно, иначе пользовательский интерфейс может зависнуть.

  * Для создания **действия** параметр `onMAMIdentitySwitchRequired` будет вызываться до вызова метода `onMAMCreate`. Если приложение должно отображать интерфейс пользователя, чтобы определить, необходимо ли разрешить переключение удостоверения, интерфейс необходимо отображать, используя *другое* действие.

  * Если **действие** запрашивает переключение на пустое удостоверение из-за значения RESUME_CANCELLED, приложение должно изменить возобновленное действие, чтобы отобразить данные, связанные с переключением удостоверения.  Если это невозможно, приложение должно запретить переключение и отобразить повторный запрос для соблюдения политики в отношении возобновления удостоверения (например, вывести в приложении экран для ввода PIN-кода).

    > [!NOTE]
    > Приложение с несколькими удостоверениями всегда получает входящие данные как из управляемых, так и из неуправляемых приложений. Приложение должно обрабатывать данные из управляемых удостоверений управляемым образом.

  Если запрошенное удостоверение является управляемым (используйте `MAMPolicyManager.getIsIdentityManaged` для проверки), но приложение не может использовать эту учетную запись (например, потому, что учетные записи, такие как учетные записи электронной почты, должны быть сначала настроены в приложении), в переключении удостоверения будет отказано.



  ### <a name="file-protection"></a>Защита файлов

  При создании каждого файла к нему привязывается удостоверение потока или процесса. Оно будет использоваться и для шифрования файлов, и для выборочной очистки. Шифруются только те файлы, удостоверение которых управляется и имеет политику, которая требует шифрования. Функция выборочной очистки пакета SDK по умолчанию удаляет только файлы, связанные с управляемым удостоверением, для которого запрошена очистка. Приложение может запросить или изменить удостоверение файла с помощью класса `MAMFileProtectionManager`.

  ```java
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

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```

Удостоверение файла маркируется как чувствительное к автономному режиму. Необходимо учитывать следующее:

  * Если корпоративный портал не установлен, удостоверения файлов маркировать нельзя.

  * Если корпоративный портал установлен, но приложение не имеет политику Intune MAM, надежная маркировка удостоверений для файлов невозможна.

  * Если маркировка удостоверений файлов становится доступной, все созданные ранее файлы считаются личными или неуправляемыми (относящимися к удостоверению с пустой строкой). Но если приложение установлено как управляемое приложение с одним удостоверением, такие файлы будут считаться принадлежащими зарегистрированному пользователю.

### <a name="directory-protection"></a>Защита каталога

Каталоги можно защищать с помощью того же метода `protect`, используемого для защиты файлов. Обратите внимание, что защита каталога применяется рекурсивно для всех файлов и подкаталогов, содержащихся в каталоге, а также для новых файлов, создаваемых в каталоге. Так как защита каталога применяется рекурсивно, вызов `protect` может занять некоторое время для очень больших каталогов. По этой причине при применении защиты для каталога, который содержит большое число файлов приложения, может потребоваться асинхронный запуск `protect` в фоновом потоке.

### <a name="data-protection"></a>Защита данных

Маркировать файл как принадлежащий нескольким удостоверениям нельзя. Приложения, которые должны сохранять принадлежащие разным пользователям данные в один файл, могут делать это с помощью функций, предоставляемых `MAMDataProtectionManager`. Он позволяет приложению шифровать данные и привязывать их к определенному пользователю. Зашифрованные данные можно сохранять на диск в файле. Вы можете запросить связанные с удостоверением данные и зашифровать их позднее.

Приложение, использующее `MAMDataProtectionManager`, должно реализовать получатель для уведомления `MANAGEMENT_REMOVED`. Когда обработка этого уведомления будет выполнена, защищенные с помощью этого класса буферы больше не будут доступными для чтения, если в то время, когда буферы были защищены, было включено шифрование файлов. Приложение может решить эту проблему, вызвав MAMDataProtectionManager.unprotect для всех буферов при обработке этого уведомления. Обратите внимание, что вызывать защиту во время обработки этого уведомления также безопасно, если необходимо сохранить сведения об удостоверении. Во время обработки удостоверения шифрование гарантированно будет отключено.

```java

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

### <a name="content-providers"></a>Поставщики содержимого

Если приложение предоставляет корпоративные данные, отличные от **ParcelFileDescriptor** через **поставщик содержимого**, приложение должно вызвать метод `isProvideContentAllowed(String)` в `MAMContentProvider`, передав идентификатор владельца UPN (имя участника-пользователя) для содержимого. Если эта функция возвращает значение false, содержимое *не будет* возвращено вызывающему. Дескрипторы файлов, возвращенные с помощью поставщика содержимого, обрабатываются автоматически, исходя из удостоверения файла.

### <a name="selective-wipe"></a>выборочная очистка;

Если приложение регистрируется для получения уведомлений `WIPE_USER_DATA`, стандартная выборочная очистка, выполняемая пакетом SDK, будет для него недоступна. Для приложений с поддержкой множественной идентификации это может быть существенно, так как стандартная выборочная очистка MAM по умолчанию удаляет только файлы, удостоверение которых предполагает такую очистку.

Если для приложения с поддержкой множественной идентификации требуется стандартная выборочная очистка MAM, которая, тем не менее, должна выполняться _**самостоятельно**_, такое приложение необходимо зарегистрировать для использования уведомлений `WIPE_USER_AUXILIARY_DATA`. Такие уведомления будут отправляться пакетом SDK непосредственно перед выполнением стандартной выборочной очистки MAM. Приложение никогда не следует регистрировать для WIPE_USER_DATA и WIPE_USER_AUXILIARY_DATA.


## <a name="style-customization-optional"></a>Настройка стиля (необязательно)

Представления, созданные пакетом SDK для MAM, можно настроить для более точного визуального соответствия приложению, в которое они интегрированы. Можно настроить основной, дополнительный и фоновый цвета, а также размер эмблемы приложения. Эта настройка стиля является необязательной. Если ее не применять, будут использоваться стандартные параметры.


### <a name="how-to-customize"></a>Как выполнять настройку
Чтобы применить изменения стиля к представлениям Intune MAM, необходимо сначала создать XML-файл переопределения стиля. Этот файл необходимо поместить в каталог /res/xml приложения, присвоив ему любое имя. Ниже приведен пример формата, которому должен соответствовать этот файл.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

Необходимо повторно использовать уже существующие в приложении ресурсы. Например, вам нужно определить зеленый цвет в файле colors.xml, сославшись на него здесь. Нельзя использовать шестнадцатеричный код цвета #0000ff. Максимальный размер эмблемы приложения составляет 110 DIP-пикселей. Можно использовать эмблему и меньшего размера. Но применив максимально возможное значение, вы получите более качественное изображение. При превышении лимита в 110 DIP-пикселей изображение будет уменьшено и, возможно, размыто.

Ниже приведен полный список разрешенных атрибутов стиля, управляемых ими элементов пользовательского интерфейса, имена элементов XML-атрибутов и ожидаемые типы ресурса.

|Атрибут стиля | Затронутые элементы пользовательского интерфейса | Имя элемента атрибута | Ожидаемый тип ресурса |
| -- | -- | -- | -- |
| Цвет фона | Цвет фона для экрана ПИН-кода <Br>Цвет заливки для поля ПИН-кода | background_color | Цвет |
| Цвет переднего плана | Цвет текста переднего плана <br> Граница поля ПИН-кода в стандартном состоянии <br> Символы (включая скрытые символы) в поле ПИН-кода, когда пользователь вводит ПИН-код| foreground_color | Цвет|
| Цвет элементов | Граница поля ПИН-кода при выделении <br> Гиперссылки |accent_color | Цвет |
| Эмблема приложения | Большой значок, отображаемый на экране ПИН-кода в приложении Intune | logo_image | Рисунки |

## <a name="limitations"></a>Ограничения

### <a name="file-size-limitations"></a>Ограничения на размер файла

Ограничения формата исполняемого файла Dalvik могут вызывать проблемы для больших баз кода, работающих без [ProGuard](http://proguard.sourceforge.net/). В частности, могут применяться следующие ограничения:

1.  Предел в 65 тысяч для полей.
2.  Предел в 65 тысяч для методов.



### <a name="policy-enforcement-limitations"></a>Ограничения применения политики

* **Снимок экрана**: пакет SDK не может применить новое значение параметра для снимка экрана в действиях, которые уже прошли через Activity.onCreate. Это может привести к тому, что в течение определенного времени, когда приложение настроено на отключение снимков экрана, снимки экрана по-прежнему могут создаваться.

* **Использование сопоставителей содержимого**. В Intune политика передачи или получения может полностью или частично блокировать использование сопоставителя содержимого для доступа к поставщику содержимого в другом приложении. Это приводит к тому, что методы ContentResolver возвращают значение NULL или выдают значение сбоя (например, при блокировке `openOutputStream` выдает исключение `FileNotFoundException` ). Приложение может определить, вызван ли (и может ли быть вызван) сбой записи данных через сопоставитель политики, выполнив вызов:

    ```java
    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI);
    ```

### <a name="exported-services"></a>Экспортированные службы

 Файл AndroidManifest.xml, входящий в состав пакета SDK для приложений Intune, содержит объект **MAMNotificationReceiverService**, который должен быть экспортированной службой, чтобы разрешить корпоративному порталу отправлять уведомления в приложение с расширенными возможностями. Служба проверяет вызывающий объект, чтобы убедиться, что корпоративный портал может отправлять уведомления.



## <a name="expectations-of-the-sdk-consumer"></a>Ожидания потребителя пакета SDK

Пакет SDK Intune поддерживает контракт, предоставляемый API Android, хотя состояния сбоя могут возникать чаще в результате применения политики. Эти рекомендации для Android позволяют снизить вероятность сбоя:

* Функции пакета SDK для Android, которые могут возвращать значение NULL, теперь с большей вероятностью равны NULL.  Чтобы свести число возникающих проблем к минимуму, обеспечьте наличие проверок значений NULL в нужных местах.

* Функции, которые могут быть проверены, следует проверять с использованием их API-интерфейсов замены MAM.

* Любые производные функции следует вызвать через их версии суперкласса.

* Избегайте неоднозначного использования любых API. Например, использование `Activity.startActivityForResult` без проверки requestCode вызовет нестандартное поведение.

## <a name="recommended-android-best-practices"></a>Рекомендации для Android

* Все проекты библиотеки должны по мере возможности совместно использовать один и тот же android:package. Это не приведет к эпизодическим сбоям в среде выполнения, так как проблема возникает исключительно при сборке. Более новые версии пакета SDK приложений Intune устранят некоторую избыточность.

* Используйте самые новые средства сборки пакета SDK для Android.

* Удалите все ненужные и неиспользуемые библиотеки (например, android.support.v4).

