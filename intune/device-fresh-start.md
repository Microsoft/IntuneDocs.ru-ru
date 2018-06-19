---
title: Сброс настроек для устройств Windows 10 с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Чтобы удалить приложения с компьютеров Windows 10 с помощью Microsoft Intune, используйте действие "Чистый запуск".
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
ms.openlocfilehash: 5658bf2e1ee250ef9fd405b3f7ec1772b166f338
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31021002"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Сброс устройств с Windows 10 с помощью функции нового запуска в Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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