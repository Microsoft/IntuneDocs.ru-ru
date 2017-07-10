---
title: "Особые примечания о миграции"
description: "В этой статье представлены особые примечания о миграции для клиента, которые следует учитывать перед началом миграции."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Особые примечания о миграции

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

В зависимости от имеющейся среды поставщика MDM к миграции могут применяться особые требования.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Сброс параметров к заводским настройкам для программы регистрации устройств (DEP) Apple

В рамках программы регистрации устройств (DEP) Apple задаются конфигурации устройств, которые пользователь не сможет удалить. Чтобы сохранить расширенные функции управления DEP, устройства нужно переключить в исходное состояние путем сброса параметров к заводским настройкам для регистрации в Intune.

Чтобы продолжить использовать программу DEP для управления устройствами в Intune, [настройте регистрацию устройств iOS с помощью программы регистрации устройств](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Дальнейшие действия 

[Этап 2. Кампания по миграции](migration-guide-campaign.md)
