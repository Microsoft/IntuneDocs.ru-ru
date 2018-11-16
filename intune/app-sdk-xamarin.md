---
title: Привязки Xamarin из пакета SDK для приложений Microsoft Intune
description: Привязки Xamarin из пакета SDK для приложений Intune позволяют использовать политику защиты приложений Intune в приложениях iOS и Android, созданных с помощью Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune
ms.openlocfilehash: d2531cc203c5c2b255378e836099feb0a9216d45
ms.sourcegitcommit: cfce9318b5b5a3005929be6eab632038a12379c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51298128"
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

Для [аутентификации](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) пакет SDK использует библиотеки [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) и сценарии условного запуска. Для этого в приложении должна быть определенная конфигурация [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Значения конфигурации передаются в пакет SDK с метаданными AndroidManifest. Ознакомьтесь с документацией по [настройке ADAL для приложения](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).

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

Для приложений Android на базе Xamarin, которые не используют инфраструктуру пользовательского интерфейса, потребуется прочесть [Руководство разработчика Android по SDK для приложений Intune](app-sdk-android.md) и выполнить приведенные там указания. Для приложения Android на основе Xamarin следует заменить класс, методы и действия их эквивалентами MAM, используя [таблицу](app-sdk-android.md#class-and-method-replacements) из этого руководства. Если приложение не определяет класс `android.app.Application`, необходимо создать его и убедиться, что выполняется наследование от `MAMApplication`.

### <a name="xamarinandroid-integration"></a>Интеграция Xamarin.Android

1. Вы можете добавить последнюю версию [пакета Microsoft.Intune.MAM.Xamarin.Android NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) в проект Xamarin.Android. Это предоставит необходимые ссылки, чтобы включить Intune для вашего приложения.

2. Прочитайте [руководство разработчиков Android по SDK для приложений Intune](app-sdk-android.md) и следуйте ему, уделив особое внимание следующему:
    1. [Весь раздел о заменах классов и методов](app-sdk-android.md#class-and-method-replacements). 
    2. [Раздел MAMApplication](app-sdk-android.md#mamapplication). Убедитесь, что подкласс правильно декорирован атрибутом `[Application]` и переопределяет конструктор `(IntPtr, JniHandleOwnership)`.
    3. [Раздел об интеграции ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal), если приложение выполняет проверку подлинности на основе AAD.
    4. [Раздел о регистрации MAM-WE](app-sdk-android.md#app-protection-policy-without-device-enrollment), если вы планируете получить политику из службы MAM в своем приложении.

> [!NOTE]
> При попытке найти эквивалентные API в [руководстве разработчиков Android по SDK для приложений Intune](app-sdk-android.md) в привязках `Microsoft.Intune.MAM.Xamarin.Android` или при преобразовании фрагментов кода из руководства следует иметь в виду, что генератор привязок Xamarin особым образом изменяет API Android.
> * Все идентификаторы преобразуются в стиль Pascale (com.foo.bar -> Com.Foo.Bar)
> * Все операции get и set преобразуются в операции property (например, Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap").
> * Перед именами всех интерфейсов добавляется символ "I" (FooInterface -> IFooInterface).

### <a name="xamarinforms-integration"></a>Интеграция Xamarin.Forms

**Кроме реализации всех описанных выше действий**, мы предоставили для приложений `Xamarin.Forms` пакет `Microsoft.Intune.MAM.Remapper`. Он осуществляет замену класса, внедряя классы `MAM` в иерархии классов распространенных классов `Xamarin.Forms`, таких как `FormsAppCompatActivity` и `FormsApplicationActivity`, чтобы вы могли и дальше использовать эти классы, осуществляя переопределения для эквивалентных функций MAM, например `OnMAMCreate` и `OnMAMResume`. Чтобы его использовать, выполните следующие действия.

1.  Добавьте [пакет NuGet Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) в свой проект. При этом привязки пакета SDK для приложений Xamarin будут добавлены автоматически (если вы еще их не включили).

2.  Добавьте вызов `Xamarin.Forms.Forms.Init(Context, Bundle)` в функцию `OnMAMCreate` класса `MAMApplication`, созданного в шаге 2.2 выше. Это необходимо, так как благодаря функции управления Intune ваше приложение запускается в фоновом режиме.

> [!NOTE]
> Так как эта операция переписывает зависимость, используемую Visual Studio для автоматического завершения IntelliSense, может потребоваться перезапустить Visual Studio после первого запуска модуля повторного сопоставления для получения данных IntelliSense, чтобы изменения были распознаны правильно. 


## <a name="support"></a>Support

Вы завершили основные этапы встраивания компонента в приложение. Теперь можно выполнить действия, включенные в пример приложения Android Xamarin. Мы предоставили два примера: один для Xamarin.Forms, а другой — для Android.

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Требование по применению политик для защиты приложений Intune при использовании бизнес-приложений Android на базе Xamarin (необязательно) 

Далее приводятся рекомендации, гарантирующие, что бизнес-приложения Android на базе Xamarin на своих устройствах смогут использовать только пользователи, защищенные Intune. 

### <a name="general-requirements"></a>Общие требования
* Зарегистрируйте идентификатор приложения. Его можно узнать на [портале Azure](https://portal.azure.com/) на странице **Все приложения** в столбце **ИД приложения**. На портале Azure:
1.  Перейдите к колонке **Azure Active Directory**.
2.  Перейдите к настройке **регистрации приложения**.
3.  В разделе **Параметры** под заголовком **Доступ через API** выберите **Требуемое разрешение**. 
4.  Нажмите кнопку **+ Добавить**.
5.  Щелкните **Выбор API**. 
6.  В поле поиска введите **Управление мобильными приложениями Майкрософт**.
7.  Выберите **Управление мобильными приложениями (Майкрософт)** в списке API и щелкните "Выбрать".
8.  Выберите **чтение и запись данных управления приложениями пользователя**.
9.  Нажмите кнопку **Готово**.
10. Нажмите **Предоставить разрешения**, а затем **Да**. 
    
### <a name="working-with-the-intune-sdk"></a>Работа с пакетом SDK Intune
Эти инструкции относятся ко всем приложениям для Android и Xamarin, которые нуждаются в обязательном применении политик защиты устройств Intune на устройстве конечного пользователя.

1. Настройте ADAL, выполнив инструкции в [руководство по пакету SDK Intune для Android](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).
> [!NOTE] 
> Под идентификатором клиента понимается привязанный к приложению идентификатор на портале Azure. 
* Чтобы включить единый вход, обратитесь к подразделу 2 в разделе "Распространенные конфигурации ADAL".

2. Включите регистрацию по умолчанию, добавив в манифест следующее значение: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```.
> [!NOTE] 
> Это должна быть единственная интеграция со службой MAM-WE в приложении. При наличии других вызовов интерфейсов API MAMEnrollmentManager могут возникнуть конфликты.

3. Включите требуемую политику MAM, добавив в манифест следующее значение: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```.
> [!NOTE] 
> В результате приложениям будет необходимо скачать приложение корпоративного портала на устройство и пройти процедуру регистрации по умолчанию перед использованием.

### <a name="working-with-adal"></a>Работа с ADAL
Эти инструкции относятся ко всем приложениям для .NET и Xamarin, которые нуждаются в обязательном применении политик защиты приложений Intune на устройстве конечного пользователя.

1. Выполните все действия, описанные в документации по ADAL в разделе о [проверки подлинности для Android через брокер](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/tree/dev/adal#brokered-authentication-for-android).
> [!NOTE] 
> Ожидается, что в следующей выпускаемой версии .NET ADAL (3.17.4) будет представлено исправление, необходимое для использования этой возможности.

Если ваша организация является существующим клиентом Intune, обратитесь к представителю службы поддержки Майкрософт, чтобы отправить запрос в службу поддержки Майкрософт и разместить сведения о проблеме на [соответствующей странице GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), и мы ответим вам сразу же, как только сможем. 

