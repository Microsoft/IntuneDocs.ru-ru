---
title: "Управление устройствами с помощью Exchange ActiveSync | Microsoft Intune"
description: "Управление мобильными устройствами с помощью системы управления Exchange ActiveSync (EAS) через соединитель с Exchange"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d5d5345dc6ef022e385a33ccc19b19cc022af2d5
ms.openlocfilehash: c67ad198c1693f84c9e00d15da00a131f7d0af87


---

# Управление мобильными устройствами Exchange ActiveSync с использованием Microsoft Intune
Чтобы служба Microsoft Intune напрямую управляла мобильными устройствами, они должны быть [зарегистрированы в Intune](prerequisites-for-enrollment.md). В качестве альтернативы администраторы могут включить более ограниченное решение управления, которое использует систему управления Exchange ActiveSync (EAS) через соединитель с Exchange. Устройствами можно управлять с локальных серверов Exchange Server и в Exchange Online с помощью Office 365. Intune поддерживает только одно подключение соединителя с Exchange любого типа на подписку.

## Правила доступа к Exchange для мобильных устройств ##

Exchange требуется набор правил, определяющий, что происходит при попытке подключения мобильных устройств к EAS . Управление этими правилами осуществляется в консоли администрирования Intune.

[Правила доступа к Exchange для мобильных устройств](exchange-access-rules-for-mobile-devices.md)

## Установка соединителя Exchange
Соединитель Exchange позволяет управлять развертыванием Exchange в консоли Intune. Сначала необходимо установить и настроить соответствующий соединитель Intune с Exchange. Выберите нужный вариант, принимая во внимание тип сервера Exchange: локальный или размещенный как служба в облаке.

-   [Настройка Intune для Exchange Online или новых выделенных сред Exchange Online](intune-service-to-service-exchange-connector.md)
-   [Установка соединителя с Intune для локальных серверов Exchange Server и старых выделенных сред Exchange Online](intune-on-premises-exchange-connector.md)


## Применение политики для мобильных устройств под управлением Exchange
Консоль Intune можно использовать для управления [настройками политики EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) и для [ограничения доступа к ресурсам компании](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Список параметров политик и функций Exchange ActiveSync, поддерживаемых определенными мобильными устройствами, см. в таблице [Сравнение клиентов Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> После подключения Intune к среде Microsoft Exchange политика EAS всех пользователей, управляемых с помощью Intune, будет сброшена до текущей политики по умолчанию на сервере Microsoft Exchange Server, если в Intune не определена более конкретная политика.

## Удаление корпоративных данных с мобильных устройств
И, наконец, можно [удалить корпоративные данные с мобильных устройств под управлением EAS](wipe-for-exchange-managed-mobile-devices.md), если они больше не используется или устройства потеряны или украдены.



<!--HONumber=Oct16_HO3-->


