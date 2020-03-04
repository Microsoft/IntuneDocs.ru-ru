---
title: Блокировка устройств с помощью Microsoft Intune в Azure | Документация Майкрософт
description: Используйте действие удаленной блокировки в Microsoft Intune, чтобы заблокировать устройство, защищенное с помощью ПИН-кода или пароля.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
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
ms.openlocfilehash: 3a0e3d22e6fe39cd2c0091b0399ea165007fc689
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781874"
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
- MacOS
- Windows 10 Mobile
- Windows Phone 8.1 и более поздней версии

**Удаленная блокировка** не поддерживается для следующих систем:
- Windows 10 Desktop

> [!NOTE]
> Для устройств с macOS необходимо задать ПИН-код восстановления из шести цифр. При блокировке устройства в разделе **Обзор устройства** отображается ПИН-код, пока не будет отправлено другое действие устройства.

## <a name="remote-lock-a-device"></a>Удаленная блокировка устройства

1. Войдите в [Центр администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Выберите **Устройства** > **Все устройства**.
4. Выберите нужное устройство в списке устройств, а затем укажите действие **Удаленная блокировка**.

## <a name="next-steps"></a>Дальнейшие шаги

- Чтобы отобразились сведения о состоянии действия, выберите **Microsoft Intune** > **Устройства** > **Действия устройства**. 
- Дополнительные действия по управлению устройствами см. в статье о [доступных действиях](device-management.md).
