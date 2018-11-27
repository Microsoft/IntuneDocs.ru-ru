---
title: Данные, которые Google отправляет в Intune
titleSuffix: Microsoft Intune
description: Список данных, которые Google отправляет в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a0678e562ab7b63c99f10c455837cf03ee30da21
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52178785"
---
# <a name="data-google-sends-to-intune"></a>Данные, которые Google отправляет в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Если на устройстве включено корпоративное управление устройствами Android, Microsoft Intune устанавливает соединение с Google и делится с Google сведениями о пользователе и устройстве. Чтобы установить соединение с Microsoft Intune, необходимо создать учетную запись Google.

В следующей таблице перечислены данные, которые Google отправляет в Intune, когда на устройстве включено управление устройствами:


| Данные, которые Google отправляет в Intune | Подробные сведения | Назначение | Пример |
|:---:|:---:|:---:|:---:|
| Корпоративные данные | Корпоративные идентификаторы клиента в Google. | Связывает информацию о клиенте в Intune и Google. | Пример **корпоративного идентификатора**: LC04eik8a6.<br>**Имя**. Имя администратора, указанное при настройке Android для бизнеса. Пример: Виктор Дегтярев.<br>**Адрес электронной почты администратора**. YourAdmin@gmail.com, который использовался при настройке Android для бизнеса. |
| Данные приложений | Данные для управляемых приложений Play Store. | Отмечают приложения для пользователей или устройств как доступные или требуемые. | **Имя приложения**, например Contoso Warehouse Inventory Application.<br>**Уникальный идентификатор для представления приложения**, например app:com.Contoso.Warehouse.InventoryTracking. |
| Учетная запись службы | Уникальная внутренняя учетная запись службы Google для использования с конкретными вызовами клиентов. | Используется для выполнения вызовов в Google от имени клиента (для просмотра приложений, устройств и т. д.). | **Имя**, например InternalAccount@InternalService.com.<br>**Ключи**, например ServiceAccountPassword. |


Чтобы прекратить использование функции корпоративного управления устройствами Android с Microsoft Intune и удалить данные, необходимо отключить эту функцию и удалить учетную запись Google. Сведения об управлении учетными записями см. в учетной записи Google.


