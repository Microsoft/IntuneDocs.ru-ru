---
title: "Удаленная блокировка управляемых устройств с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения о том, как удаленно блокировать управляемые устройства с помощью Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab885fa6f693e65295986c182353f4918024281f
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Удаленная блокировка управляемых устройств с помощью Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Функция **удаленной блокировки** позволяет заблокировать выбранное устройство. Чтобы его разблокировать, владельцу устройства необходимо ввести секретный код. Удаленно заблокировать можно только устройство, для которого задан ПИН-код или пароль.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — не поддерживается
- Windows Phone — поддерживается в Windows Phone 8.1 и более поздних версиях
- iOS — поддерживается
- macOS — не поддерживается
- Android — поддерживается

## <a name="how-to-remote-lock-a-device"></a>Удаленная блокировка устройства

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие **Удаленная блокировка**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
