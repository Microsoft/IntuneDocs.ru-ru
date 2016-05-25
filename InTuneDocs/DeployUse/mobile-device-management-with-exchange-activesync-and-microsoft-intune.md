---
# required metadata

title: Управление мобильными устройствами с помощью Exchange ActiveSync и Microsoft Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Управление мобильными устройствами с помощью Exchange ActiveSync и Microsoft Intune
Чтобы обеспечить прямое управление мобильными устройствами с помощью Microsoft Intune, пользователям следует зарегистрировать устройства в Intune. Для незарегистрированных мобильных устройств можно включить управление Exchange ActiveSync (EAS) с помощью соединителя Exchange. Устройствами можно управлять с локальных серверов Exchange и размещенного в облаке Exchange в среде Microsoft Office 365.

## Правила доступа к Exchange для мобильных устройств ##

Exchange требуется набор правил, определяющий, что происходит при попытке подключения мобильных устройств к EAS . Управление этими правилами осуществляется в консоли администрирования Intune.

[Правила доступа к Exchange для мобильных устройств](exchange-access-rules-for-mobile-devices.md)

## Установка соединителя Exchange
Соединитель Exchange позволяет управлять развертыванием Exchange в консоли Intune. Сначала необходимо установить и настроить соответствующий соединитель Intune с Exchange. Выберите нужный вариант, принимая во внимание вид сервера Exchange: локальный или размещенный как служба в облаке.

-   [Установка соединителя Intune для локального Exchange](intune-on-premises-exchange-connector.md)
-   [Настройка Intune service to service connector для размещенного Exchange](intune-service-to-service-exchange-connector.md)

## Применение политики для мобильных устройств под управлением Exchange
Параметры политики можно применить с помощью консоли. См. статью [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Список параметров политик и функций Exchange ActiveSync, поддерживаемых определенными устройствами, см. в таблице [Exchange ActiveSync Client Comparison Table (Сравнение клиентов Exchange ActiveSync)](http://go.microsoft.com/fwlink/?LinkId=247270).

> После подключения Intune к среде Microsoft Exchange политика EAS всех пользователей, управляемых с помощью Intune, будет сброшена до текущей политики по умолчанию на сервере Microsoft Exchange Server, если в Intune не определена более конкретная политика.

## Удаление корпоративных данных с мобильных устройств
И, наконец, можно [удалить корпоративные данные с мобильных устройств под управлением EAS](wipe-for-exchange-managed-mobile-devices.md), если они больше не используется или устройства потеряны или украдены.


<!--HONumber=May16_HO2-->


