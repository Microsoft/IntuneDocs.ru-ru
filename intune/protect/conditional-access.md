---
title: Условный доступ с помощью Microsoft Intune
titleSuffix: Microsoft Intune
description: Узнайте, как определить условия, которым должны отвечать пользователи, устройства и приложения для доступа к корпоративным ресурсам в Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: cef8bcf74509d83b076b30a1ee7f2406e622b129
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722648"
---
# <a name="learn-about-conditional-access-and-intune"></a>Дополнительные сведения об условном доступе и Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Условный доступ — это способ управления устройствами и приложениями, которым разрешено подключаться к вашей электронной почте и ресурсам компании. В этой статье описывается условный доступ для устройств и приложений и приводятся распространенные сценарии использования условного доступа в Intune.

Технология условного доступа в Enterprise Mobility + Security (EMS) не является автономным продуктом и используется всеми службами и продуктами в составе решения EMS. Она обеспечивает детализированное управление доступом для эффективной защиты корпоративных данных, гарантируя при этом максимально продуктивную работу пользователей на любом устройстве и из любого места.

Вы можете определить условия, ограничивающие доступ к вашим корпоративным данным на основе расположения, состояния устройства и пользователя, а также конфиденциальности приложения.

> [!NOTE] 
> Условный доступ также расширяет возможности [служб Office 365](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Архитектурная схема условного доступа](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Условный доступ с помощью Intune

Условный доступ — это функция Azure Active Directory, которая входит в лицензию Azure Active Directory Premium. Intune расширяет эту возможность, добавляя в решение средства для обеспечения соответствия мобильных устройств и для управления мобильными приложениями. 

![Intune и условный доступ при использовании EMS](./media/conditional-access/intune-with-ca-1.png)

Способы использования условного доступа с помощью Intune:

- **Условный доступ на основе информации об устройстве**

  - Условный доступ для локальной организации Exchange

  - Условный доступ на основе управления доступом к сети

  - Условный доступ на основе сведений о рисках для устройства

  - Условный доступ для ПК под управлением Windows

    - Корпоративные устройства

    - Принеси свое устройство (BYOD)

- **Условный доступ на основе приложений**

## <a name="next-steps"></a>Дальнейшие шаги

[Каковы стандартные способы использования условного доступа с помощью Intune?](conditional-access-intune-common-ways-use.md)
