---
title: Управление устройствами с помощью Microsoft Intune в Azure | Документы Майкрософт
description: Просмотр устройств, управляемых с помощью Microsoft Intune, включая экспорт списка устройств в CSV-формат, просмотр устройств, присоединенных к Azure Active Directory, просмотр журнала изменений выполняемых действий на устройстве, использование TeamViewer Connector для удаленного устранения неполадок на устройствах Android ИТ-администраторами и просмотр всех действий, которые можно выполнять на устройствах.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd1d99e0c3853a7bf607dd2f64046c503068566d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728628"
---
# <a name="what-is-microsoft-intune-device-management"></a>Что такое управление устройствами с помощью Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

ИТ-администратор должен сделать так, чтобы управляемые устройства предоставляли ресурсы, необходимые пользователям для выполнения работы, с одновременной защитой этих данных от риска.

Рабочая нагрузка **Устройства** позволяет получить сведения об управляемых устройствах и выполнять на них удаленные задачи.

## <a name="get-to-your-devices"></a>Доступ к устройствам

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Выберите **Устройства**. В этом представлении отображаются подробные сведения об отдельных устройствах, а также выполняемые на них действия.

   - В разделе **Общие сведения** отображается снимок зарегистрированных устройств, а также показано количество устройств, использующих различные платформ, включая Android, iOS и т. д.
   - В разделе **Все устройства** отображается список зарегистрированных управляемых устройств.

     Функция **Экспорт** позволяет создать CSV-список всех устройств с шагом 10 000 (Internet Explorer) или 30 000 (Microsoft Edge, Chrome).

     Выберите любое устройство, чтобы [просмотреть дополнительные сведения об этом устройстве](device-inventory.md), включая данные об оборудовании, установленные приложения, состояние политики соответствия и многое другое.

   - В разделе **Устройства Azure AD** отображается список устройств, зарегистрированных или присоединенных к Azure Active Directory (Azure AD). Дополнительные сведения об [управлении устройствами Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Действия устройства** — журнал удаленных действий, выполненных на разных устройствах, включая действие, его состояние, пользователя, который инициировал действие, и время.

     ![Снимок экрана: мониторинг действий устройств](./media/device-management/monitor-device-actions.png)

   - В **журналы аудита** записываются действия, которые генерируют изменения в Intune. В [журналах аудита](../fundamentals/monitor-audit-logs.md) содержатся более подробные сведения.
   - **TeamViewer Connector** — это служба, которая позволяет пользователям устройств Android, управляемым Intune, получать удаленную помощь от ИТ-администраторов. Дополнительные сведения о [TeamViewer](teamviewer-support.md).
   - В разделе **Справка и поддержка** находится ярлык на советы по устранению неполадок, обращению в службу поддержки или проверке состояния Intune.

## <a name="available-device-actions"></a>Доступные действия на устройствах
Доступные действия зависят от платформы и конфигурации устройства.

- [Просмотр данных по инвентаризации устройств](device-inventory.md)
- Выполнение действий удаленного устройства
  - [Прекратить использование](devices-wipe.md#retire)
  - [Очистка](devices-wipe.md#wipe)
  - [Удаленная блокировка](device-remote-lock.md).
  - [Сбросить секретный код](device-passcode-reset.md)
  - [Обход блокировки активации](device-activation-lock-bypass.md) (только iOS)
  - [Новый запуск](device-fresh-start.md) (только Windows)
  - [Режим пропажи](device-lost-mode.md) (только iOS)
  - [Найти устройство](device-locate.md) (только iOS)
  - [Перезапуск](device-restart.md) (только Windows)
  - [Сброс ПИН-кода для Windows 10](device-windows-pin-reset.md)
  - [Удаленное управление устройством Android](teamviewer-support.md)
  - [Синхронизация устройств](device-sync.md)
  - [Отправить пользовательское уведомление](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS)

## <a name="next-steps"></a>Дальнейшие шаги

- В разделе **Все устройства** выберите устройство, чтобы просмотреть о нем дополнительные сведения.
- Выберите **Действия устройства** для просмотра состояния действий, выполняемых на управляемых устройствах.