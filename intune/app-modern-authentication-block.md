---
title: "Блокировка приложений, не поддерживающих современные средства проверки подлинности, в Intune"
titleSuffix: Microsoft Intune
description: "Узнайте о блокировке приложений, не поддерживающих современные средства проверки подлинности (ADAL)."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 798a1552e27d21c699e1ac8f22fedbad4b7c624e
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Для условного доступа на основе приложений, предоставляемого с учетом политик защиты приложений, необходимы приложения, использующие [современные средства проверки подлинности](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) и представляющие собой реализацию протокола OAuth2. Большинство современных мобильных и классических приложений Office используют современные средства проверки подлинности, однако существуют сторонние приложения и более старые приложения Office, которые применяют другие методы проверки подлинности, такие как обычная проверка подлинности или проверка подлинности на основе форм.

Чтобы заблокировать доступ к этим приложениям, выполните следующие действия:

* Настройте правила утверждений ADFS для блокирования несовременных протоколов проверки подлинности. Подробные инструкции представлены в сценарии 3 — [полная блокировка доступа к Office 365 за исключением браузерных приложений](https://technet.microsoft.com/library/dn592182.aspx).
* Для отключения проверки подлинности с помощью несовременных протоколов для службы **SharePoint Online** используйте командлет PowerShell [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx), чтобы присвоить свойству проверки подлинности с помощью несовременных протоколов значение false:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>ЦС на основе приложений нельзя использовать с проверкой подлинности на основе сертификатов Azure Active Directory (Azure AD). В текущий момент времени может быть задан только один из этих методов.

### <a name="see-also"></a>См. также:
[Настройка условного доступа на основе приложений с помощью Intune](app-based-conditional-access-intune.md)
