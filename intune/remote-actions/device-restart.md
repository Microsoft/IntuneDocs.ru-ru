---
title: Перезапуск устройств с помощью Microsoft Intune в Azure | Документы Майкрософт
description: Перезапуск устройств iOS, iPadOS и Windows с помощью Microsoft Intune на портале Azure с помощью удаленного действия "Перезапуск".
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
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6312a71ecd341bf52057af4d3fb7c1b796b89d1
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781995"
---
# <a name="remotely-restart-devices-with-intune"></a>Удаленный перезапуск устройств с помощью Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Действие **Перезапустить** позволяет перезапустить выбранное устройство (в течение 5 минут). Владелец устройства не получает автоматическое уведомление о перезапуске устройства, поэтому возможна потеря несохраненных данных.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 8.1 и более поздних версиях
- Windows Phone — поддерживается в Windows Phone 8.1 и более поздних версиях
- Киоски Android — поддерживается в Android 7.0 и более поздних версиях
- iOS и iPadOS — поддерживается

    > [!Note]  
    > Для выполнения этой команды требуются защищенные устройства и право доступа **Блокировка устройства**. Устройство перезапускается немедленно. Устройства iOS и iPadOS, заблокированные с помощью секретного кода, не подключаются повторно к сети Wi-Fi после перезапуска. После перезапуска у устройства может отсутствовать доступ к серверу.
- macOS — не поддерживается
- Устройства Android и устройства с рабочим профилем Android — не поддерживается

## <a name="restart-a-device"></a>перезапускать устройство;

1. Войдите в [Центр администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Выберите **Устройства** > **Все устройства**.
4. Выберите нужное устройство в списке управляемых устройств > **Перезапустить** > **Да**.

## <a name="next-steps"></a>Дальнейшие шаги

- Чтобы отобразились сведения о состоянии действия **Перезапуск**, выберите **Устройства** > **Действия устройства**.
