---
title: Привязки Xamarin из пакета SDK для приложений Microsoft Intune
description: Привязки Xamarin из пакета SDK для приложений Intune позволяют использовать политику защиты приложений Intune в приложениях iOS и Android, созданных с помощью Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 079b27c73a466ae19dad950564ba0d56d8e20f8d
ms.sourcegitcommit: a474a6496209ff3b60e014a91526f3d163a45438
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44031275"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Привязки Xamarin из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.

## <a name="overview"></a>Обзор
[Привязки Xamarin из пакета SDK для приложений Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) позволяют использовать [политику защиты приложений Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в приложениях iOS и Android, созданных с помощью Xamarin. Привязки разрешают разработчикам легко встраивать в свои приложения на базе Xamarin функции защиты приложений Intune.

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

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Включение политик защиты приложений Intune в мобильном приложении iOS
1. Добавьте [пакет Microsoft.Intune.MAM.Xamarin.iOS NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) в проект Xamarin.iOS.
2.  Выполните общие шаги, необходимые для интеграции пакета SDK для приложений Intune в мобильное приложение iOS. Можно начать с шага 3 инструкций по интеграции из раздела [Интеграция пакета SDK с мобильным приложением](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Последний шаг в этом разделе IntuneMAMConfigurator можно пропустить, так как это средство включено в пакет Microsoft.Intune.MAM.Xamarin.iOS и будет запущено автоматически во время сборки.
    **Важно.** Включение общего доступа к цепочке ключей для приложения в Visual Studio немного отличается от этой процедуры в среде Xcode. Откройте PLIST-файл прав. Убедитесь, что включен параметр "Включить цепочку ключей" и что в этом разделе добавлены соответствующие группы совместного доступа к цепочке ключей. Убедитесь, что PLIST-файл прав указан в поле "Настраиваемые назначения" параметров пакетной подписи iOS проекта для всех соответствующих сочетаний конфигурации и платформы.
3.  После добавления привязок и правильной настройки приложение сможет использовать API пакета SDK для Intune. Для этого необходимо включить следующее пространство имен:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Чтобы ваше приложение получало политики защиты приложения, его необходимо зарегистрировать в службе Intune MAM. Если ваше приложение уже использует библиотеку Azure Active Directory Authentication (ADAL) для аутентификации пользователей, оно должно предоставить имя участника-пользователя в метод registerAndEnrollAccount IntuneMAMEnrollmentManager после его успешной аутентификации:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Важно.** Необходимо заменить стандартные параметры ADAL пакета SDK для приложений Intune параметрами вашего приложения. Это можно сделать через словарь IntuneMAMSettings в файле Info.plist приложения, как упоминалось в разделе [Руководство для разработчиков по пакету SDK для приложений Microsoft Intune в iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), или можно использовать свойства переопределения AAD экземпляра IntuneMAMPolicyManager. Использование файла Info.plist рекомендуется для приложений, параметры ADAL которых являются статическими. И рекомендуется переопределять свойства приложений, которые определяют эти значения во время выполнения. 
      
      Если приложение не использует ADAL и вы хотите, чтобы аутентификацию обрабатывал пакет SDK Intune, приложение должно вызвать метод loginAndEnrollAccount IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      
> [!NOTE] 
> Модуль повторного сопоставления для iOS отсутствует. Интеграция в приложение Xamarin.Forms должна быть такой же, как и для обычного проекта Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Включение политик защиты приложений Intune в мобильном приложении Android

Для приложений Android на базе Xamarin, которые не используют инфраструктуру пользовательского интерфейса, потребуется прочесть [Руководство разработчика Android по SDK для приложений Intune](app-sdk-android.md) и выполнить приведенные там указания. Для приложения Android на основе Xamarin следует заменить класс, методы и действия их эквивалентами MAM, используя [таблицу](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) из этого руководства. Если приложение не определяет класс `android.app.Application`, необходимо создать его и убедиться, что выполняется наследование от `MAMApplication`.

### <a name="xamarinandroid-integration"></a>Интеграция Xamarin.Android

1. Вы можете добавить последнюю версию [пакета Microsoft.Intune.MAM.Xamarin.Android NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) в проект Xamarin.Android. Это предоставит необходимые ссылки, чтобы включить Intune для вашего приложения.

2. Прочитайте [руководство разработчиков Android по SDK для приложений Intune](app-sdk-android.md) и следуйте ему, уделив особое внимание следующему:
    1. [Весь раздел о заменах классов и методов](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
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
* Команда SDK Intune запросит идентификатор вашего приложения. Его можно узнать на [портале Azure](https://portal.azure.com/) на странице **Все приложения** в столбце **ИД приложения**. Связаться с командой SDK Intune можно по электронной почте: msintuneappsdk@microsoft.com.
     
### <a name="working-with-the-intune-sdk"></a>Работа с пакетом SDK Intune
Эти инструкции относятся ко всем приложениям для Android и Xamarin, которые нуждаются в обязательном применении политик защиты устройств Intune на устройстве конечного пользователя.

1. Настройте ADAL, выполнив инструкции в [руководство по пакету SDK Intune для Android](https://docs.microsoft.com/en-us/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).
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

