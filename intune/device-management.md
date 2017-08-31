---
title: "Управление устройствами с помощью Intune"
titleSuffix: Intune on Azure
description: "Узнайте, как просмотреть устройства, управляемые с помощью Intune, и выполнять с ними различные операции.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d78b4a87eaa366b7bb00356c4b98d609620dcf3
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Что такое управление устройствами с помощью Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Рабочая нагрузка **Устройства** позволяет получить сведения об управляемых устройствах и выполнять на них удаленные задачи. Для доступа к рабочей нагрузке сделайте следующее:

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. Можно просмотреть сведения об устройствах и выполнять указанные действия с удаленными устройствами.

## <a name="available-device-actions"></a>Доступные действия на устройствах
Доступные действия зависят от платформы и конфигурации устройства.

- [Просмотр данных по инвентаризации устройств](device-inventory.md)
- Выполните следующие действия удаленного устройства:
    - [Удаление данных организации](devices-wipe.md#remove-company-data)
    - [Сброс параметров](devices-wipe.md#factory-reset)
    - [Удаленная блокировка](device-remote-lock.md). 
    - [Сбросить секретный код](device-passcode-reset.md)
    - [Обход блокировки активации](device-activation-lock-bypass.md) (только iOS)
    - [Новый запуск](device-fresh-start.md) (только Windows)
    - [Режим пропажи](device-lost-mode.md) (только iOS)
    - [Найти устройство](device-locate.md) (только iOS)
    - [Перезапуск](device-restart.md) (только Windows)
    - [Сброс ПИН-кода для Windows 10](device-windows-pin-reset.md)
    - [Удаленное управление устройством Android](device-profile-android-teamviewer.md)
    - [Синхронизация устройств](device-sync.md)


## <a name="next-steps"></a>Дальнейшие действия

- Выберите **Действия устройства** для просмотра состояния действий, выполняемых на управляемых устройствах.
![Монитор действий устройств](./media/monitor-device-actions.png)
