---
title: Блокировка устройств с помощью Microsoft Intune в Azure | Документация Майкрософт
description: Используйте действие удаленной блокировки в Microsoft Intune, чтобы заблокировать устройство, защищенное с помощью ПИН-кода или пароля.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Удаленная блокировка устройств с помощью Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Функция **удаленной блокировки** позволяет заблокировать устройство. Чтобы разблокировать устройство, владельцу устройства необходимо ввести секретный код. Удаленно заблокировать можно устройства, для которых задан ПИН-код или пароль. Устройства без ПИН-кода или секретного код нельзя заблокировать удаленно.

## <a name="supported-platforms"></a>Поддерживаемые платформы

Удаленная блокировка поддерживается на указанных ниже платформах.

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 и более поздней версии

Она **не** поддерживается для:
- Windows 10 Desktop

> [!NOTE]
> Для устройств с macOS необходимо задать ПИН-код восстановления из шести цифр. При блокировке в разделе **Обзор устройства** отображается ПИН-код, пока не будет отправлено другое действие устройства.

## <a name="remote-lock-a-device"></a>Удаленная блокировка устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Устройства**, а затем — **Все устройства**.
4. Выберите нужное устройство в списке устройств, а затем укажите действие **Удаленная блокировка**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы отобразились сведения о состоянии действия, выберите **Действия устройства** (Microsoft Intune > Устройства). См. дополнительные сведения о [доступных действиях](device-management.md) по управлению устройствами.