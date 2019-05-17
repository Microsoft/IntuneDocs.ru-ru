---
title: Блокировка приложений, не поддерживающих современные средства проверки подлинности, в Intune
titleSuffix: Microsoft Intune
description: Дополнительные сведения о приложениях и современных средствах проверки подлинности (ADAL) с использованием Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59569107"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Блокировка приложений, не поддерживающих современные средства проверки подлинности (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Для условного доступа на основе приложений, предоставляемого с учетом политик защиты приложений, необходимы приложения, использующие [современные средства проверки подлинности](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) и представляющие собой реализацию протокола OAuth2. Последние версии большинства мобильных и классических приложений Office используют современные средства проверки подлинности. Но есть и сторонние приложения и более старые приложения Office, которые применяют другие средства, такие как обычная проверка подлинности или проверка подлинности на основе форм.

## <a name="block-access-to-apps"></a>Блокировка доступа к приложениям

Чтобы заблокировать доступ к приложениям, которые не используют современную проверку подлинности, используйте политики защиты приложений Intune для реализации условного доступа. Дополнительные сведения см. в статье [Условный доступ на основе приложений с помощью Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Дополнительные сведения

Дополнительные сведения об условном доступе Azure AD см. в следующих статьях и разделах.
- [Что представляет собой условный доступ в Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Принципы реализации условного доступа на основе приложений](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [How to: Block legacy authentication to Azure AD with conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo) (Практическое руководство: блокировка устаревших методов проверки подлинности в AAD с помощью условного доступа)

## <a name="next-steps"></a>Дальнейшие шаги

- [Настройка условного доступа на основе приложений с помощью Intune](app-based-conditional-access-intune.md)
