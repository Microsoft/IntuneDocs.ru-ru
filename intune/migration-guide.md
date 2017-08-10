---
title: "Руководство по переходу к управлению мобильными устройствами Intune"
description: "В этом руководстве содержатся разные сведения, посвященные переходу от стороннего поставщика MDM к Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: d86260872230bb0a9274fa302acac5caeaa682a7
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2017
---
# <a name="intune-migration-guide"></a>Руководство по переходу к Intune

![Статья с руководством по переходу к Intune MDM](./media/MDM-migration-guide-art.PNG)

Успешный переход к Intune начинается с создания надежного плана, в котором учитываются текущая среда управления мобильными устройствами (MDM), бизнес-цели и технические требования. Кроме того, необходимо заручиться поддержкой ключевых заинтересованных лиц, которые будут содействовать реализации вашего плана перехода и работать над ним вместе с вами.

В этом руководстве содержатся разные сведения, посвященные переходу от стороннего поставщика MDM к Intune.

## <a name="whats-included-in-this-guide"></a>Что входит в состав этого руководства?

В руководстве представлено два этапа перехода, каждый из которых состоит из задач, стратегий и тактических рекомендаций, которые помогут вам постепенно и комплексно перейти к Intune MDM.

-   [Этап 1. Подготовка Intune к управлению мобильными устройствами](migration-guide-prepare.md)

    -   [Оценка требований к переходу к MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Базовая настройка](migration-guide-setup.md)

    -   [Настройка политик управления устройствами и приложениями](migration-guide-configure-policies.md)

    -   [Настройка политик защиты приложений](migration-guide-app-protection-policies.md)

    -   [Особые примечания о миграции](migration-guide-considerations.md)

-   [Этап 2: кампании по миграции](migration-guide-campaign.md)

    -   [Коммуникационный план](migration-guide-communication-plan.md)

    -   [Реализация в системах конечных пользователей за счет условного доступа](migration-guide-drive-adoption.md)

    -   [Типичный цикл миграции](migration-guide-cycle.md)
        -   [Мониторинг миграции](migration-guide-cycle.md#monitoring-migration)
        -   [Задачи, выполняемые после переноса](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Допущения

-   Вы уже оценили Intune в среде для подтверждения концепции и решили использовать эту службу в качестве решения по управлению мобильными устройствами в своей организации.

-   Вы уже знакомы с Intune и ее функциями.

## <a name="before-you-begin"></a>Подготовка к работе

Важно понять, что новое развертывание Intune может отличаться от старого развертывания MDM. В отличие от традиционных служб MDM, служба Intune ориентирована на управление доступом на основе удостоверений и поэтому не требует сетевого устройства прокси-сервера для управления доступом к корпоративным данным с мобильных устройств вне периметра корпоративной сети. Корпорация Майкрософт предлагает решения для защиты служб данных в облаке, входящие в набор тесно интегрированных облачных служб, который представляет собой предложение Enterprise Client + Security.

-   Ознакомьтесь с [распространенными способами использования Intune](common-scenarios.md).

## <a name="next-steps"></a>Дальнейшие действия

[Этап 1. Подготовка Intune к управлению мобильными устройствами](migration-guide-prepare.md)
