---
title: "Сущность IntuneManagementExtension | Документация Майкрософт"
description: "Справочник по категории \"Сущность IntuneManagementExtension\" коллекций сущностей в API хранилища данных Intune."
keywords: "Хранилище данных Intune"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93a5fde5f0c6ac870104ab90035e119757064cb3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
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
| ExtensionState |Состояние работоспособности IntuneManagementExtension. | Healthy |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension** ежедневно перечисляет работоспособность IntuneManagementExtension на каждом устройстве Windows 10.
Эти данные хранятся в течение 60 дней. 

| Свойство  | Описание | Пример |
|---------|------------|--------|
| DateKey |Уникальный идентификатор даты. | 123 |
| TenantKey |Уникальный идентификатор клиента. | 456 |
| DeviceKey |Уникальный идентификатор устройства. | 789 |
| ExtensionVersionKey |Уникальный идентификатор для версии IntuneManagementExtension. | 1 |
| ExtensionStateKey|Уникальный идентификатор для состояния работоспособности. | 2 |