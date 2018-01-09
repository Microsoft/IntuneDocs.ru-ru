---
title: "Сопоставление пользователя и устройства — хранилище данных Intune | Документация Майкрософт"
description: "Список изменений в API-интерфейсе хранилища данных Intune."
keywords: "Хранилище данных Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 45c3e14631fdfe74cafea4a0965efac51386524a
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2018
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
