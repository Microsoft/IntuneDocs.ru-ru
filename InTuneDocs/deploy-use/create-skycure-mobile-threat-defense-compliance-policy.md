---
title: "Создание политики соответствия защиты мобильных устройств от угроз Skycure | Документы Майкрософт"
description: "Создание политики соответствия защиты мобильных устройств от угроз Skycure в классической консоли Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 3a7322bd389b6d2ca72108b9f54318000857895b
ms.lasthandoff: 03/22/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Создание политики соответствия защиты мобильных устройств от угроз Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune со службой защиты мобильных устройств от угроз Skycure позволяет обнаруживать угрозы на мобильных устройствах и оценивать соответствующие риски. Можно создать правило Intune для политики соответствия требованиям, которое будет оценивать риски для определения соответствия устройства. Затем можно использовать политику условного доступа, чтобы запретить доступ к службам в зависимости от соответствия устройства требованиям.

## <a name="before-you-begin"></a>Подготовка к работе

Что нужно сделать для политики соответствия требованиям при использовании службы защиты мобильных устройств от угроз Skycure:

-   [настроить интеграцию Skycure и Intune;](https://docs.microsoft.com/en-us/intune/deploy-use/setup-the-skycure-integration-with-Intune)

-   [включить подключения Skycure в Intune.](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

В рамках настройки службы защиты мобильных устройств от угроз Skycure в консоли Skycure создается политика, которая разделяет различные угрозы на категории по уровню угрозы (высокий, средний, низкий). В политике соответствия Intune указывается максимальный допустимый уровень угрозы.

## <a name="to-create-skycure-compliance-policy"></a>Создание политики соответствия Skycure

1.  Перейдите в [классическую консоль Intune](https://manage.microsoft.com/) и введите свои учетные данные.

2.  Выберите пункты **Политика** &gt; **Политики соответствия**. Можно использовать существующую политику соответствия или создать новую.

3.  Выберите пункты **Добавить** &gt; **Работоспособность устройства**, затем включите **Защиту устройства от угроз**.

4.  Выберите **Максимально допустимый уровень угроз**:

    а.  **Нет (защищено)**. Этот уровень обеспечивает максимальную защиту. Устройство не может осуществлять доступ к ресурсам компании при наличии каких-либо угроз. При обнаружении любых угроз устройство переходит в состояние несоответствия.

    b.  **Низкий**. Если обнаруженные на устройстве угрозы имеют низкий уровень, считается, что устройство соответствует требованиям. Любая угроза с уровнем выше низкого переводит устройство в состояние несоответствия.

    в.  **Средний**. Если обнаруженные на устройстве угрозы имеют низкий или средний уровень, считается, что устройство соответствует требованиям. Если на устройстве найдены угрозы с высоким уровнем, устройство переходит в состояние несоответствия.

    г.  **Высокий** — это наименее безопасный вариант. При этом допустимы все уровни угроз, а защита мобильных устройств от угроз Skycure используется только для создания отчетов.

> [!IMPORTANT] 
> При создании политик условного доступа для Office 365 и других служб такая оценка соответствия принимается во внимание, и доступ несоответствующих устройств к указанным службам блокируется до устранения угрозы.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Дальнейшие шаги

-   Создание политики условного доступа для:

    -   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Локальная организация Exchange](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype для бизнеса Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

