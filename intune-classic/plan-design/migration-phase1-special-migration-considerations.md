---
title: "Особые примечания о миграции | Документация Майкрософт"
description: "В этой статье представлены особые примечания о миграции для клиента, которые следует учитывать перед началом миграции."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>Этап 1. Особые примечания о миграции

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

В зависимости от имеющейся среды поставщика MDM к миграции могут применяться особые требования.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Сброс параметров к заводским настройкам для программы регистрации устройств (DEP) Apple

В рамках программы регистрации устройств (DEP) Apple задаются конфигурации устройств, которые пользователь не сможет удалить. Чтобы сохранить расширенные функции управления DEP, устройства нужно переключить в исходное состояние путем сброса параметров к заводским настройкам для регистрации в Intune.

Чтобы продолжить использовать DEP для управления устройствами в Intune, сделайте следующее:

1.  Внедрите [DEP в Intune](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

2.  Перейдите в учетную запись Apple DEP и [переназначьте Intune серийные номера устройств DEP](https://help.apple.com/deployment/business/#/tesf9562af26), назначенные поставщику MDM.

3.  [Синхронизируйте](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) учетную запись DEP с Intune.

4.  [Создайте и назначьте](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) соответствующие профили регистрации DEP серийным номерам в Intune.

5.  Сбросьте параметры устройства к заводским настройкам (удаленно с помощью текущего поставщика MDM или вручную на каждом устройстве).

6.  Распределите устройства между пользователями.

## <a name="next-steps"></a>Дальнейшие действия 

[Этап 2. Кампания по миграции](/intune-classic/plan-design/migration-phase2-migration-campaign)

