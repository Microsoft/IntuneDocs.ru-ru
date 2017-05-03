---
title: "Условный доступ на базе приложений к 0365"
description: "Объяснение того, как MAM CA может помочь в управлении доступом приложений к службам Office 365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 8fc53e8717277a4075bc7ecde31fd60c3539a5f7
ms.lasthandoff: 04/19/2017


---

# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Предоставление доступа к службам Office 365 только мобильным приложениям, которые поддерживают политики защиты приложений Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Политики защиты приложений Intune](protect-apps-and-data-with-microsoft-intune.md) помогают защитить данные компании на устройствах, зарегистрированных для управления в Intune. Политики защиты приложений также можно использовать на **устройствах, принадлежащих сотрудникам, которые не зарегистрированы для управления в Intune**.  В этом случае, даже если контроля над устройством нет, все равно необходимо обеспечить защиту данных и ресурсов компании. Используя условный доступ на основе приложений с MAM, можно создать политику, которая позволяет обращаться к службам Office 365, таким как Exchange Online, только мобильным приложениям, поддерживающим политики защиты приложений Intune.

Например, разрешив обращаться к Exchange Online только **приложению Microsoft Outlook**, можно **блокировать работу встроенных почтовых приложений на iOS и Android**, которые не имеют защиты данных на базе политик Intune MAM при получении сообщений электронной почты из **Exchange Online**. Или вы можете блокировать мобильным приложениям без поддержки Intune MAM доступ к **SharePoint Online**.

На следующей схеме показан поток, с помощью которого политики условного доступа на основе приложений определяют, когда нужно разрешать, а когда блокировать доступ: ![Схема различных критериев предоставления или блокировки доступа](../media/mam-ca-decision-flow_simple.png).

Описание сокращений, используемых на схемах:
* **CP**: приложение корпоративного портала
* **AA**: приложение для проверки подлинности Azure
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Необходимые компоненты
**Перед** настройкой политики условного доступа на основе приложений необходимо установить набор **Enterprise Mobility + Security или оформить премиальную подписку Azure Active Directory**, а у пользователей должна быть лицензия на работу с EMS или Azure AD. Дополнительные сведения см. на странице [Цены Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) или [Цены Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Поддерживаемые приложения
**Exchange Online**:
* **Microsoft Outlook** для Android и iOS.

**SharePoint Online**
* Microsoft Word для iOS и Android
* Microsoft Excel для iOS и Android
* Microsoft PowerPoint для iOS и Android
* Microsoft OneDrive для бизнеса для iOS и Android
* Microsoft OneNote для iOS

>[!IMPORTANT]
>Для устройств Android первоначальная регистрация выполняется с помощью входа в приложение OneDrive или Outlook. Приложение OneNote для Android пока не поддерживают MAM без регистрации.

Дополнительные сведения о взаимодействии с пользователем в приложении с политиками условного доступа на основе приложений см. в статье [Что произойдет при использовании приложения с MAM CA](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Дальнейшие действия
[Создание политики Exchange Online для приложений MAM](mam-ca-for-exchange-online.md)

[Создание политики SharePoint Online для приложений MAM](mam-ca-for-sharepoint-online.md)

[Блокировка приложений, не поддерживающих современные средства проверки подлинности](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>См. также

[Защита данных приложений с помощью политик защиты приложений](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

