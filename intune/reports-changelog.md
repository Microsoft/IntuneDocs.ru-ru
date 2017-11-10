---
title: "Журнал изменений хранилища данных Intune | Документация Майкрософт"
description: "Список изменений в API-интерфейсе хранилища данных Intune."
keywords: "Хранилище данных Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b81846c2e45f968184d50d2ea7c50aabb86b4964
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Журнал изменений для API-интерфейса хранилища данных Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Следите за обновлениями хранилища данных Intune.

## <a name="1710"></a>1710
_Выпущен в октябре 2017 г._

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Сущность User содержит последние данные пользователя в модели данных для хранилища данных <!-- 1544273 -->

Первая версия модели данных для хранилища данных Intune содержала только недавние исторические данные Intune. Средствам создания отчетов не удавалось зафиксировать текущее состояние пользователя. В этом обновлении [**сущность User**](reports-ref-user.md) будет заполнена последними данными пользователя.

### <a name="new-entity-in-the-in-data-warehouse-data-model----1479526---"></a>Новая сущность в модели данных для хранилища данных <!-- 1479526 -->

Добавлена сущность [**UserDeviceAssociation**](reports-ref-user-device.md). Сущность **UserDeviceAssociation** содержит сопоставления пользователей и устройств в вашей организации.

## <a name="next-steps"></a>Дальнейшие действия
 - Следите за [еженедельными новостями об улучшениях в Intune](whats-new.md). Кроме того, здесь можно узнать о предстоящих изменениях и получить важные уведомления относительно службы, а также сведения о прошлых выпусках. 
 - Прочтите [блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).