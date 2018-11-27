---
title: Блокировка приложений, не поддерживающих современные средства проверки подлинности, в Intune
titleSuffix: Microsoft Intune
description: Узнайте о блокировке приложений, не поддерживающих современные средства проверки подлинности (ADAL).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0b74559eb0914d87daabaaad52902547ae7c08ac
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182046"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Для условного доступа на основе приложений, предоставляемого с учетом политик защиты приложений, необходимы приложения, использующие [современные средства проверки подлинности](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) и представляющие собой реализацию протокола OAuth2. Последние версии большинства мобильных и классических приложений Office используют современные средства проверки подлинности. Но есть и сторонние приложения и более старые приложения Office, которые применяют другие средства, такие как обычная проверка подлинности или проверка подлинности на основе форм.

Чтобы заблокировать доступ к этим приложениям, выполните следующие действия:

* Настройте правила утверждений ADFS для блокирования несовременных протоколов проверки подлинности. Подробные инструкции представлены в сценарии 3 — [полная блокировка доступа к Office 365 за исключением браузерных приложений](https://technet.microsoft.com/library/dn592182.aspx).
* Для **Exchange и SharePoint Online** используйте условный доступ Azure Active Directory. Для SharePoint Online используйте командлет Set-SPOTenant. Подробные указания: [Как настроить SharePoint Online и Exchange Online для условного доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>ЦС на основе приложений нельзя использовать с проверкой подлинности на основе сертификатов Azure Active Directory (Azure AD). В текущий момент времени может быть задан только один из этих методов.

### <a name="see-also"></a>См. также:
[Настройка условного доступа на основе приложений с помощью Intune](app-based-conditional-access-intune.md)
