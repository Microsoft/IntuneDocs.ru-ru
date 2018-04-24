---
title: Привязки Xamarin из пакета SDK для приложений Microsoft Intune
description: Привязки Xamarin из пакета SDK для приложений Intune позволяют использовать политику защиты приложений Intune в приложениях iOS и Android, созданных с помощью Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f9cc117925f59c9fb7c55d0ff10aedf09d26f93
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Привязки Xamarin из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.

## <a name="overview"></a>Обзор
[Привязки Xamarin из пакета SDK для приложений Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) позволяют использовать [политику защиты приложений Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в приложениях iOS и Android, созданных с помощью Xamarin. Привязки разрешают разработчикам легко встраивать в свои приложения на базе Xamarin функции защиты приложений Intune.

Привязки Xamarin из пакета SDK для приложений Microsoft Intune позволяют встраивать в приложения, разработанные с помощью Xamarin, политики защиты приложений Intune, также известные как политики защиты приложений или политики управления мобильными приложениями. В приложение, которое использует MAM, встроен пакет SDK для приложений Intune. ИТ-администраторы могут развернуть политики защиты приложений в вашем мобильном приложении, когда Intune активно управляет им.

## <a name="whats-supported"></a>Поддерживаемые возможности

### <a name="developer-machines"></a>Компьютеры разработчиков
* Windows
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

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Включение политик защиты приложений в мобильном приложении Android
Добавьте [пакет Microsoft.Intune.MAM.Xamarin.Android NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) в проект Xamarin.Android.

При работе с приложениями Xamarin.Android необходимо полностью прочесть [руководство разработчика Android по SDK для приложений Intune](app-sdk-android.md) и выполнить содержащиеся в нем инструкции, включая замену классов, методов и действий их эквивалентами MAM на основе [таблицы](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent), приведенной в руководстве. 

> [!NOTE]
> Если приложение не определяет класс `android.app.Application`, необходимо создать его и убедиться, что выполняется наследование от `MAMApplication`.

> [!NOTE]
> При попытке найти эквивалентные API в [руководстве разработчика Android по SDK для приложений Intune](app-sdk-android.md) в привязках `Microsoft.Intune.MAM.Xamarin.Android` или при преобразовании фрагментов кода из руководства следует иметь в виду, что генератор привязок Xamarin особым образом изменяет API Android.
> * Все идентификаторы преобразуются в стиль Pascale (com.microsoft.foo -> Com.Microsoft.Foo).
> * Все операции get и set преобразуются в операции property (например, Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap").
> * Перед именами всех интерфейсов добавляется символ "I" (FooInterface -> IFooInterface).

Для приложений, использующих Xamarin Forms или другие инфраструктуры пользовательского интерфейса, мы предоставили средство `Microsoft.Intune.MAM.Remapper`. Оно выполняет описанную замену класса. Чтобы его использовать, выполните следующие действия.

1.  Добавьте [пакет NuGet Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) в свой проект.

2.  Для файла `remapping-config.json`, который включен в пакет Nuget, задайте действие сборки **RemappingConfigFile**. Имеющийся `remapping-config.json` работает только с Xamarin.Forms. Информацию для других инфраструктур пользовательского интерфейса см. в файле сведений, входящем в состав пакета NuGet Remapper.

3.  Добавьте вызов Xamarin.Forms.Forms.Init(Context, Bundle) в функцию OnMAMCreate для MAMApplication, так как при управлении с помощью Intune приложение может быть запущено в фоновом режиме.

4.  Выполните остальные действия из [руководства разработчика Android по SDK для приложений Intune](app-sdk-android.md), применимые к приложению.

> [!NOTE]
> Иногда при обновлении пакета Microsoft.Intune.MAM.Remapper.Tasks происходит сброс действия сборки remapping-config.json, что приводит к сбою сборки.

## <a name="next-steps"></a>Дальнейшие шаги

Вы завершили основные действия настройки приложения для управления с помощью Intune. Теперь можно выполнять процедуры из руководств по интеграции для каждой из перечисленных выше платформ.

Если ваша организация является существующим клиентом Intune, обратитесь к представителю службы поддержки Майкрософт, чтобы отправить запрос в службу поддержки Майкрософт и разместить сведения о проблеме на [соответствующей странице GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), и мы ответим вам сразу же, как только сможем. 