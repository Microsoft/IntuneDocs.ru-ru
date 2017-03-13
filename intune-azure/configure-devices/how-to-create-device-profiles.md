---
title: "Создание профилей конфигурации устройств в Intune | Предварительная версия Intune Azure"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: создание профилей конфигурации устройств в Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: cc9ef6777f06aca5ef93154c38e12520ab9ed348
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Создание профилей конфигурации устройств в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
2. В колонке со списком профилей выберите **Создание профиля**.
3. В колонке **Создание профиля** укажите следующее:
    - **Имя.** Введите описательное имя для нового профиля.
    - **Описание.** Введите необязательное описание профиля.
    - **Платформа.** Выберите тип платформы для профиля, который нужно создать.
    - **Тип профиля.** Выберите тип создаваемого профиля. Список доступных типов будет разным в зависимости от выбранной платформы.
    - **Параметры.** Информацию о параметрах для каждого типа профиля см. по ссылкам ниже.
        -  [Параметры ограничений для устройств](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Параметры электронной почты](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Параметры VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Параметры Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Параметры для обновления выпуска Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Параметры сертификата](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Параметры Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Параметры образования](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Пользовательские параметры](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Создание профиля устройства](./media/create-device-profile.png)
4. Завершив настройку параметров, в колонке **Создать профиль** выберите **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Дальнейшие действия
Сведения о назначении профилей устройств см. в статье о [назначении профилей устройств в Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).

