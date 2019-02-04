---
title: Обновление до Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Сведения о том, как обновить устройства с Windows Holographic и перевести их на Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 80d4cf8db5789e6eeb22a777eeef74dce3009856
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831298"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Обновление устройств с Windows Holographic до Windows Holographic for Business

Microsoft Intune включает множество параметров для управления и защиты устройств. В этой статье перечислены и описаны параметры, которые можно использовать, чтобы обновить устройства Windows Holographic до Windows Holographic for Business. Эти параметры создаются в профиле конфигурации обновлений в Intune, отправляемых или развернутых на устройствах.

В рамках решения в системе управления мобильными устройствами используйте эти параметры для обновления ваших устройств Windows Holographic. Для получения нужной лицензии на обновление Microsoft HoloLens вы можете приобрести пакет Commercial Suite. Дополнительные сведения: [Разблокировка функций Windows Holographic for Business](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

Дополнительные сведения об этой функции см. в разделе [Обновление Windows 10 или выход из S-режима в Intune с помощью профиля конфигурации](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Подготовка к работе

[Создайте профиль конфигурации устройства](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Обновление выпусков

- **Выпуск, до которого необходимо обновить**: выберите **Windows 10 Holographic для бизнеса**.
- **Файл лицензии**: перейдите и выберите полученный вами файл лицензии XML.

  ![Введите имя файла XML, которое включает информацию о Holographic for Business.](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но пока в нем ничего нельзя делать. Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).

Вы можете также создать профили обновления выпусков для устройств [Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения S-режима в Intune](edition-upgrade-windows-settings.md).
