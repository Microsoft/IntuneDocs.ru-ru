---
title: Привязки Xamarin из пакета SDK для приложений Microsoft Intune
description: Привязки Xamarin из пакета SDK для приложений Intune позволяют использовать политику защиты приложений Intune в приложениях iOS и Android, созданных с помощью Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd162f6af256c104c04374290a695141cdcc26f6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566205"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Привязки Xamarin из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.

## <a name="overview"></a>Обзор
[Привязки Xamarin из пакета SDK для приложений Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) позволяют использовать [политику защиты приложений Intune](app-protection-policy.md) в приложениях iOS и Android, созданных с помощью Xamarin. Привязки разрешают разработчикам легко встраивать в свои приложения на базе Xamarin функции защиты приложений Intune.

Привязки Xamarin из пакета SDK для приложений Microsoft Intune позволяют встраивать в приложения, разработанные с помощью Xamarin, политики защиты приложений Intune, также известные как политики защиты приложений или политики управления мобильными приложениями. В приложение, которое использует MAM, встроен пакет SDK для приложений Intune. ИТ-администраторы могут развернуть политики защиты приложений в вашем мобильном приложении, когда Intune активно управляет им.

## <a name="whats-supported"></a>Поддерживаемые возможности

### <a name="developer-machines"></a>Компьютеры разработчиков
* Windows (версия Visual Studio 15.7 и более поздние)
* macOS

### <a name="mobile-app-platforms"></a>Платформы мобильных приложений
* Android
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Ситуации, связанные с управлением мобильными приложениями Intune

* Intune APP-WE (без регистрации устройства)
* Устройства, зарегистрированные в Intune MDM
* Сторонние устройства, зарегистрированные в EMM

Приложения Xamarin, созданные с помощью привязок Xamarin из пакета SDK для приложений Intune, теперь могут получать политики защиты приложений Intune как на устройствах, зарегистрированных в системе управления мобильными устройствами (MDM) Intune, так и на незарегистрированных устройствах.

## <a name="prerequisites"></a>Предварительные условия

Прочтите [условия лицензионного соглашения](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Распечатать и сохранить копию условий лицензии для своих записей. Скачивая и используя привязки Xamarin из пакета SDK для приложений Intune, вы соглашаетесь с этими условиями лицензии. Если вы не согласны, не используйте это программное обеспечение.

Для [аутентификации](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) пакет SDK использует библиотеки [Библиотеку проверки подлинности Active Directory (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) и сценарии условного запуска. Для этого в приложении должна быть определенная конфигурация [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Если приложение уже настроено для использования ADAL или MSAL и имеет свой собственный пользовательский идентификатор клиента, используемый для проверки подлинности с помощью Azure Active Directory, убедитесь, что выполнены шаги для предоставления разрешений приложения Xamarin для службы управления мобильными приложениями Intune (MAM). Инструкции см. в разделе [Предоставить вашему приложению доступ к Intune защиты службы приложений](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional) руководства [Приступая к работе с руководством по пакету SDK для Intune](app-sdk-get-started.md).

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Включение политик защиты приложений Intune в мобильном приложении iOS
1. Добавьте [пакет Microsoft.Intune.MAM.Xamarin.iOS NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) в проект Xamarin.iOS.
2.  Выполните общие шаги, необходимые для интеграции пакета SDK для приложений Intune в мобильное приложение iOS. Можно начать с шага 3 инструкций по интеграции из раздела [Интеграция пакета SDK с мобильным приложением](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Последний шаг в этом разделе IntuneMAMConfigurator можно пропустить, так как это средство включено в пакет Microsoft.Intune.MAM.Xamarin.iOS и будет запущено автоматически во время сборки.
    **Важно.** Включение общего доступа к цепочке ключей для приложения в Visual Studio немного отличается от этой процедуры в среде Xcode. Откройте PLIST-файл прав. Убедитесь, что включен параметр "Включить цепочку ключей" и что в этом разделе добавлены соответствующие группы совместного доступа к цепочке ключей. Убедитесь, что PLIST-файл прав указан в поле "Настраиваемые назначения" параметров пакетной подписи iOS проекта для всех соответствующих сочетаний конфигурации и платформы.
3.  После добавления привязок и правильной настройки приложение сможет использовать API пакета SDK для Intune. Для этого необходимо включить следующее пространство имен:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Чтобы ваше приложение получало политики защиты приложения, его необходимо зарегистрировать в службе Intune MAM. Если приложение не использует [библиотеку проверки подлинности Azure Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) или [библиотеку проверки подлинности Майкрософт](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) для аутентификации пользователей и вы хотите передать обработку проверки подлинности пакету SDK Intune, приложение должно предоставлять имя участника-пользователя в метод LoginAndEnrollAccount класса IntuneMAMEnrollmentManager.
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Приложение может передавать значение null, если имя участника-пользователя неизвестно во время вызова. В этом случае пользователям будет предложено ввести адрес электронной почты и пароль.
      
      Если приложение уже использует библиотеку ADAL или MSAL для проверки подлинности пользователей, можно настроить единый вход между приложением и пакетом SDK Intune. Прежде всего, необходимо настроить для библиотек ADAL/MSAL хранение маркеров в той же группе доступа к цепочкам ключей, которая используется привязками Xamarin Intune для iOS (com.microsoft.adalcache). Для ADAL это можно сделать, [задав свойство KeychainSecurityGroup класса AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications). Для MSAL потребуется [задать свойство KeychainSecurityGroup класса PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios). Затем необходимо переопределить параметры AAD по умолчанию, используемые пакетом SDK Intune, параметрами вашего приложения. Это можно сделать через словарь IntuneMAMSettings в файле Info.plist приложения, как упоминалось в разделе [Руководство для разработчиков по пакету SDK для приложений Microsoft Intune в iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), или можно использовать свойства переопределения AAD экземпляра IntuneMAMPolicyManager. Использование файла Info.plist рекомендуется для приложений, параметры ADAL которых являются статическими. И рекомендуется переопределять свойства приложений, которые определяют эти значения во время выполнения. После настройки всех параметров единого входа приложение должно предоставлять имя участника-пользователя методу RegisterAndEnrollAccount класса IntuneMAMEnrollmentManager после успешной проверки подлинности.
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Приложения могут определять результат попытки регистрации путем реализации метода EnrollmentRequestWithStatus в подклассе IntuneMAMEnrollmentDelegate и задания для свойства Delegate класса IntuneMAMEnrollmentManager экземпляра этого класса. См. [пример приложения Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios).

      После успешной регистрации приложения могут определять имя участника-пользователя зарегистрированной учетной записи (если ранее оно было неизвестно), запрашивая следующее свойство: 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> Модуль повторного сопоставления для iOS отсутствует. Интеграция в приложение Xamarin.Forms должна быть такой же, как и для обычного проекта Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Включение политик защиты приложений Intune в мобильном приложении Android

1. Добавьте [пакет Microsoft.Intune.MAM.Xamarin.Android NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) в проект Xamarin.Android.
    1. Для приложения Xamarin.Forms, добавьте [пакет Microsoft.Intune.MAM.Remapper.Tasks NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) в проект Xamarin.Android. 
2. Выполните общие шаги, необходимые для [интеграция пакета SDK для приложений Intune](app-sdk-android.md) в мобильное приложение Android для ссылки на дополнительные сведения.

### <a name="xamarinandroid-integration"></a>Интеграция Xamarin.Android

Полный обзор по интеграции пакета SDK для приложений Intune можно найти в [Microsoft Intune App SDK for руководство разработчика Android по](app-sdk-android.md). Прочтите руководство и интеграция пакета SDK для приложений Intune с приложением Xamarin следующие разделы призваны выделены различия между реализацией, собственное приложение Android, разработанный в Java и разработанные приложения Xamarin в C#. Эти разделы следует рассматривать как дополнительное и не может использоваться в качестве замены для обязательно прочитайте руководство целиком.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Переименованные методы](app-sdk-android.md#renamed-methods)
Часто метод, доступный в классе Android, отмечается как окончательный в замещающем классе MAM. В этом случае замещающий класс MAM предоставляет метод с таким же именем (с суффиксом `MAM`), который должен быть переопределен вместо исходного. Например, при наследовании от `MAMActivity` вместо переопределения `OnCreate()` и вызова `base.OnCreate()` объекту `Activity` необходимо переопределить `OnMAMCreate()` и вызвать `base.OnMAMCreate()`.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[Приложения MAM](app-sdk-android.md#mamapplication)
Необходимо определить приложение `Android.App.Application` класс, наследующий от `MAMApplication`. Убедитесь, что подкласс правильно декорирован атрибутом `[Application]` и переопределяет конструктор `(IntPtr, JniHandleOwnership)`.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Включение функций, требующих содействия со стороны приложения](app-sdk-android.md#enable-features-that-require-app-participation)
Пример. Определение необходимости использования ПИН-кода в приложении
```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```
Пример. Определение основного пользователя Intune
```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```
Пример. Определение разрешения на сохранение данных на устройстве или в облачном хранилище
```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[Регистрация для получения уведомлений из пакета SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
Ваше приложение следует зарегистрировать для получения уведомлений из пакета SDK. Для этого нужно создать класс `MAMNotificationReceiver` и зарегистрировать его с помощью `MAMNotificationReceiverRegistry`. Для этого укажите получателя, а также тип необходимых уведомлений в `App.OnMAMCreate`, как показано в следующем примере:
```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
    registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[Диспетчер регистрации MAM](app-sdk-android.md#mamenrollmentmanager)
```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Интеграция Xamarin.Forms

Для `Xamarin.Forms` приложений, мы предоставили `Microsoft.Intune.MAM.Remapper` пакета, который автоматически выполнять замену класса MAM, внедряя `MAM` классы в иерархии классов из часто используемых `Xamarin.Forms` классы. 

> [!NOTE]
> Интеграция Xamarin.Forms осуществляется требуется выполнить, кроме того, для интеграции Xamarin.Android, описанные выше.

После добавления в проект Remapper необходимо будет выполнить замену эквивалент MAM. Например `FormsAppCompatActivity` и `FormsApplicationActivity` можно продолжать использовать в приложение, предоставленное переопределений для `OnCreate` и `OnResume` заменяются эквивалентами MAM `OnMAMCreate` и `OnMAMResume` соответственно.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```
Если не внести замены могут возникнуть следующие ошибки компиляции, пока не выполните замены:
* [Ошибка компилятора CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Эта ошибка обычно возникает в этой форме ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Это ожидаемо; когда remapper изменяет наследование классов Xamarin, некоторые функции станут `sealed` и для переопределения вместо этого добавляется новый вариант MAM.
* [Ошибка компилятора CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): Эта ошибка обычно возникает в этой форме ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. По мере изменения порядка наследования некоторых классов Xamarin средством remapper некоторые функции-члены будут изменены на `public`. Если переопределить любой из этих функций, необходимо будет изменить их переопределения модификаторов доступа для тех `public` также.

> [!NOTE]
> Remapper перезаписывает зависимость, которая используется Visual Studio для автоматического завершения IntelliSense. Таким образом может потребоваться перезагрузить и перестройте проект в том случае, если Remapper был добавлен для IntelliSense, чтобы правильно распознать изменения.

## <a name="support"></a>Support
Если ваша организация является существующим клиентом Intune, обратитесь к представителю службы поддержки Майкрософт, чтобы отправить запрос в службу поддержки Майкрософт и разместить сведения о проблеме на [соответствующей странице GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), и мы ответим вам сразу же, как только сможем. 
