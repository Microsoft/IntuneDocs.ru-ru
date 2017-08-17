---
title: "Удаление организационных данных с устройств с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения о том, как удалить только организационные данные с устройств, управляемых в Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b0cc7d62770057ff9df5a36e6e5df58b29430534
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Удаление организационных данных с управляемых устройств Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие устройства **Удаление организационных данных** удаляет только организационные данные с устройств под управлением Intune. Оно не удаляет персональные данные с устройства. После удаления устройство больше не управляется Intune и не может получать доступ к корпоративным ресурсам.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается (не поддерживается для устройств Windows, которые присоединены к Azure Active Directory)
- Windows Phone — поддерживается
- iOS — поддерживается
- macOS — поддерживается
- Android — поддерживается

## <a name="how-to-remove-company-data"></a>Удаление организационных данных

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие удаленного устройства **Удаление организационных данных**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
