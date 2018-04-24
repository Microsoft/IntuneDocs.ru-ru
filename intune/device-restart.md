---
title: Перезапуск устройств с помощью Microsoft Intune в Azure | Документы Майкрософт
description: Перезапуск устройств iOS и Windows с помощью Microsoft Intune на портале Azure с помощью удаленного действия "Перезапуск".
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8aadebceed9c58717801b374a3a5d776926343
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Удаленный перезапуск устройств с помощью Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Действие **Перезапуск** позволяет перезапустить выбранное устройство. Владелец устройства не получает автоматическое уведомление о перезапуске устройства, поэтому возможна потеря несохраненных данных.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 8.1 и более поздних версиях
- Windows Phone — поддерживается в Windows Phone 8.1 и более поздних версиях
- iOS — поддерживается

    > [!Note]  
    > Для выполнения этой команды требуются защищенные устройства и право доступа **Блокировка устройства**. Устройство перезапускается немедленно. Устройства iOS, заблокированные с помощью секретного кода, не подключаются повторно к сети Wi-Fi после перезапуска. После перезапуска у устройства может отсутствовать доступ к серверу.
- macOS — не поддерживается
- Android — не поддерживается

## <a name="restart-a-device"></a>Перезапуск устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Устройства** > **Все устройства**.
4. Выберите нужное устройство в списке управляемых устройств, а затем нажмите **...Еще** и выберите удаленное действие **Перезапуск**.

## <a name="next-steps"></a>Дальнейшие шаги

- Чтобы отобразились сведения о состоянии действия **Перезапуск**, выберите **Устройства** > **Действия устройства**.
