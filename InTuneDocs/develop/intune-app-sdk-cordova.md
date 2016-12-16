---
title: "Подключаемый модуль Cordova из пакета SDK для приложений Microsoft Intune | Документация Майкрософт"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 9ef09f43e6c878af689a500457bab578149de499


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Подключаемый модуль Cordova из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](intune-app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.


## <a name="overview"></a>Обзор

[Подключаемый модуль Cordova из пакета SDK для приложений Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) позволяет использовать [возможности управления мобильными приложениями Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в приложениях iOS и Android, созданных с помощью Cordova. С его помощью разработчики могут интегрировать в свое приложение на основе Cordova функции защиты данных и приложений Intune.

Вы обнаружите, что функции SDK можно включить без изменения поведения приложения. После встраивания подключаемого модуля в мобильное приложение для iOS или Android ИТ-администратор сможет развернуть политику при помощи системы управления мобильными приложениями Microsoft Intune, где поддерживается множество разных возможностей для защиты данных. Мы разработали этот подключаемый модуль таким образом, чтобы большинство действий выполнялось автоматически в процессе сборки Cordova. Это позволяет быстро реализовать функции управления в приложении. Чтобы начать работу, выполните указанные ниже действия с учетом целевой платформы.




## <a name="whats-supported"></a>Поддерживаемые возможности

### <a name="developer-machines"></a>Компьютеры разработчиков
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Платформы мобильных приложений
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Ситуации, связанные с управлением мобильными приложениями Intune

* Устройства, зарегистрированные в Intune MDM
* Сторонние устройства, зарегистрированные в EMM
* Неуправляемые устройства (не зарегистрированные в MDM)

Приложения Cordova, созданные с помощью подключаемого модуля Cordova из пакета SDK для приложений Intune, теперь могут получать политики управления мобильными приложениями (MAM) Intune как на устройствах, зарегистрированных в системе управления мобильными устройствами (MDM) Intune, так и на незарегистрированных устройствах.



## <a name="prerequisites"></a>Предварительные требования

### <a name="technical-prerequisites"></a>Технические предварительные требования

* **[Только для Android]** На устройстве должно быть установлено самое новое приложение корпоративного портала Microsoft Intune.


* Требуется [подключаемый модуль библиотек проверки подлинности Azure Active Directory (ADAL) для Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) версии 0.8.0 или более поздней.
  * **Внимание!** Из-за ошибки в Apache Cordova, описанной [здесь](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), приложения, которые уже имеют зависимость от подключаемого модуля, не обновляют его до нужной версии автоматически.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Перед установкой и использованием подключаемого модуля Cordova из пакета SDK для приложений Intune **требуется** выполнить следующее:

* Ознакомиться с [условиями лицензии для подключаемого модуля Cordova из пакета SDK для приложений Intune.](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Распечатать и сохранить копию условий лицензии для своих записей. Скачивая и используя подключаемый модуль Cordova из пакета SDK для приложений Intune, вы соглашаетесь с этими условиями лицензии.  Если вы не согласны, не используйте это программное обеспечение.


## <a name="quick-start"></a>Быстрое начало работы

1. Обновите версию ADAL:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Добавьте пакет SDK для приложений Intune для подключаемого модуля Cordova:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Встраивание подключаемого модуля в приложение iOS

Чтобы обеспечить поддержку приложения в Intune MAM, требуется выполнить несколько действий. Из соображений удобства эти действия выполняются автоматически в процессе сборки Cordova в качестве предварительной обработки. В результате автоматические действия изменят файлы `*.pbxproj`, `*-Info.plist` и `*.entitlements` файлы, связанные с конфигурацией проекта. Если проект не содержит файл объема обслуживания, подключаемый модуль создаст его автоматически.

Эта настройка поддерживает только один целевой объект. При наличии нескольких таких объектов настройка выполняется для первого из них. Если процедура завершается со сбоем, проверьте следующее:

1. Проект приложения Xcode называется `[name].xcodeproj`, где значение `[name]` определяется в `config.xml`
2. Проект использует [стандартную структуру каталогов для приложения Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Встраивание подключаемого модуля в приложение Android

1. Импортируйте этот подключаемый модуль с помощью самых новых средств Cordova. Подключаемый модуль будет автоматически вызываться как шаг `after_compile`.

2. В конце процесса сборки подключаемый модуль создаст версию APK с поддержкой MAM (Android API 14 или более поздней версии). Выходные данные сборки будут содержать `[Project]-intunewrapped-[Build_Configuration].apk` (например, `helloWorld-intunewrapped-debug.apk`).

Подключаемый модуль поддерживает только сборки Gradle.

В связи с описанной [здесь](https://issues.apache.org/jira/browse/CB-9434) ошибкой Cordova, из-за которой пропускаются некоторые обработчики Cordova при `cordova run`, для выполнения изолированного приложения из командной строки требуется выполнить следующие действия:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Подписывание приложения Android
Чтобы добавить сведения о подписи в изолированный APK, измените `build.json` обычным образом. Пример.
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Сборка только для тестирования на платформе Android

1. Добавьте `android:testOnly="true"` к узлу приложения в файле `AndroidManifest.xml`.


2. **Cordova 6.x.x:** в `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js` измените строку 60 с

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    значение
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Целью всего этого является выполнение `adb install` с флагом "-t", так как без него приложения `testOnly` не устанавливаются.

### <a name="debugging-from-visual-studio"></a>Отладка в Visual Studio
После первого запуска приложения должно появиться диалоговое окно с уведомлением о том, что приложение управляется Intune. Выберите параметр "Больше не показывать" и еще раз нажмите кнопку отладки и запуска в VS для перехода по точкам останова.

## <a name="known-limitations"></a>Известные ограничения
### <a name="android"></a>Android
* Поддержка MultiDex является неполной.
* Приложение должно быть нацелено на Android 4.0 (Android API 14) или более поздней версии.

### <a name="ios"></a>iOS
* Каждый раз при изменении списка UTI в узле **CFBundleDocumentTypes** файла **Info.plist** следует очистить UTI в разделе импортированных UTI того же файла PLIST (узел **UTImportedTypeDeclarations**) перед повторной сборкой. Все UTI Intune начинаются с префикса `com.microsoft.intune.mam`.

* Если вы хотите удалить подключаемый модуль Intune из проекта Cordova, следует также удалить платформу iOS и повторно добавить ее, чтобы отменить некоторые элементы конфигурации Intune в файлах XCODEPROJ и PLIST.



<!--HONumber=Dec16_HO2-->


