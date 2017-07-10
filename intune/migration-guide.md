---
title: "Руководство по переходу к управлению мобильными устройствами Intune"
description: "В этом руководстве представлены различные сведения, связанные с переходом от стороннего поставщика MDM к Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Руководство по переходу к Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Статья с руководством по переходу к Intune MDM](./media/MDM-migration-guide-art.PNG)

Успешный переход к Intune начинается с создания надежного плана, в котором учитываются текущая среда управления мобильными устройствами (MDM), бизнес-цели и технические требования. Кроме того, необходимо заручиться поддержкой ключевых заинтересованных лиц, которые будут содействовать реализации вашего плана перехода и работать над ним вместе с вами.

В этом руководстве представлены различные сведения, связанные с переходом от стороннего поставщика MDM к Intune.

## <a name="whats-included-in-this-guide"></a>Что входит в состав этого руководства?

В руководстве представлено два этапа, каждый из которых состоит из задач, стратегий и тактических рекомендаций, которые помогут вам постепенно и комплексно перейти к Intune MDM.

-   [Этап 1. Подготовка Intune к управлению мобильными устройствами] (migration-guide-prepare.md)

    -   [Оценка требований к переходу к MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Базовая настройка](migration-guide-setup.md)

    -   [Настройка политик управления устройствами и приложениями](migration-guide-configure-policies.md)

    -   [Настройка политик защиты приложений] (migration-guide-app-protection-policies.md)

    -   [Особые примечания о миграции](migration-guide-considerations.md)

-   [Этап 2. Кампания по миграции](migration-guide-campaign.md)

    -   [План распространения сведений](migration-guide-communication-plan.md)

    -   [Реализация в системах конечных пользователей за счет условного доступа](migration-guide-drive-adoption.md)
    
    -   [Типичный цикл миграции](migration-guide-cycle.md)
        -   [Мониторинг миграции](migration-guide-cycle.md#monitoring-migration)
        -   [Задачи, выполняемые после переноса](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Допущения

-   Вы уже оценили Intune в среде для подтверждения концепции и решили использовать эту службу в качестве решения по управлению мобильными устройствами в своей организации.

-   Вы уже знакомы с Intune и ее функциями. 

> [!NOTE]
> Изучите [руководство по оценке Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune), если хотите более подробно ознакомиться с Intune перед миграцией.

## <a name="before-you-begin"></a>Подготовка к работе

Важно понять, что новое развертывание Intune может отличаться от старого развертывания MDM. В отличие от традиционных служб MDM, служба Intune ориентирована на управление доступом на основе удостоверений и поэтому не требует сетевого устройства прокси-сервера для управления доступом к корпоративным данным с мобильных устройств вне периметра корпоративной сети. Корпорация Майкрософт предлагает решения для защиты служб данных в облаке в наборе тесно интегрированных облачных служб, который представляет собой предложение Enterprise Client + Security.

-   Ознакомьтесь с [распространенными способами использования Intune](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="next-steps"></a>Дальнейшие действия

[Этап 1. Подготовка Intune к управлению мобильными устройствами] (migration-guide-prepare.md)
