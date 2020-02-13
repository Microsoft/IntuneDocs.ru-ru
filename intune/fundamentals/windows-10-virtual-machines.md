---
title: Использование виртуальных машин Windows 10 с Microsoft Intune
titleSuffix: ''
description: Рекомендации по использованию виртуальных машин Windows 10 с Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 486ca7eae1b1e8b016f44c735ec04a23145421a8
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124985"
---
# <a name="using-windows-10-virtual-machines-with-intune"></a>Использование виртуальных машин Windows 10 с Intune

Intune поддерживает управление виртуальными машинами под управлением Windows 10 Корпоративная с определенными ограничениями. Управление с помощью Intune не зависит от управления той же виртуальной машиной со стороны Виртуального рабочего стола Windows и не мешает ему.

При управлении виртуальными машинами Windows 10 с помощью Intune учитывайте приведенные ниже моменты.

## <a name="enrollment"></a>Регистрация
- Не рекомендуется управлять виртуальными машинами узла сеансов, размещенными по запросу, с помощью Intune. Каждая виртуальная машина должна быть зарегистрирована во время создания. Кроме того, в результате регулярного удаления виртуальных машин в Intune будут оставаться потерянные записи устройств до тех пор, пока они не будут [очищены](../remote-actions/devices-wipe.md#automatically-delete-devices-with-cleanup-rules). 
- Самостоятельное развертывание Windows Autopilot и развертывание с предварительной подготовкой не поддерживаются, поскольку для них требуется физический доверенный платформенный модуль (TPM). 
- Регистрация при первом включении компьютера не поддерживается на виртуальных машинах, доступ к которым возможен только через RDP (например, виртуальные машины, размещенные в Azure). Это ограничение означает:
    - Windows Autopilot и коммерческая версия регистрации при первом включении компьютера не поддерживаются.
    - Параметры страницы "Состояние регистрации" для политик контекста устройства не поддерживаются.

## <a name="configuration"></a>Конфигурация
Intune не поддерживает какую-либо конфигурацию, которая использует доверенный платформенный модуль (TPM) или управление оборудованием, в том числе:
- [параметры BitLocker](../configuration/device-profiles.md#endpoint-protection);
- [параметры интерфейса конфигурации встроенного ПО устройства](../configuration/device-profiles.md#device-firmware-configuration-interface).

## <a name="reporting"></a>Отчеты
Intune автоматически обнаруживает виртуальные машины и выводит их в виде записи "Виртуальная машина" в разделе **Устройства** > **Все устройства** > выберите устройство > **Обзор** > **Модель**. 

Освобожденные виртуальные машины могут привести к появлению записей в отчетах о несоответствующих устройствах, так как они не могут [обратиться к службе Intune](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retirement"></a>Прекращение использования
Если у вас есть доступ только по протоколу RDP, не используйте [действие очистки](../remote-actions/devices-wipe.md#wipe). Действие очистки удалит параметры RDP виртуальной машины и не позволит подключиться снова.


