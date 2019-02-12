---
title: Создание профилей устройств в Microsoft Intune | Документы Майкрософт
description: Добавьте или настройте профиль устройства в Microsoft Intune, включая выбор типа платформы и настройку параметров на портале Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: befffd3f3ae43531d8a5f541e6f7cd4e43f4a2b0
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845801"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Создайте профиль устройства в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Создание профиля

1. На [портале Azure](https://portal.azure.com) выберите **Все службы** > отфильтруйте список по **Intune** > выберите **Intune**.

2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.

3. Укажите следующие свойства.

   - **Имя**. Введите описательное имя для нового профиля.
   - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
   - **Платформа**. Выберите тип платформы:  

       - **Android**
       - **Android для бизнеса**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 и более поздние версии**
       - **Windows 10 и более поздних версий**.

   - **Тип профиля**. Выберите тип создаваемого профиля. Список зависит от выбранной платформы.
   - **Параметры**: Параметры каждого типа профиля описаны в следующих статьях:

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
