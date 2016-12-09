---
title: "Условный доступ на базе приложений к 0365 | Microsoft Intune"
description: "Объяснение того, как MAM CA может помочь в управлении доступом приложений к службам Office 365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: c966d955365611781e83eea9f2aec743f0fc0321


---

# <a name="allow-only-mobile-apps-that-support-intune-mam-policies-to-access-office-365-services"></a>Позволяет обращаться к службам Office 365 только мобильным приложениям, поддерживающим политики Intune MAM
[Политики управления мобильными приложениями (MAM) Intune](protect-apps-and-data-with-microsoft-intune.md) помогают защитить данные компании на устройствах, зарегистрированных для управления в Intune. Политики MAM также можно использовать на **устройствах, принадлежащих сотрудникам, которые не зарегистрированы для управления в Intune**.  В этом случае, даже если контроля над устройством нет, все равно необходимо обеспечить защиту данных и ресурсов компании. С помощью условного доступа для MAM (MAM CA) можно создать политику, которая позволяет обращаться к службам Office 365, таким как Exchange Online, только мобильным приложениям, поддерживающим политики Intune MAM.

Например, разрешив обращаться к Exchange Online только **приложению Microsoft Outlook**, можно **блокировать работу встроенных почтовых приложений на iOS и Android**, которые не имеют защиты данных на базе политик Intune MAM при получении сообщений электронной почты из **Exchange Online**.

На следующей схеме показан поток, с помощью которого политики MAM CA определяют, когда нужно разрешать, а когда блокировать доступ: ](../media/mam-ca-decision-flow_simple.png)Схема различных критериев предоставления или блокировки доступа![.

Описание сокращений, используемых на схемах:
* **CP**: приложение корпоративного портала
* **AA**: приложение для проверки подлинности Azure
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Необходимые компоненты
**Перед** настройкой политики MAM CA необходимо установить набор **Enterprise Mobility + Security или оформить премиальную подписку Azure Active Directory**, а у пользователей должна быть лицензия на работу с EMS или Azure AD. Дополнительные сведения см. на странице [Цены Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) или [Цены Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## <a name="supported-apps"></a>Поддерживаемые приложения
**Exchange Online**: **Microsoft Outlook** для Android и iOS.

Дополнительные сведения о взаимодействии с пользователем в приложении с политиками MAM CA см. в статье [Что произойдет при использовании приложения с MAM CA](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Дальнейшие шаги
[Создание политики Exchange Online для приложений MAM](mam-ca-for-exchange-online.md)

[Блокировка приложений, не поддерживающих современные средства проверки подлинности](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>См. также

[Защита данных приложения с помощью политик MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


