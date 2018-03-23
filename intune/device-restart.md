---
title: Удаленный перезапуск устройств с помощью Intune
titlesuffix: Microsoft Intune
description: Сведения о том, как удаленно перезапустить устройство с помощью соответствующего действия в Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bd5a01b8aac91c3bd6ea033d62d41e19aab65f8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Удаленный перезапуск устройств с помощью Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Перезапуск** позволяет перезапустить выбранное устройство. Владелец устройства не получает автоматическое уведомление о перезапуске устройства, поэтому возможна потеря несохраненных данных.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 8.1 и более поздних версиях
- Windows Phone — поддерживается в Windows Phone 8.1 и более поздних версиях
- iOS — поддерживается

    > [!Note]  
    > Для выполнения этой команды требуются защищенные устройства и право доступа **Блокировка устройства**. Устройство перезапускается немедленно. Устройства iOS, защищенные секретным кодом, после перезапуска не будут повторно подключены к сети Wi-Fi, так как взаимодействие с сервером может оказаться невозможным.
- macOS — не поддерживается
- Android — не поддерживается

## <a name="how-to-restart-a-device"></a>Перезапуск устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем нажмите **...Еще** и выберите удаленное действие **Перезагрузить**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства** выберите **Действия устройства**.
