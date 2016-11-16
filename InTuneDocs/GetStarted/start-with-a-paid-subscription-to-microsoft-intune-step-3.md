---
title: "Синхронизация Active Directory и добавление пользователей в Intune | Microsoft Intune"
description: "Синхронизация локальных пользователей с Azure AD и предоставление разрешений администратора для подписки Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: 786aa2a665a881d13412ecc2d247a8b79a6d09f8


---


# Синхронизация Active Directory и добавление пользователей в Intune
Можно настроить синхронизацию каталогов для импорта учетных записей пользователей из локальной службы Active Directory в Microsoft Azure Active Directory (Azure AD). Соединение локальной службы Active Directory со всеми вашими службами, использующими Azure Active Directory, существенно упрощает управление удостоверениями пользователей. Можно также настроить единый вход, чтобы взаимодействие с пользователями при проверке подлинности происходило просто и привычно.

При использовании нескольких служб с одним и тем же [клиентом Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) ранее синхронизированные учетные записи пользователей доступны всем облачным службам с общей подпиской клиента Azure AD, что еще больше упрощает работу.

## Синхронизация локальных пользователей с помощью Azure AD
Для синхронизации учетных записей пользователей с Azure AD нужно всего одно средство — [Мастер Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Мастер Azure AD Connect — это удобное средство для подключения локальной инфраструктуры удостоверений к облаку.  Выберите топологию и потребности (один или несколько каталогов, синхронизация паролей или федерация), и мастер сможет развернуть и настроить все компоненты, необходимые для работы подключения. Сюда входят службы синхронизации, службы федерации Active Directory (AD FS) и модуль Azure AD PowerShell.

> [!TIP]
> Azure AD Connect включает в себя функции, которые ранее выпускались как Dirsync и Azure AD Sync. См. дополнительные сведения об [интеграции каталогов](http://technet.microsoft.com/library/jj573653.aspx). Дополнительные сведения о преимуществах синхронизации учетных записей пользователей из локального каталога c Azure AD см. в статье [Сходство Active Directory и Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Назначение прав администратора
После добавления пользователей в подписку рекомендуется назначить некоторым из них [учетные данные администратора](administrative-accounts-websites-perms.md). Консоль, которая будет использоваться для назначения административных учетных данных, зависит от типа администратора.

-   **Администратор клиента**: используйте **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]**, чтобы назначить эту роль администратора для управления подпиской, включая выставление счетов, облачное хранилище и управление пользователями, которым разрешено использовать [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Администратор служб**: используйте **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]**, чтобы назначить эту роль администратора для выполнения повседневных задач, включая управление мобильными устройствами и компьютерами, развертывание политик и ПО и выполнение отчетов.


### Дальнейшие действия
Поздравляем! Вы завершили шаг 3 *краткого руководства по Intune*.

>[!div class="step-by-step"]

>[&larr; **Параметры домена**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md) [**Управление лицензиями Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Oct16_HO4-->


