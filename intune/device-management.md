---
title: "Управление устройствами с помощью Intune"
titleSuffix: Intune on Azure
description: "Узнайте, как просмотреть устройства, управляемые с помощью Intune, и выполнять с ними различные операции.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0fc5337b92ac604a448038f685b27623b6153f9
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Что такое управление устройствами с помощью Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Рабочая нагрузка **Устройства** позволяет получить сведения об управляемых устройствах и выполнять на них удаленные задачи. Для доступа к рабочей нагрузке сделайте следующее:

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. Теперь можно выполнять перечисленные удаленные действия на устройствах. Доступные действия зависят от платформы и конфигурации устройства.

## <a name="available-device-actions"></a>Доступные действия на устройствах

- [Просмотр данных по инвентаризации устройств](device-inventory.md)
- Выполните следующие действия удаленного устройства:
    - [Удаление данных организации](device-company-data-remove.md) 
    - [Сброс параметров](device-factory-reset.md)
    - [Удаленная блокировка](device-remote-lock.md).
    - [Сбросить секретный код](device-passcode-reset.md)
    - [Обход блокировки активации](device-activation-lock-bypass.md)
    - [С чистого листа](device-fresh-start.md)
    - [Режим пропажи](device-lost-mode.md)
    - [Найти устройство](device-locate.md)
    - [Перезапуск](device-restart.md)
    - [Сброс ПИН-кода для Windows 10](device-windows-pin-reset.md)
    - [Удаленное управление устройством Android](device-profile-android-teamviewer.md)
    - [Синхронизация устройств](device-sync.md)


## <a name="next-steps"></a>Дальнейшие действия

- Выберите **Действия устройства** для просмотра состояния действий, выполняемых на управляемых устройствах. 
![Монитор действий устройств](./media/monitor-device-actions.png)
