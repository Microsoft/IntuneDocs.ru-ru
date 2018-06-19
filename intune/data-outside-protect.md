---
title: Предотвращение несанкционированного доступа к корпоративным данным
titlesuffix: Microsoft Intune
description: Вы можете предотвратить несанкционированный доступ к данным компании при их совместном использовании за пределами корпоративной сети с помощью Microsoft Intune.
keywords: Office 365 Azure Information Protection защита данных за пределами сети данные компании
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6a88573a-aa60-455c-858c-74562798246b
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fa717147d8c5fcc33f350cc16bd4af53a31efc7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020526"
---
# <a name="prevent-unauthorized-access-to-company-data-using-microsoft-intune"></a>Предотвращение несанкционированного доступа к корпоративным данным с помощью Microsoft Intune

Вы можете классифицировать, снабжать метками и защищать документы и сообщения электронной почты Office 365, чтобы только авторизованные пользователи могли получать доступ к этим данным. Управление параметрами осуществляется автоматически после того, как ИТ-администраторы или пользователи зададут правила и условия. Кроме того, ИТ-отдел может предоставить рекомендуемые параметры для пользователей. Администраторы и пользователи также могут отзывать доступ к данным, уже находящимся в общем доступе, без помощи со стороны других уполномоченных лиц. Таким образом, можно контролировать, кто открывает или изменяет защищенные данные, даже в том случае если данные покидают локальную сеть. 

## <a name="before-you-begin"></a>Подготовка к работе

Если в среде выполнены перечисленные ниже требования, вы можете использовать следующий план действий.
* Компания готова к безопасному переходу в облако.
* Компания использует Office 365 Exchange Online, SharePoint Online, OneDrive для бизнеса или Yammer.
* Компания имеет лицензии Microsoft 365, Enterprise Mobility + Security (EMS) и Azure Information Protection.
* В вашей организации используются устройства под управлением Windows 7 с пакетом обновления 1 (SP1) или более поздней версии.
* В компании используется Office 365 профессиональный плюс с приложениями версий 2016 или 2013, Office профессиональный плюс 2016, Office профессиональный плюс 2013 с пакетом обновления 1 (SP1) или Office профессиональный плюс 2010.

## <a name="action-plan"></a>План действий

Выполните [краткое руководство по началу работы со службой Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).  

## <a name="what-to-tell-employees-and-students"></a>Что следует рассказать сотрудникам и учащимся

Расскажите пользователям о том, [как и в каких случаях необходимо защищать документы и сообщения электронной почты, содержащие конфиденциальные сведения](https://docs.microsoft.com/information-protection/deploy-use/help-users).

## <a name="next-steps"></a>Дальнейшие шаги

В рамках следующей процедуры вы узнаете о других способах повышения безопасности данных компании, включая: 

* Узнайте, как использовать [Azure Information Protection на устройствах iOS и Android](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq.
* Если вы используете устройства Mac и Windows Phone, прочитайте о [приложении для управления доступом Microsoft Rights Management](https://technet.microsoft.com/dn451248).
