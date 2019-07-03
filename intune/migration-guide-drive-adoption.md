---
title: Реализация в системах конечных пользователей за счет условного доступа
titleSuffix: Microsoft Intune
description: Сведения об использовании условного доступа для регистрации в Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2bedaf279d65ee1ed7f8dda4e8d866fb848bade7
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044585"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Реализация в системах конечных пользователей за счет условного доступа в Microsoft Intune

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


Это один из многих подходов. Вы можете выбрать простой процесс, при котором предоставление условного доступа откладывается до регистрации на каждом этапе, или более строгий процесс, при котором условный доступ применяется с самого начала, а для доступа требуется полное соответствие требованиям.

-   Дополнительные сведения об [условном доступе](conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Список задач для условного доступа

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Задача 1. Выбор способа реализации условного доступа

[Стандартные способы использования условного доступа](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>Задача 2. Настройка условного доступа Intune

Выберите один из следующих вариантов.

-   [Настройка условного доступа в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   [Установка локального соединителя Exchange с помощью Intune](exchange-connector-install.md)

-   [Настройка политик условного доступа на основе приложений для Exchange Online](app-based-conditional-access-intune-create.md).

-   [Настройка политик условного доступа на базе приложений для SharePoint Online](app-based-conditional-access-intune-create.md).

-   [Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)](app-modern-authentication-block.md)

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения о типичном цикле миграции см. [здесь](migration-guide-cycle.md).
