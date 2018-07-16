---
title: Настройка параметров ограничений устройств в Microsoft Intune в Azure | Документы Майкрософт
description: Вы можете добавить профиль устройства для ограничения возможностей на устройствах Android, macOS, iOS, Windows Phone и Windows 10 в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 56ddf28bb9e81417b4b91bb18baaba14f07fbdd9
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905059"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Настройка параметров ограничений устройств в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ограничения устройств позволяют управлять параметрами и функциями для различных категорий, таких как:
- Безопасность
- Браузер
- Оборудование
- Параметры общего доступа к данным

Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств с iOS.

Ознакомьтесь с основами профиля ограничения устройств, а затем прочитайте статьи об особенностях каждой платформы.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Создание профиля устройства с параметрами ограничения для устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
4. Введите значения в поля **Имя** и **Описание** для профиля ограничения устройства.
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
    - [Параметры рабочего профиля Android](device-restrictions-android-for-work.md)
8. По завершении вернитесь на страницу **Создать профиль** и щелкните **Создать**.

Созданный профиль отобразится на странице со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
