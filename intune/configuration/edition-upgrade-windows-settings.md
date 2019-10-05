---
title: Параметры обновления Windows 10 и S-режима в Microsoft Intune в Azure | Документация Майкрософт
description: В статье представлен список всех параметров и их назначение при обновлении выпуска Windows 10 на устройстве, а также включение S-режима на устройстве с помощью профиля конфигурации устройства в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c34f683bfd16362dfb9af9a69c6f7d9b04860c7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734769"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения S-режима в Intune

Microsoft Intune включает множество параметров для управления и защиты устройств. В этой статье перечислены и описаны параметры обновления выпусков или включение S-режима на устройствах Windows 10. Эти параметры создаются в профиле конфигурации обновлений в Intune, отправляемых или развернутых на устройствах.

В рамках управления мобильными устройствами (MDM) используйте эти параметры для управления параметрами выпуска и S-режима для устройств с Windows 10.

Дополнительные сведения об этой функции см. в разделе [Обновление Windows 10 или выход из S-режима в Intune с помощью профиля конфигурации](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Подготовка к работе

[Создайте профиль](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Обновление выпусков

- **Выпуск, до которого необходимо обновить**: выберите выпуск Windows 10, до которого производится обновление. Устройства, на которые распространяется данная политика, обновляются до выбранного выпуска.
- **Ключ продукта**: укажите ключ продукта, полученный от Майкрософт. После создания политики с помощью ключа продукта ключ невозможно обновить. Он скрыт по соображениям безопасности. Чтобы изменить его, необходимо повторно ввести весь ключ.
- **Файл лицензии**: для выпуска **Windows 10 Holographic for Business** или **Windows 10 Mobile** нажмите кнопку **Обзор**, чтобы выбрать файл лицензии, полученный от Майкрософт. Этот файл лицензии содержит сведения о лицензии для выпусков, до которых обновляются устройства.

## <a name="mode-switch"></a>Переключение режима

- **Без настройки**: устройство остается в S-режиме. Пользователь может вывести устройство из S-режима.
- **Оставаться в S-режиме**: пользователь не сможет вывести устройство из S-режима.
- **Смена**: устройство выводится из S-режима.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но пока в нем ничего нельзя делать. Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).

Вы также можете создать профили обновления выпусков, подробнее см. в статье [Обновление устройств с Windows Holographic до Windows Holographic for Business](holographic-upgrade.md).
