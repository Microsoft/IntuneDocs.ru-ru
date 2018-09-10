---
title: Создание профилей устройств в Microsoft Intune | Документы Майкрософт
description: Добавьте или настройте профиль устройства в Microsoft Intune, включая выбор типа платформы и настройку параметров на портале Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7195b9d2d64c2282f2380624a209ad45220d3a4f
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313944"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Создайте профиль устройства в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Создание профиля
1. На [портале Azure](https://portal.azure.com) выберите **Все службы** и найдите **Microsoft Intune**.

2. В **Microsoft Intune** выберите **Конфигурация устройства** и нажмите **Профили**. Затем нажмите **Создать профиль**.

3. Укажите следующие свойства.

   - **Имя.** Введите описательное имя для нового профиля.
   - **Описание.** Введите описание профиля. (Этот шаг является необязательным, но рекомендуемым.)
   - **Платформа.** Выберите тип платформы:  

       - **Android**
       - **Рабочие профили Android**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 и более поздние версии**
       - **Windows 10 и более поздних версий**.

   - **Тип профиля.** Выберите тип создаваемого профиля. Список зависит от выбранной платформы.
   - **Параметры.** Параметры каждого типа профиля описаны в следующих статьях.

       -  [Возможности устройств](device-features-configure.md)
       -  [Ограничения устройств](device-restrictions-configure.md)
       -  [Защита конечных точек](endpoint-protection-configure.md)
       -  [Защита идентификации](identity-protection-configure.md)  
       -  [Киоск](kiosk-settings.md)
       -  [Электронная почта](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Образование для [Windows 10](education-settings-configure.md) и [iOS](wi-fi-settings-ios.md)
       -  [Обновление выпуска Windows 10](edition-upgrade-configure-windows-10.md)
       -  [Политики обновления iOS](software-updates-ios.md)
       -  [Сертификаты](certificates-configure.md)
       -  [Windows Information Protection](windows-information-protection-configure.md)
       -  [Пользовательский](custom-settings-configure.md)

     ![Снимок экрана создания профиля](./media/create-device-profile.png)

4. Нажмите **Создать** после завершения.

Созданный профиль отобразится в списке.

## <a name="next-steps"></a>Дальнейшие шаги
[Назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).
