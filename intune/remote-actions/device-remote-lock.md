---
title: Блокировка устройств с помощью Microsoft Intune в Azure | Документация Майкрософт
description: Используйте действие удаленной блокировки в Microsoft Intune, чтобы заблокировать устройство, защищенное с помощью ПИН-кода или пароля.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bce5a89ecc49952f5c21536c429e9cd3309b13c3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "73712272"
---
# <a name="remotely-lock-devices-with-intune"></a>Удаленная блокировка устройств с помощью Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Действие устройства **Удаленная блокировка** позволяет заблокировать устройство. Чтобы разблокировать устройство, владельцу устройства необходимо ввести секретный код. Удаленно заблокировать можно устройства, для которых задан ПИН-код или пароль. Устройства без ПИН-кода или пароля нельзя заблокировать удаленно.

## <a name="supported-platforms"></a>Поддерживаемые платформы

**Удаленная блокировка** поддерживается на указанных ниже платформах.

- Android
- Корпоративные устройства с Android для киосков
- Устройства с рабочим профилем Android для бизнеса
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 и более поздней версии

**Удаленная блокировка** не поддерживается для следующих систем:
- Windows 10 Desktop

> [!NOTE]
> Для устройств с macOS необходимо задать ПИН-код восстановления из шести цифр. При блокировке устройства в разделе **Обзор устройства** отображается ПИН-код, пока не будет отправлено другое действие устройства.

## <a name="remote-lock-a-device"></a>Удаленная блокировка устройства

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Выберите **Устройства** > **Все устройства**.
4. Выберите нужное устройство в списке устройств, а затем укажите действие **Удаленная блокировка**.

## <a name="next-steps"></a>Дальнейшие шаги

- Чтобы отобразились сведения о состоянии действия, выберите **Microsoft Intune** > **Устройства** > **Действия устройства**. 
- Дополнительные действия по управлению устройствами см. в статье о [доступных действиях](device-management.md).
