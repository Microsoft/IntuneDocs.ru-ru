---
title: "Удаление организационных данных с устройств с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения о том, как удалить только организационные данные с устройств, управляемых в Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Удаление организационных данных с управляемых устройств Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Удаление организационных данных** удаляет только организационные данные с устройств под управлением Intune. Не удаляет персональные данные с устройства. Устройством больше не будет управлять Intune. Кроме того, оно больше не сможет обращаться к корпоративным ресурсам (не поддерживается для устройств Windows, присоединенных к Azure Active Directory).

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие удаленного устройства **Удаление организационных данных**.

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
