---
title: Сброс настроек для устройств Windows 10 с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Чтобы удалить приложения с компьютеров Windows 10 с помощью Microsoft Intune, в том числе предварительно установленные приложения от изготовителей оборудования, используйте действие "Чистый запуск". Кроме того, при помощи этого действия можно сохранить содержимое домашней папки, используя параметр if user data is retained.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d17c9dc11791f32f0c2c1e7faa88966c112fc6a5
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Сброс устройств с Windows 10 с помощью функции нового запуска в Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

При использовании действия устройства **Чистый запуск** удаляются все приложения, установленные на ПК с Windows 10 Creators Update. Затем операционная система ПК автоматически обновляется до последней версии Windows.

Это действие позволяет удалить предварительно установленные приложения (поставщика оборудования) на новом компьютере. Чтобы сохранить содержимое домашней папки пользователя и удалить только приложения и настройки, используйте параметр `if user data is retained`.

> [!IMPORTANT]
> При использовании действия "Чистый запуск" регистрация этого устройства в Intune отменяется, но оно остается в Azure Active Directory.

## <a name="use-fresh-start"></a>Использование действия "Чистый запуск"

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Устройства**, а затем — **Все устройства**.
4. Выберите нужное классическое устройство с Windows 10 в списке управляемых устройств, а затем выберите действие **Чистый запуск**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы отобразились сведения о состоянии действия, выберите **Действия устройства** (**Microsoft Intune** > **Устройства**).