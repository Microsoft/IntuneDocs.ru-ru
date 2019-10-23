---
title: Особые примечания о миграции
titleSuffix: Microsoft Intune
description: В этой статье рассказывается о том, какие моменты необходимо учесть, прежде чем начинать миграцию в Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 86cef30c31b53c6bfd1873390fb7546cbeab2a53
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510038"
---
# <a name="special-migration-considerations"></a>Особые примечания о миграции

В зависимости от имеющейся среды поставщика MDM к миграции могут применяться особые требования.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Очистка для программы регистрации устройств (DEP) Apple

В рамках программы регистрации устройств (DEP) Apple задаются конфигурации устройств, которые пользователь не сможет удалить. Чтобы сохранить расширенные функции управления DEP, устройства нужно переключить в исходное состояние путем очистки для регистрации в Intune.

Чтобы продолжить использовать программу DEP для управления устройствами в Intune, [настройте регистрацию устройств iOS с помощью программы регистрации устройств](../enrollment/device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Дальнейшие шаги

[Этап 2. Кампания по миграции](../migration-guide-campaign.md)
