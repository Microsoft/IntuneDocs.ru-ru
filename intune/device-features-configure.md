---
title: "Настройка параметров возможностей устройств Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: сведения о настройке возможностей на управляемых устройствах с помощью Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f584d76a498264f8ab1cf883f5ee95d52d3446d3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Настройка параметров возможностей устройств в Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ограничения устройств позволяют управлять возможностями устройств с iOS и macOS, например AirPrint, уведомления и конфигурации общих устройств.

Эта статья содержит базовые сведения о настройке профилей возможностей устройств, а также ссылки на статьи со сведениями об особенностях устройств, работающих под управлением разных платформ.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Создание профиля устройства с параметрами ограничения для устройства

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Другое** > **Intune**.
3. В колонке **Intune** выберите пункт **Конфигурация устройства**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создание профиля**.
4. В колонке **Создание профиля** введите **имя** и **описание** для профиля ограничения устройства.
5. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить параметры. Сейчас для возможностей устройств можно выбрать одну из следующих платформ.
    - **iOS**
    - **macOS**
6. В раскрывающемся списке **Тип профиля** выберите **Возможности устройств**. 
7. Доступные для настройки параметры будут отличаться в зависимости от выбранной платформы. Дополнительные сведения о параметрах для каждой платформы см. по ссылкам ниже.
    - [Параметры AirPrint для iOS и MacOS](air-print-settings-ios-macos.md)
     - [Параметры AirPlay для iOS](airplay-settings-ios.md)
    - [Параметры макета начального экрана для iOS](home-screen-settings-ios.md)
    - [Параметры уведомлений приложения для iOS](app-notification-settings-ios.md)
    - [Параметры конфигурации iOS общего устройства](shared-device-settings-ios.md)

8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).




