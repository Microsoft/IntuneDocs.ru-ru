---
title: "Условный доступ с Intune"
titlesuffix: Azure portal
description: "Здесь содержатся сведения о том, как определить условия, которым должны отвечать пользователи и устройства для доступа к корпоративным ресурсам в Microsoft Intune.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1cd12a105142d5e537da487e3bd9297ef83ddcb3
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="whats-conditional-access"></a>Что такое условный доступ?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

В этой статье описывается условный доступ, его применение в Enterprise Mobility + Security (EMS), а также распространенные сценарии использования условного доступа в Intune.

Технология условного доступа в Enterprise Mobility + Security (EMS) не является автономным продуктом и используется всеми службами и продуктами в составе решения EMS. Она обеспечивает детализированное управление доступом для эффективной защиты корпоративных данных, гарантируя при этом максимально продуктивную работу пользователей на любом устройстве и из любого места.

Вы можете определить условия, ограничивающие доступ к вашим корпоративным данным на основе расположения, состояния устройства и пользователя, а также конфиденциальности приложения.

> [!NOTE] 
> Условный доступ также расширяет возможности [служб Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Архитектурная схема условного доступа](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Условный доступ с Intune

Intune расширяет возможности решения условного доступа EMS, дополняя их политиками соответствия мобильных устройств и управления приложениями.

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

## <a name="next-steps"></a>Дальнейшие действия

[Стандартные способы использования условного доступа с помощью Intune](conditional-access-intune-common-ways-use.md)
