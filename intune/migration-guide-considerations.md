---
title: "Особые примечания о миграции"
description: "В этой статье рассказывается о том, какие моменты необходимо учесть, прежде чем начинать миграцию."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2017
---
# <a name="special-migration-considerations"></a>Особые примечания о миграции

В зависимости от имеющейся среды поставщика MDM к миграции могут применяться особые требования.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Сброс параметров к заводским настройкам для программы регистрации устройств (DEP) Apple

В рамках программы регистрации устройств (DEP) Apple задаются конфигурации устройств, которые пользователь не сможет удалить. Чтобы сохранить расширенные функции управления DEP, устройства нужно переключить в исходное состояние путем сброса параметров к заводским настройкам для регистрации в Intune.

Чтобы продолжить использовать программу DEP для управления устройствами в Intune, [настройте регистрацию устройств iOS с помощью программы регистрации устройств](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Дальнейшие действия

[Этап 2. Кампания по миграции](migration-guide-campaign.md)
