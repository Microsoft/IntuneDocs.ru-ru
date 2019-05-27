---
title: Сущность IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Справочник по категории "Сущность IntuneManagementExtension" коллекций сущностей в API хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebece46bac8ebee5cb3c6a573f0b09c4b308abe3
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040985"
---
# <a name="reference-for-intune-management-extension"></a>Справочник по расширению управления Intune

Категория **IntuneManagementExtension** содержит сущности для мобильных устройств, отслеживающие указанную ниже информацию:

  -  Версии IntuneManagementExtension
  -  Состояние установки IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

Сущность **IntuneManagementExtensionVersion** перечисляет все версии, используемые IntuneManagementExtension.

| Свойство  | Описание | Пример |
|---------|------------|--------|
| ExtensionVersionKey |Уникальный идентификатор для версии IntuneManagementExtension. | 1 |
| ExtensionVersion |Номер версии из 4 цифр. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState** перечисляет все возможные состояния работоспособности IntuneManagementExtension.

| Свойство  | Описание | Пример |
|---------|------------|--------|
| ExtensionStateKey |Уникальный идентификатор для состояния работоспособности. | 2 |
| ExtensionState |Состояние работоспособности IntuneManagementExtension. | Работоспособно |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension** ежедневно перечисляет работоспособность IntuneManagementExtension на каждом устройстве Windows 10.
Эти данные хранятся в течение 60 дней. 


|      Свойство       |                         Описание                         | Пример |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Уникальный идентификатор даты.                |   123   |
|      TenantKey      |              Уникальный идентификатор клиента.               |   456   |
|      DeviceKey      |              Уникальный идентификатор устройства.               |   789   |
| ExtensionVersionKey | Уникальный идентификатор для версии IntuneManagementExtension. |    1    |
|  ExtensionStateKey  |             Уникальный идентификатор для состояния работоспособности.              |    2    |

