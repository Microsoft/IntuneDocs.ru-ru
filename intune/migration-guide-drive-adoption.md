---
title: "Реализация в системах конечных пользователей за счет условного доступа"
description: "В этой статье представлены сведения о том, как привлечь пользователей к регистрации в Intune за счет условного доступа."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Реализация в системах конечных пользователей за счет условного доступа

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

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

-   Дополнительные сведения об [условном доступе](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Список задач для условного доступа

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Задача 1. Выбор способа реализации условного доступа

[Стандартные способы использования условного доступа](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>Задача 2. Настройка условного доступа Intune

Выберите один из следующих вариантов.

-   [Настройка условного доступа в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Установка локального соединителя Exchange с помощью Intune](/intune/exchange-connector-install)

-   [Настройка политик условного доступа на базе приложений для Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Настройка политик условного доступа на базе приложений для SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Дальнейшие действия

[Типичный цикл миграции](migration-guide-cycle.md)
