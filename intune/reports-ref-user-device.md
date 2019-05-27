---
title: Сопоставление пользователя и устройства — хранилище данных Intune
titleSuffix: Microsoft Intune
description: Сущность UserDeviceAssociation содержит сопоставления пользователей и устройств в вашей организации.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7401b5da7629addf03498afd44033a59839d39e
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045322"
---
# <a name="reference-for-user-device-association-entity"></a>Справочник по сущности сопоставления пользователя и устройства

Сущность **UserDeviceAssociation** содержит сопоставления пользователей и устройств в вашей организации.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Название        |                                           Описание                                            |        Пример         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Уникальный идентификатор пользователя в хранилище данных. (Суррогатный ключ).               |          123           |
|     DeviceKey      |                      Уникальный идентификатор устройства в хранилище данных.                      |          123           |
| CreatedDateTimeUTC |           Дата и время создания сопоставления пользователя и устройства. Используется формат UTC.           | 23/11/2016 12:00:00 |
|     IsDeleted      | Указывает, что пользователь отменил регистрацию этого устройства и что сопоставление больше не действительно. |       Истина/ложь       |
|  EndedDateTimeUTC  |              Дата и время (в формате UTC), когда значение IsDeleted изменилось на <strong>True</strong>.               | 23/06/2017 12:00:00 |

## <a name="next-steps"></a>Дальнейшие шаги

- Дополнительные сведения см. в статье [Использование хранилища данных Intune](reports-nav-create-intune-reports.md).
