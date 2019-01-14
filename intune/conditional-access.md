---
title: Условный доступ с помощью Microsoft Intune | Microsoft Intune
description: Узнайте, как определить условия, которым должны отвечать пользователи, устройства и приложения для доступа к корпоративным ресурсам в Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: f25fe74c9506d2179c683156821ef9afb218128a
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816571"
---
# <a name="whats-conditional-access"></a>Что такое условный доступ?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Условный доступ — это способ управления устройствами и приложениями, которым разрешено подключаться к вашей электронной почте и ресурсам компании. В этой статье описывается условный доступ для устройств и приложений и приводятся распространенные сценарии использования условного доступа в Intune.

Технология условного доступа в Enterprise Mobility + Security (EMS) не является автономным продуктом и используется всеми службами и продуктами в составе решения EMS. Она обеспечивает детализированное управление доступом для эффективной защиты корпоративных данных, гарантируя при этом максимально продуктивную работу пользователей на любом устройстве и из любого места.

Вы можете определить условия, ограничивающие доступ к вашим корпоративным данным на основе расположения, состояния устройства и пользователя, а также конфиденциальности приложения.

> [!NOTE] 
> Условный доступ также расширяет возможности [служб Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Архитектурная схема условного доступа](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Условный доступ с Intune

Условный доступ — это функция Azure Active Directory, которая входит в лицензию Azure Active Directory Premium. Intune расширяет эту возможность, добавляя в решение средства для обеспечения соответствия мобильных устройств и для управления мобильными приложениями. 

![Intune и условный доступ при использовании EMS](./media/intune-with-ca-1.png)

Способы использования условного доступа с помощью Intune:

-   **Условный доступ на основе информации об устройстве**

    -   Условный доступ для локальной организации Exchange

    -   Условный доступ на основе управления доступом к сети

    -   Условный доступ на основе сведений о рисках для устройства

    -   Условный доступ для ПК под управлением Windows

        -   Корпоративные устройства

        -   Принеси свое устройство (BYOD)

-   **Условный доступ на основе приложений**

## <a name="next-steps"></a>Дальнейшие шаги

[Стандартные способы использования условного доступа с помощью Intune](conditional-access-intune-common-ways-use.md)
