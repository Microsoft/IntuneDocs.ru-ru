---
title: "Руководство по переходу к управлению мобильными устройствами (MDM) Intune | Документация Майкрософт"
description: "В этом руководстве представлены различные сведения, связанные с переходом от стороннего поставщика MDM к Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Руководство по переходу к Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Статья с руководством по переходу к Intune MDM](../media/MDM-migration-guide-art.PNG)

Успешный переход к Intune начинается с создания надежного плана, в котором учитывается текущая среда MDM, бизнес-цели и технические требования. Кроме того, необходимо заручиться поддержкой ключевых заинтересованных лиц, которые будут содействовать реализации вашего плана перехода и работать над ним вместе с вами.

В этом руководстве представлены различные сведения, связанные с переходом от стороннего поставщика MDM к Intune.

## <a name="whats-included-in-this-guide"></a>Что входит в состав этого руководства?

В руководстве представлено два этапа, каждый из которых состоит из задач, стратегий и тактических рекомендаций, которые помогут вам постепенно и комплексно перейти к Intune MDM.

-   [Этап 1. Подготовка Intune к управлению мобильными устройствами (MDM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Оценка требований к переходу к MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Базовая настройка](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Настройка политик управления устройствами и приложениями](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Настройка политик защиты приложений (необязательно)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Особые примечания о миграции](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [Этап 2. Кампания по миграции](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [План распространения сведений](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Реализация в системах конечных пользователей за счет условного доступа](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Типичный цикл миграции](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Мониторинг миграции](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Задачи, выполняемые после переноса](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Допущения

-   Вы уже оценили Intune в среде для подтверждения концепции и решили использовать эту службу в качестве решения по управлению мобильными устройствами в своей организации.

-   Вы уже знакомы с Intune и ее функциями. 

> [!NOTE]
> Изучите [руководство по оценке Intune](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune), если хотите более подробно ознакомиться с Intune перед миграцией.

## <a name="before-you-begin"></a>Подготовка к работе

Важно понять, что новое развертывание Intune может отличаться от старого развертывания MDM. В отличие от традиционных служб MDM, служба Intune ориентирована на управление доступом на основе удостоверений и поэтому не требует сетевого устройства прокси-сервера для управления доступом к корпоративным данным с мобильных устройств вне периметра корпоративной сети. Корпорация Майкрософт предлагает решения для защиты служб данных в облаке в наборе тесно интегрированных облачных служб, который представляет собой предложение Enterprise Client + Security.

-   Изучите [распространенные способы использования Intune](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) и начните отвечать на вопросы в разделе об [оценке требований к MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Дальнейшие действия

[Этап 1. Подготовка Intune к управлению мобильными устройствами (MDM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

