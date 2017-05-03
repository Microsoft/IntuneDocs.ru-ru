---
title: "Блокировка приложений, не поддерживающих современные средства проверки подлинности"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: abfb3912ba6dfa6802e1321782afd155a96fbefc
ms.lasthandoff: 04/19/2017


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

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
[Разрешение доступа к службам Office 365 только для приложений, поддерживаемых Intune](allow-policy-managed-apps-access-to-o365.md)

