---
title: "Компонент Xamarin из пакета SDK для приложений Microsoft Intune"
description: "Компонент Xamarin из пакета SDK для приложений Intune позволяет использовать политику защиты приложений Intune в приложениях iOS и Android, созданных с помощью Xamarin."
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9fa0d471f91eeeebd0058417aa437e5469f48e09
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Компонент Xamarin из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.

## <a name="overview"></a>Обзор
[Компонент Xamarin из пакета SDK для приложений Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) позволяет использовать [политику защиты приложений Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в приложениях iOS и Android, созданных с помощью Xamarin. Этот компонент позволяет разработчикам легко встраивать в свои приложения на базе Xamarin функции защиты приложений Intune.

> [!NOTE]
> Сейчас поддержка пакета SDK Intune для Xamarin доступна в предварительной версии. 

Компонент Xamarin из пакета SDK для приложений Microsoft Intune позволяет встроить в приложения, разработанные с помощью Xamarin, политики защиты приложений, также известные как политики защиты приложений или политики управления мобильными приложениями. В приложение, которое использует MAM, встроен пакет SDK для приложений Intune. ИТ-администраторы могут развернуть политики защиты приложений в вашем мобильном приложении, когда Intune активно управляет им.

## <a name="whats-supported"></a>Поддерживаемые возможности

### <a name="developer-machines"></a>Компьютеры разработчиков
* macOS


### <a name="mobile-app-platforms"></a>Платформы мобильных приложений
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Ситуации, связанные с управлением мобильными приложениями Intune

* Устройства, зарегистрированные в Intune MDM
* Сторонние устройства, зарегистрированные в EMM
* Неуправляемые устройства (не зарегистрированные в MDM)

Приложения Xamarin, созданные с помощью компонента Xamarin из пакета SDK для приложений Intune, теперь могут получать политики защиты приложений Intune как на устройствах, зарегистрированных в системе управления мобильными устройствами (MDM) Intune, так и на незарегистрированных устройствах.

## <a name="prerequisites"></a>Предварительные условия

* **[Только для Android]** На устройстве должно быть установлено самое новое приложение корпоративного портала Microsoft Intune.

## <a name="get-started"></a>Начало работы

1.  Скачайте **Xamarin-component.exe** [отсюда](https://components.xamarin.com/submit/xpkg) и извлеките его.

2. Прочитайте [условия лицензионного соглашения](https://components.xamarin.com/license/microsoft.intune.mam) для компонента Xamarin Microsoft Intune MAM.

3.  Скачайте папку компонента Xamarin из пакета SDK для приложений Intune с [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) или [Nuget.org](https://www.nuget.org/profiles/msintuneappsdk) и извлеките ее содержимое. Файлы, скачанные на шагах 1 и 3, должны находиться на одном уровне каталога.

4.  В командной строке с правами администратора запустите `mono Xamarin.Component.exe install <.xam> file`.

5.  В Visual Studio щелкните правой кнопкой мыши **компоненты** в ранее созданном проекте Xamarin.

6.  Выберите **Изменить компоненты** и добавьте компонент пакета SDK для приложений Intune, который скачали на свой компьютер.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Включение политик защиты приложений Intune в мобильном приложении iOS
1.  Выполните общие шаги, необходимые для интеграции пакета SDK для приложений Intune в мобильное приложение iOS. Можно начать с шага 3 инструкций по интеграции из раздела [Интеграция пакета SDK с мобильным приложением](app-sdk-ios.md#build-the-sdk-into-your-mobile-app).
    **Важно.** Включение общего доступа к цепочке ключей для приложения в Visual Studio немного отличается от этой процедуры в среде Xcode. Откройте PLIST-файл прав. Убедитесь, что включен параметр "Включить цепочку ключей" и что в этом разделе добавлены соответствующие группы совместного доступа к цепочке ключей. Убедитесь, что PLIST-файл прав указан в поле "Настраиваемые назначения" параметров пакетной подписи iOS проекта для всех соответствующих сочетаний конфигурации и платформы.
2.  После добавления компонента и правильной настройки приложение сможет использовать API пакета SDK для Intune. Для этого необходимо включить следующее пространство имен:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    Чтобы ваше приложение получало политики защиты приложения, его необходимо зарегистрировать в службе Intune MAM. Если ваше приложение уже использует библиотеку Azure Active Directory Authentication (ADAL) для аутентификации пользователей, оно должно предоставить имя участника-пользователя в метод registerAndEnrollAccount IntuneMAMEnrollmentManager после его успешной аутентификации:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Важно.** Необходимо заменить стандартные параметры ADAL пакета SDK для приложений Intune параметрами вашего приложения. Это можно сделать через словарь IntuneMAMSettings в файле Info.plist приложения, как упоминалось в разделе [Руководство для разработчиков по пакету SDK для приложений Microsoft Intune в iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), или можно использовать свойства переопределения AAD экземпляра IntuneMAMPolicyManager. Использование файла Info.plist рекомендуется для приложений, параметры ADAL которых являются статическими. И рекомендуется переопределять свойства приложений, которые определяют эти значения во время выполнения. 
      
      Если приложение не использует ADAL и вы хотите, чтобы аутентификацию обрабатывал пакет SDK Intune, приложение должно вызвать метод loginAndEnrollAccount IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Включение политик защиты приложений в мобильном приложении Android
Для приложений Android на базе Xamarin, которые не используют инфраструктуру пользовательского интерфейса, потребуется прочесть [Руководство разработчика Android по SDK для приложений Intune](app-sdk-android.md) и выполнить приведенные там указания. Для приложения Android на основе Xamarin следует заменить класс, методы и действия их эквивалентами MAM, используя [таблицу](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) из этого руководства. Если приложение не определяет класс `android.app.Application`, необходимо создать его и убедиться, что выполняется наследование от `MAMApplication`.

Для Xamarin Forms и других инфраструктур пользовательского интерфейса мы предоставили средство `MAM.Remapper`. Оно выполняет описанную замену класса. При этом вам необходимо выполнить следующие действия.

1.  Добавьте ссылку на пакет NuGet `Microsoft.Intune.MAM.Remapper.Tasks` версии 0.1.0.0 или более поздней.

2.  Добавьте следующую строку в файл CSPROJ Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Задайте действие сборки для добавленного файла `remapping-config.json` в **RemappingConfigFile**. Имеющийся `remapping-config.json` работает только с Xamarin.Forms. Информацию для других инфраструктур пользовательского интерфейса см. в файле сведений, входящем в состав пакета NuGet Remapper.

## <a name="next-steps"></a>Дальнейшие шаги

Вы завершили основные этапы встраивания компонента в приложение. Теперь можно выполнить действия, включенные в пример приложения Android Xamarin. Мы предоставили два примера: один для Xamarin.Forms, а другой — для Android.
