---
title: "Создание профилей конфигурации устройств в Intune"
titlesuffix: Azure portal
description: "Создание профилей конфигурации устройств в Intune.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5afc6896883e6be67780c2314107c15633fd237a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Создание профилей конфигурации устройств в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
2. В колонке со списком профилей выберите **Создание профиля**.
3. В колонке **Создание профиля** укажите следующие элементы:
    - **Имя.** Введите описательное имя для нового профиля.
    - **Описание.** Введите необязательное описание профиля.
    - **Платформа.** Выберите тип платформы для профиля, который нужно создать.
    - **Тип профиля.** Выберите тип создаваемого профиля. Список доступных типов будет разным в зависимости от выбранной платформы.
    - **Параметры.** Информацию о параметрах для каждого типа профиля см. по ссылкам ниже.
        -  [Параметры возможностей устройства](device-features-configure.md)
        -  [Параметры ограничений для устройств](device-restrictions-configure.md)
        -  [Параметры электронной почты](email-settings-configure.md)
        -  [Параметры VPN](vpn-settings-configure.md)
        -  [Параметры Wi-Fi](wi-fi-settings-configure.md)
        -  [Параметры для обновления выпуска Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Параметры сертификата](certificates-configure.md)
        -  [Параметры Windows Information Protection](windows-information-protection-configure.md)
        -  [Параметры образования](education-settings-configure.md)
        -  [Пользовательские параметры](custom-settings-configure.md)

    ![Создание профиля устройства](./media/create-device-profile.png)
4. Завершив настройку параметров, в колонке **Создать профиль** выберите **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).


### <a name="next-steps"></a>Дальнейшие шаги
Сведения о назначении профилей устройств см. в статье о [назначении профилей устройств в Microsoft Intune](device-profile-assign.md).
