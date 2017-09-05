---
title: "Восстановление заводских настроек устройства с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения о том, как восстановить заводские настройки устройств, управляемых в Intune.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fd7273d6c5f75a675d7b01df4225a96fd3a5f821
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Восстановление заводских настроек устройств под управлением Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Сброс параметров** восстанавливает параметры по умолчанию на устройстве. Устройством больше не управляет Intune. Рабочие и личные данные удаляются. Это действие нельзя отменить.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 8.1 и более поздних версий (не устройства, управляемые EAS)
- Windows Phone — поддерживается
- iOS — поддерживается
- macOS — не поддерживается
- Android — поддерживается (Android for Work не поддерживается)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Сброс параметров устройства до заводских настроек

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие удаленного устройства **Сброс параметров**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
