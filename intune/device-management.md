---
title: "Управление устройствами с помощью Intune"
titleSuffix: Intune on Azure
description: "Узнайте, как просмотреть устройства, управляемые с помощью Intune, и выполнять с ними различные операции.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b034e144aa43d239874b484acb2a40be12aff7c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Что такое управление устройствами с помощью Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

ИТ-администратор должен сделать так, чтобы управляемые устройства предоставляли ресурсы, необходимые конечным пользователям для выполнения работы, с одновременной защитой этих данных от риска.

Рабочая нагрузка **Устройства** позволяет получить сведения об управляемых устройствах и выполнять на них удаленные задачи. Для доступа к рабочей нагрузке сделайте следующее:

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В **Intune** выберите **Устройства**.
4. Можно просмотреть сведения об устройствах и выполнять указанные действия с удаленными устройствами, как показано далее.
    - **Общие сведения** — моментальный снимок зарегистрированных устройств, которыми можно управлять.
    - **Все устройства** — список зарегистрированных устройств, которыми можно управлять. Выберите **Фильтр** или **Столбцы** для уточнения отображаемых сведений. Выберите устройство для [просмотра данных по инвентаризации устройства](device-inventory.md).
    - **Устройства Azure AD** — список устройств, зарегистрированных или присоединенных к Azure Active Directory (AD). Дополнительные сведения об [управлении устройствами Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Действия устройства** — журнал удаленных действий, выполненных на устройствах, включая действие, его состояние, пользователя, который инициировал действие, и время.

    ![Мониторинг действий устройств](./media/monitor-device-actions.png)

    - **TeamViewer** — служба TeamViewer позволяет пользователям устройств Android, управляемым Intune, получать помощь удаленно от ИТ-администраторов. Дополнительные сведения о [TeamViewer](device-profile-android-teamviewer.md).

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


## <a name="next-steps"></a>Дальнейшие шаги

- Выберите **Действия устройства** для просмотра состояния действий, выполняемых на управляемых устройствах.
