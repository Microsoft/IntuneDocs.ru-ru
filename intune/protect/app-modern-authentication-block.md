---
title: Блокировка приложений, не поддерживающих современные средства проверки подлинности, в Intune
titleSuffix: Microsoft Intune
description: Дополнительные сведения о приложениях и современных средствах проверки подлинности (ADAL) с использованием Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 81c7746985bd3449ce4e5f2d90780bcd117069eb
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509663"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Для условного доступа на основе приложений, предоставляемого с учетом политик защиты приложений, необходимы приложения, использующие [современные средства проверки подлинности](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) и представляющие собой реализацию протокола OAuth2. Последние версии большинства мобильных и классических приложений Office используют современные средства проверки подлинности. Но есть и сторонние приложения и более старые приложения Office, которые применяют другие средства, такие как обычная проверка подлинности или проверка подлинности на основе форм.

## <a name="block-access-to-apps"></a>Блокировка доступа к приложениям

Чтобы заблокировать доступ к приложениям, которые не используют современную проверку подлинности, используйте политики защиты приложений Intune для реализации условного доступа. Дополнительные сведения см. в статье [Условный доступ на основе приложений с помощью Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Дополнительные сведения

Дополнительные сведения об условном доступе Azure AD см. в следующих статьях и разделах.
- [Что представляет собой условный доступ в Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Принципы реализации условного доступа на основе приложений](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Как настроить SharePoint Online и Exchange Online для условного доступа Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Дальнейшие шаги

- [Условный доступ на основе приложений с помощью Intune](app-based-conditional-access-intune.md)
