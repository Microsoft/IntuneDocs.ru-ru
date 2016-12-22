---
title: "Компонент Xamarin из пакета SDK для приложений Intune | Документация Майкрософт"
description: 
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: 74607fc704234e6ac85eae3bf55c186000c6e68a


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Компонент Xamarin из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](intune-app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.



## <a name="overview"></a>Обзор
[Компонент Xamarin из пакета SDK для приложений Intune](https://components.xamarin.com/view/microsoft.intune.mam) позволяет использовать [возможности управления мобильными приложениями Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в приложениях iOS и Android, созданных с помощью Xamarin. Этот компонент позволяет разработчикам легко встраивать в свои приложения на базе Xamarin функции защиты приложений Intune.

Вы обнаружите, что функции SDK можно включить без изменения поведения приложения. После встраивания компонента в мобильное приложение для iOS или Android ИТ-администратор сможет развернуть политику при помощи системы управления мобильными приложениями Microsoft Intune, где поддерживается множество разных возможностей для защиты данных.

## <a name="whats-supported"></a>Поддерживаемые возможности

### <a name="developer-machines"></a>Компьютеры разработчиков
* Windows


### <a name="mobile-app-platforms"></a>Платформы мобильных приложений
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Ситуации, связанные с управлением мобильными приложениями Intune

* Устройства, зарегистрированные в Intune MDM
* Сторонние устройства, зарегистрированные в EMM
* Неуправляемые устройства (не зарегистрированные в MDM)

Приложения Xamarin, созданные с помощью компонента Xamarin из пакета SDK для приложений Intune, теперь могут получать политики управления мобильными приложениями (MAM) Intune как на устройствах, зарегистрированных в системе управления мобильными устройствами (MDM) Intune, так и на незарегистрированных устройствах.

## <a name="prerequisites"></a>Предварительные требования

* **[Только для Android]** На устройстве должно быть установлено самое новое приложение корпоративного портала Microsoft Intune.

## <a name="get-started"></a>Начало работы

1.  Скачайте **Xamarin-component.exe** [отсюда](https://components.xamarin.com/submit/xpkg) и извлеките его.

2. Прочитайте [условия лицензионного соглашения](https://components.xamarin.com/license/microsoft.intune.mam) для компонента Xamarin Microsoft Intune MAM.

3.  Скачайте папку компонента Xamarin из пакета SDK для приложений Intune с [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) или [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) и извлеките ее. Файлы, скачанные на шагах 1 и 2, должны находиться на одном уровне каталога.

4.  В командной строке с правами администратора запустите `Xamain.Component.exe install <.xam> file`.

5.  В Visual Studio щелкните правой кнопкой мыши **компоненты** в ранее созданном проекте Xamarin.

6.  Выберите **Изменить компоненты** и добавьте компонент пакета SDK для приложений Intune, который скачали на свой компьютер.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Включение Intune MAM в мобильном приложении iOS
1.  Чтобы инициализировать пакет SDK для приложений Intune, потребуется выполнить вызов для любого API в классе `AppDelegate.cs`. Пример.

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Теперь, когда компонент добавлен и инициализирован, следует выполнить общие шаги, необходимые для встраивания пакета SDK в мобильное приложение iOS. Вы найдете полную документацию по включению собственных приложений iOS в разделе [Руководство разработчика iOS по SDK для приложений Intune](intune-app-sdk-ios.md).
3. **Важно**! Существует несколько изменений, характерных именно для приложений iOS на базе Xamarin. Например, при включении групп цепочек ключей вам потребуется добавить следующий код для включения примера приложения Xamarin в компонент. Ниже приведен пример групп, которые должны присутствовать в группах доступа к цепочкам ключей:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Вы выполнили шаги, необходимые для встраивания компонента в приложение iOS на базе Xamarin. Если вы используете Xcode для создания проекта, можно использовать `Intune App SDK Settings.bundle`. Это позволит включать и отключать параметры политики Intune при создании проекта для тестирования и отладки. Чтобы воспользоваться преимуществами данного пакета, выполните действия, описанные в разделе [Руководство разработчика iOS по SDK для приложений Intune](intune-app-sdk-ios.md), и ознакомьтесь с разделом, посвященным [отладке в Xcode](intune-app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-mam-in-your-android-mobile-app"></a>Включение MAM в мобильном приложении Android
Для приложений Android на базе Xamarin, которые не используют инфраструктуру пользовательского интерфейса, потребуется прочесть [Руководство разработчика Android по SDK для приложений Intune] и выполнить приведенные там указания. Для приложения Android на основе Xamarin следует заменить класс, методы и действия их эквивалентами MAM, используя [таблицу](intune-app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent-required) из этого руководства. Если приложение не определяет класс `android.app.Application`, потребуется создать его и убедиться, что выполняется наследование от `MAMApplication`.

Для Xamarin Forms и других инфраструктур пользовательского интерфейса мы предоставили средство `MAM.Remapper`. Оно поможет выполнить описанную замену класса. При этом вам потребуется выполнить следующие действия.

1.  Добавьте ссылку на пакет nuget ` Microsoft.Intune.MAM.Remapper.Tasks` версии 0.1.0.0 или более поздней.

2.  Добавьте следующую строку в файл CSPROJ Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Задайте действие сборки для добавленного файла `remapping-config.json` в **RemappingConfigFile**. Имеющийся `remapping-config.json` работает только с Xamarin.Forms. Информацию для других инфраструктур пользовательского интерфейса см. в файле сведений, входящем в состав пакета nuget Remapper.

## <a name="test-your-app"></a>Тестирование приложения

Вы завершили основные этапы встраивания компонента в приложение. Теперь можно выполнить действия, включенные в пример приложения Android Xamarin. Мы предоставили два примера: один для Xamarin.Forms, а другой — для Android.



<!--HONumber=Dec16_HO2-->


