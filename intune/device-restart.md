---
title: "Удаленный перезапуск устройств с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения о том, как удаленно перезапустить устройство с помощью соответствующего действия.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5278179f22d174de6e97aa990bbe8761d8c8f8f8
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2017
---
# <a name="remotely-restart-devices-with-intune"></a>Удаленный перезапуск устройств с помощью Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Перезапуск** позволяет перезапустить выбранное устройство. Владелец устройства не получает автоматическое уведомление о перезапуске устройства, поэтому возможна потеря несохраненных данных.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 8.1 и более поздних версиях
- Windows Phone — поддерживается в Windows Phone 8.1 и более поздних версиях
- iOS — не поддерживается
- macOS — не поддерживается
- Android — не поддерживается

## <a name="how-to-restart-a-device"></a>Перезапуск устройства

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие **Перезапуск**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
