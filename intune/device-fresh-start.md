---
title: "Сброс устройств Windows 10 с помощью Intune"
titlesuffix: Azure portal
description: "Сведения об использовании функции нового запуска для сброса компьютеров с Windows 10, на которых выполняется Intune.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Сброс устройств с Windows 10 с помощью функции нового запуска в Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие устройства **Чистый запуск** удаляет все установленные приложения на ПК с ОС Windows 10 с обновлением Creators Update, а затем автоматически обновляет ПК до последней версии Windows.
Это действие можно использовать для удаления предварительно установленных приложений, которые часто поставляются с новыми компьютерами. Кроме того, можно настроить сохранение данных пользователей при выполнении этого действия устройства. В этом случае приложения и параметры удаляются, но содержимое домашней папки сохраняется.

## <a name="how-to-use-fresh-start"></a>Использование действия "Чистый запуск"

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.
3. На панели **Intune** выберите **Устройства**.
4. На панели **Устройства** выберите **Все устройства**.
5. Выберите нужное классическое устройство с Windows 10 в списке управляемых устройств, а затем выберите действие удаленного устройства **Чистый запуск**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, на панели **Устройства** выберите **Действия устройства**.

