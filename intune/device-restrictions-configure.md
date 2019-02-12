---
title: Настройка параметров ограничений устройств в Microsoft Intune в Azure | Документы Майкрософт
description: Вы можете добавить профиль устройства для ограничения возможностей на устройствах Android, macOS, iOS, Windows Phone и Windows 10 в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e30b5fc544d67dcb9e10502d19961d1c91a3e47
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55843108"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Настройка параметров ограничений устройств в Microsoft Intune

Ограничения устройств позволяют управлять параметрами и функциями для различных категорий, таких как:
- Безопасность
- Браузер
- Оборудование
- Параметры общего доступа к данным

Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств с iOS.

Ознакомьтесь с основами профиля ограничения устройств, а затем прочитайте статьи об особенностях каждой платформы.

## <a name="create-the-profile"></a>Создание профиля

1. На [портале Azure](https://portal.azure.com) выберите **Все службы** > отфильтруйте список по **Intune** > выберите **Intune**.
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Введите значения в поля **Имя** и **Описание** для профиля ограничения устройства.
4. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить настроенные параметры. Сейчас для параметров ограничения устройства можно выбрать одну из следующих платформ:

    - **Android**
    - **Android для бизнеса**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 и более поздние версии**
    - **Windows 10 и более поздних версий**.

5. В раскрывающемся списке **Профиль** выберите **Ограничения устройства**. Если вы хотите создать профиль ограничений для устройств Windows 10 для совместной работы, например Surface Hub, выберите **Ограничения для устройств (Windows 10 для совместной работы)**.
6. Доступные для настройки параметры различаются в зависимости от выбранной платформы. Выберите платформу для настройки дополнительных параметров:

    - [Параметры Android](device-restrictions-android.md)
    - [Параметры Android для бизнеса](device-restrictions-android-for-work.md)
    - [Параметры iOS](device-restrictions-ios.md)
    - [Параметры macOS](device-restrictions-macos.md)
    - [Параметры Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Параметры Windows 10](device-restrictions-windows-10.md)
    - [Параметры Windows 10 для совместной работы](device-restrictions-windows-10-teams.md)
    - [Параметры Windows Holographic for Business](device-restrictions-windows-holographic.md)

7. По завершении нажмите **ОК** > **Создать**, чтобы сохранить изменения.

Созданный профиль отобразится в списке профилей.

## <a name="next-steps"></a>Дальнейшие шаги

Созданный профиль готов к назначению. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
