---
title: "Блокировка приложений, не поддерживающих современные средства проверки подлинности, в Intune"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fbdb9d6e7e1869aba12b3639b8e887401491a79
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Для условного доступа на основе приложений, предоставляемого с учетом политик защиты приложений, необходимы приложения, использующие [современные средства проверки подлинности](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) и представляющие собой реализацию протокола OAuth2. Большинство современных мобильных и настольных приложений Office используют современные средства проверки подлинности, однако существуют сторонние приложения и более старые приложения Office, которые применяют другие методы проверки подлинности, такие как обычная проверка подлинности или проверка подлинности на основе форм.

Чтобы заблокировать доступ к этим приложениям, выполните следующие действия:

* Настройте правила утверждений ADFS для блокирования несовременных протоколов проверки подлинности. Подробные инструкции представлены в сценарии 3 — [полная блокировка доступа к Office 365 за исключением браузерных приложений](https://technet.microsoft.com/library/dn592182.aspx).
* Для отключения проверки подлинности с помощью несовременных протоколов для службы **SharePoint Online** используйте командлет PowerShell [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx), чтобы присвоить свойству проверки подлинности с помощью несовременных протоколов значение false:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>Центр сертификации на основе приложений нельзя использовать с проверкой подлинности на основе сертификатов Azure Active Directory (Azure AD). В текущий момент времени может быть задан только один из этих методов.

### <a name="see-also"></a>См. также
[Настройка условного доступа на основе приложений с помощью Intune](app-based-conditional-access-intune.md)