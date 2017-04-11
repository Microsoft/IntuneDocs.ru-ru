---
title: "Реализация в системах конечных пользователей за счет условного доступа | Документация Майкрософт"
description: "В этой статье представлены сведения о том, как привлечь пользователей к регистрации в Intune за счет условного доступа."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 26d11bc64802005bcce8cc1962d531af6ffe5cd5
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Этап 2. Реализация в системах конечных пользователей за счет условного доступа

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Включение функций условного доступа с помощью Intune, таких как блокирование электронной почты с устройств, регистрация которых отменена, может помочь заинтересовать пользователей в регистрации и обеспечении соответствия, но это не требуется для успешной миграции. Успех определяют цели внедрения миграции и требования к безопасности.

## <a name="migration-campaign-with-conditional-access"></a>Кампания по миграции и условный доступ

Ниже приведен типичный подход к повышению эффективности кампании по миграции за счет условного доступа.

1.  Задайте правила условного доступа, применяемые ко всем пользователям, но исключите пользователей, которым необходимо выполнить миграцию из старого поставщика MDM. Вы можете создать группу пользователей Azure AD со всеми пользователями, исключенными для условного доступа.

2.  При миграции пользователей удалите их из группы исключений условного доступа.

3.  По завершении миграции настройте для всех политик условного доступа блокировку по умолчанию (если в Intune доступ не разрешен).

### <a name="advantages"></a>Преимущества

-   Вы можете управлять доступом для новых учетных записей пользователей или учетных записей пользователей, которыми не управляло предыдущее решение.

-   Пользователи предыдущего решения получают отсрочку для миграции.

-   Снижение производительности сводится к минимуму.

### <a name="disadvantages"></a>Недостатки

-   Пользователи предыдущих решений потенциально могут обращаться к ресурсам с неуправляемых устройств до включения условного доступа.

> [!TIP] 
> Это один из многих подходов. Вы можете выбрать простой процесс, при котором предоставление условного доступа откладывается до регистрации на каждом этапе, или более строгий процесс, при котором условный доступ применяется с самого начала, а для доступа требуется полное соответствие требованиям.

-   Дополнительные сведения об [условном доступе](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access).

## <a name="task-list-for-conditional-access"></a>Список задач для условного доступа

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Задача 1. Подготовка к условному доступу Intune

-   Узнайте, [как настроить условный доступ](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-setup-intune-conditional-access"></a>Задача 2. Настройка условного доступа Intune

Ниже представлены ссылки, по которым можно получить дополнительные сведения о типах политик условного доступа.

-   [Защита доступа к электронной почте в Exchange Online и новой выделенной среде Exchange Online при помощи Intune](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Защита доступа к электронной почте в локальной организации Exchange и прежней выделенной среде Exchange Online при помощи Intune](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype для бизнеса Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Защита доступа к электронной почте при помощи Microsoft Intune: ситуации-примеры](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Дальнейшие действия

[Этап 2. Типичный цикл миграции](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)

