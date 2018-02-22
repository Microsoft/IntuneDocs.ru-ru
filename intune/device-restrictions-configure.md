---
title: "Настройка ограничений для устройств Intune"
titleSuffix: Azure portal
description: "Сведения о настройке параметров и функций на управляемых устройствах с помощью Intune.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93b6a642f26ec6273853f75d063fd368698f3864
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Настройка параметров ограничений для устройств iOS в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ограничения устройств позволяют управлять параметрами и функциями для различных категорий, таких как:
- Безопасность
- Браузер
- Оборудование
- Параметры общего доступа к данным

Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств с iOS.

Эта статья содержит базовые сведения о настройке профилей ограничения устройств, а также ссылки на статьи со сведениями об особенностях устройств, работающих под управлением разных платформ.

Создание профиля устройства с параметрами ограничения для устройства:

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создание профиля**.
4. В колонке **Создание профиля** введите **Имя** и **Описание** для профиля ограничения устройства.
5. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить настроенные параметры. Сейчас для параметров ограничения устройства можно выбрать одну из следующих платформ:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 и более поздние версии**
    - **Windows 10 и более поздних версий**.
6. В раскрывающемся списке **Профиль** выберите **Ограничения устройства**. Если вы хотите создать профиль ограничений для устройств Windows 10 для совместной работы, например Surface Hub, выберите **Ограничения для устройств (Windows 10 для совместной работы)**.
7. Доступные для настройки параметры различаются в зависимости от выбранной платформы. Дополнительные сведения о параметрах для каждой платформы см. по ссылкам ниже.
    - [Параметры Android](device-restrictions-android.md)
    - [Параметры iOS](device-restrictions-ios.md)
    - [Параметры macOS](device-restrictions-macos.md)
    - [Параметры Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Параметры Windows 10](device-restrictions-windows-10.md)
    - [Параметры Windows 10 для совместной работы](device-restrictions-windows-10-teams.md)
    - [Параметры Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Параметры Android for Work](device-restrictions-android-for-work.md)
8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->