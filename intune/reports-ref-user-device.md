---
title: Сопоставление пользователя и устройства — хранилище данных Intune
titlesuffix: Microsoft Intune
description: Список изменений в API-интерфейсе хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de14444376cb2998f17f406f084c428523ef4e4f
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="user-device-association"></a>Сопоставление пользователя и устройства

Сущность **UserDeviceAssociation** содержит сопоставления пользователей и устройств в вашей организации.

| Название               | Описание                                                                                      | Пример                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Уникальный идентификатор пользователя в хранилище данных. (Суррогатный ключ).                              | 123                    |
| DeviceKey          | Уникальный идентификатор устройства в хранилище данных.                                            | 123                    |
| CreatedDateTimeUTC | Дата и время создания сопоставления пользователя и устройства. Используется формат UTC.                                | 23/11/2016 12:00:00 |
| IsDeleted          | Указывает, что пользователь отменил регистрацию этого устройства и что сопоставление больше не действительно. | Истина/ложь             |
| EndedDateTimeUTC   | Дата и время (в формате UTC), когда значение IsDeleted изменилось на **True**.                                              | 23/06/2017 12:00:00 |
