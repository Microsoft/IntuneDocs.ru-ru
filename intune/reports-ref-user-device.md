---
title: Сопоставление пользователя и устройства — хранилище данных Intune
titlesuffix: Microsoft Intune
description: Список изменений в API-интерфейсе хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0829bbcb661822c5d00ba4ca1e5d31ece301ef02
ms.sourcegitcommit: 445a54dc6826a549d770a9953549ae2191d391c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727430"
---
# <a name="user-device-association"></a>Сопоставление пользователя и устройства

Сущность **UserDeviceAssociation** содержит сопоставления пользователей и устройств в вашей организации.


|        Название        |                                           Описание                                            |        Пример         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Уникальный идентификатор пользователя в хранилище данных. (Суррогатный ключ).               |          123           |
|     DeviceKey      |                      Уникальный идентификатор устройства в хранилище данных.                      |          123           |
| CreatedDateTimeUTC |           Дата и время создания сопоставления пользователя и устройства. Используется формат UTC.           | 23/11/2016 12:00:00 |
|     IsDeleted      | Указывает, что пользователь отменил регистрацию этого устройства и что сопоставление больше не действительно. |       Истина/ложь       |
|  EndedDateTimeUTC  |              Дата и время (в формате UTC), когда значение IsDeleted изменилось на <strong>True</strong>.               | 23/06/2017 12:00:00 |

