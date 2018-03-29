---
title: Создание профилей устройств в Microsoft Intune | Документы Майкрософт
description: Добавьте или настройте профиль устройства в Microsoft Intune, включая выбор типа платформы и настройку параметров на портале Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e5070052c0d4cce3cfd81a7bae259bc7dfb22e7f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Создайте профиль устройства в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Создание профиля
1. На [портале Azure](https://portal.azure.com) выберите **Все службы** и найдите **Microsoft Intune**.

2. В **Microsoft Intune** выберите **Конфигурация устройства** и нажмите **Профили**. Затем нажмите **Создать профиль**.

3. Укажите следующие свойства.

    - **Имя.** Введите описательное имя для нового профиля.
    - **Описание.** Введите описание профиля. (Этот шаг является необязательным, но рекомендуемым.)
    - **Платформа.** Выберите тип платформы:  

        - **Android**
        - **Android for Work**
        - **iOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 и более поздние версии**
        - **Windows 10 и более поздних версий**.

    - **Тип профиля.** Выберите тип создаваемого профиля. Список зависит от выбранной платформы.
    - **Параметры.** Параметры каждого типа профиля описаны в следующих статьях.

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

    ![Снимок экрана создания профиля](./media/create-device-profile.png)

4. Нажмите **Создать** после завершения.

Созданный профиль отобразится в списке.


## <a name="next-steps"></a>Дальнейшие шаги
Сведения о назначении профилей устройств см. в статье [Как назначить профили устройств в Microsoft Intune](device-profile-assign.md).
