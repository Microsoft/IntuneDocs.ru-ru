---
title: "Сброс устройств Windows 10 с помощью Intune"
titleSuffix: Intune on Azure
description: "Сведения об использовании функции нового запуска для сброса компьютеров с Windows 10, на которых выполняется Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 590472c0ab9f0103d72730b8ab01dc324c852a7a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Сброс устройств с Windows 10 с помощью функции нового запуска в Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие устройства **Чистый запуск** удаляет все установленные приложения на ПК с ОС Windows 10 с обновлением Creators Update, а затем автоматически обновляет ПК до последней версии Windows.
Эту функцию можно использовать для удаления предварительно установленных OEM-приложений, которые часто поставляются с новыми компьютерами. Кроме того, можно настроить сохранение данных пользователей при выполнении этого действия устройства. В этом случае приложения и параметры удаляются, но содержимое домашней папки сохраняется.

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное классическое устройство с Windows 10 в списке управляемых устройств, а затем выберите действие удаленного устройства **Чистый запуск**.

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.

