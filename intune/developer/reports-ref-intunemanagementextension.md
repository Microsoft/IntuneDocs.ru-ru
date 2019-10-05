---
title: Сущность IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Справочник по категории "Сущность IntuneManagementExtension" коллекций сущностей в API хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
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
ms.openlocfilehash: 19b63172c8901059239c44aaf56fc49f0d7a01ad
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940399"
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

