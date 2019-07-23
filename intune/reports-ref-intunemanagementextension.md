---
title: Сущность IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Справочник по категории "Сущность IntuneManagementExtension" коллекций сущностей в API хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
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
ms.openlocfilehash: 70802626c79f11748e81c39afdd8bc8c5d0622b3
ms.sourcegitcommit: c3ac858bbadb63d248ed54069e48160d703bbaf2
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313774"
---
# <a name="reference-for-intune-management-extensions"></a>Справочник по расширениям для управления Intune

Категория **intuneManagementExtensions** содержит сущности для мобильных устройств, отслеживающие такую информацию:

- Версии IntuneManagementExtension
- Состояние установки IntuneManagementExtension

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

Сущность **intuneManagementExtensionVersion** выводит список всех версий, используемых intuneManagementExtensions.

| Свойство  | Описание | Пример |
|---------|------------|--------|
| extensionVersionKey |Уникальный идентификатор для версии IntuneManagementExtensions. | 1 |
| extensionVersion |Номер версии из 4 цифр. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

**intuneManagementExtensionHealthState** выводит список всех возможных состояний работоспособности intuneManagementExtensions.

| Свойство  | Описание | Пример |
|---------|------------|--------|
| extensionStateKey |Уникальный идентификатор для состояния работоспособности. | 2 |
| extensionState |Состояние работоспособности IntuneManagementExtension. | Работоспособно |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

**intuneManagementExtension** ежедневно выводит данные о работоспособности IntuneManagementExtensions на каждом устройстве с Windows 10.
Эти данные хранятся в течение 60 дней. 


|      Свойство       |                         Описание                         | Пример |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Уникальный идентификатор даты.                |   123   |
|      tenantKey      |              Уникальный идентификатор клиента.               |   456   |
|      deviceKey      |              Уникальный идентификатор устройства.               |   789   |
| extensionVersionKey | Уникальный идентификатор для версии intuneManagementExtension. |    1    |
|  extensionStateKey  |             Уникальный идентификатор для состояния работоспособности.              |    2    |

