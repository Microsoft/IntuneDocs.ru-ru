---
title: "Подключаемый модуль Cordova из пакета SDK для приложений Microsoft Intune"
description: 
keywords: sdk, Cordova, intune
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fd4cedd20f427966dc3cfb7c2748f57b4d0746ab
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2017
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Подключаемый модуль Cordova из пакета SDK для приложений Microsoft Intune

> [!NOTE]
> Вы можете сначала прочесть статью [Начало работы с пакетом SDK для приложений Intune](app-sdk-get-started.md), в которой описана подготовка к интеграции на каждой поддерживаемой платформе.

## <a name="overview"></a>Обзор

[Подключаемый модуль Cordova из пакета SDK для приложений Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) в iOS и приложениях под управлением Android на основе Cordova С его помощью разработчики могут интегрировать в свое приложение на основе Cordova функции защиты данных и приложений Intune.

Вы обнаружите, что функции пакета SDK можно включить, не изменяя поведение приложения. После создания подключаемого модуля в приложении iOS или Android администратор Microsoft Intune сможет развернуть политику защиты приложений Intune, которая включает различные компоненты для защиты данных. Этот подключаемый модуль создан таким образом, что большинство действий выполняются автоматически в процессе сборки Cordova. Это позволяет быстро реализовать защиту приложения в Intune. Чтобы начать работу, выполните указанные ниже действия с учетом целевой платформы.

## <a name="supported-platforms"></a>Поддерживаемые платформы

* Подключаемый модуль работает в ОС Windows, Mac и Linux.
* Подключаемый модуль работает с приложениями Android: `minSdkVersion` >= 14 и `targetSdkVersion` <= 24.
* Подключаемый модуль работает с приложениями iOS, предназначенными для iOS 9.0 и более поздних версий.

## <a name="intune-mobile-application-management-scenarios"></a>Ситуации, связанные с управлением мобильными приложениями Intune

* Устройства, зарегистрированные в Intune MDM
* Сторонние устройства, зарегистрированные в EMM
* Неуправляемые устройства (не зарегистрированные в MDM)

Приложения Cordova, созданные с помощью подключаемого модуля Cordova из пакета SDK для приложений Intune, теперь могут получать политики защиты приложений Intune как на устройствах, зарегистрированных в системе управления мобильными устройствами (MDM) Intune, так и на незарегистрированных устройствах.

## <a name="prerequisites"></a>Необходимые компоненты

### <a name="android"></a>Android

* На устройстве должна быть установлена последняя версия приложения корпоративного портала Microsoft Intune.
* В расположении, где будет выполняться сборка Cordova при использовании подключаемого модуля, необходимо установить Java 7 (или более поздней версии).

### <a name="ios"></a>iOS

* Для использования функций MDM на устройстве должна быть установлена последняя версия приложения корпоративного портала Microsoft Intune. Это *не* требуется, если используется политика защиты приложений Intune без функций регистрации устройств.

### <a name="both-platforms"></a>Все платформы

* Требуется [подключаемый модуль библиотек проверки подлинности Azure Active Directory (ADAL) для Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) версии 0.8.0 или более поздней.

> [!NOTE]
> Из-за ошибки в Apache Cordova, описанной [здесь](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), приложения, которые зависят от подключаемого модуля, не обновляют подключаемый модуль до нужной версии автоматически.



## <a name="quick-start"></a>Быстрое начало работы

1. Обновите версию ADAL:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Добавьте пакет SDK для приложений Intune для подключаемого модуля Cordova:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Встраивание подключаемого модуля в приложение iOS

Чтобы включить для приложения политику защиты приложений Intune, потребуется выполнить несколько действий. Из соображений удобства эти действия выполняются автоматически в процессе сборки Cordova в качестве предварительной обработки. В результате автоматические действия изменят файлы `*.pbxproj`, `*-Info.plist` и `*.entitlements` файлы, связанные с конфигурацией проекта. Если проект не содержит файл объема обслуживания, подключаемый модуль создаст его автоматически.

Эта настройка поддерживает только один целевой объект. При наличии нескольких таких объектов настройка выполняется для первого из них. Если процедура завершается со сбоем, проверьте следующее:

1. Проект приложения Xcode называется `[name].xcodeproj`, где значение `[name]` определяется в `config.xml`
2. Проект использует [стандартную структуру каталогов для приложения Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="build-the-plugin-into-your-android-app"></a>Встраивание подключаемого модуля в приложение Android

1. Импортируйте этот подключаемый модуль с помощью самых новых средств Cordova. Подключаемый модуль будет автоматически вызываться как шаг `after_compile`.

2. В конце процесса сборки подключаемый модуль создаст версию встроенного пакета APK с поддержкой Intune (Android API 14 или более поздней версии). Выходные данные сборки будут содержать `[Project]-intunewrapped-[Build_Configuration].apk` (например, `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> Подключаемый модуль поддерживает только сборки Gradle.

В связи с описанной [здесь](https://issues.apache.org/jira/browse/CB-9434) ошибкой Cordova, из-за которой пропускаются некоторые обработчики Cordova при `cordova run`, для выполнения изолированного приложения из командной строки требуется выполнить следующие действия:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Подписывание приложения Android

Подключаемый модуль автоматически распознает сведения о подписи, которые вы указываете для Cordova в следующих расположениях:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Дополнительные сведения о требуемом формате см. в разделе о [свойствах подписи Cordova Gradle](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle).

Предоставление сведений о подписи в `build.json` или произвольных расположениях, передаваемых через параметры в сборку Cordova, сейчас не поддерживается.

## <a name="debugging-from-visual-studio"></a>Отладка в Visual Studio

После первого запуска приложения должно появиться диалоговое окно с уведомлением о том, что приложение управляется Intune. Выберите параметр "Больше не показывать" и еще раз нажмите кнопку отладки и запуска в VS для перехода по точкам останова.

## <a name="known-limitations"></a>Известные ограничения

### <a name="android"></a>Android

* Поддержка MultiDex является неполной.
* Приложение должно иметь `minSdkVersion` 14 и `targetSdkVersion` 24 (или ниже). Приложения, предназначенные для API 25, сейчас не поддерживаются.
* Нельзя повторно подписывать приложения, которые были подписаны с использованием схемы подписи V2. Когда такие приложения упаковываются с помощью подключаемого модуля, упакованный выходной APK-файл не будет подписан.
*
  * Вы можете отключить стандартную функцию схемы подписи V2 в Cordova, добавив следующий код в файл `build-extras.gradle`:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Каждый раз при изменении списка UTI в узле **CFBundleDocumentTypes** файла **Info.plist** следует очищать UTI Intune в разделе импортированных UTI того же PLIST-файла (узел **UTImportedTypeDeclarations**) перед повторной сборкой. Все UTI Intune начинаются с префикса `com.microsoft.intune.mam`.

* Если вы хотите удалить из проекта Cordova пакет SDK для приложений Intune для подключаемого модуля Cordova, следует также удалить платформу iOS и повторно добавить ее, чтобы отменить некоторые элементы конфигурации Intune в XCODEPROJ- и PLIST-файлах.
