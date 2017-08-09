---
title: "Пользователь | Документация Майкрософт"
description: "Справочник по категории \"Пользователь\" коллекций сущностей в API хранилища данных Intune."
keywords: "Хранилище данных Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>Справочник по сущности пользователя

Категория **Пользователь** содержит сущность **User**, которая определяет свойства пользователей и агентов в модели данных.

**User**

Сущность **User** перечисляет всех пользователей Azure Active Directory (Azure AD) с назначенными лицензиями в вашей организации.

| Свойство  | Описание | Пример |
|---------|------------|--------|
| UserKey |Уникальный идентификатор для пользователя в хранилище данных — суррогатный ключ |123 |
| UserId |Уникальный идентификатор пользователя — аналогичен UserKey, но является естественным ключом |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Адрес электронной почты пользователя |John@constoso.com |
| DisplayName |Отображаемое имя пользователя |Виталий |
| IntuneLicensed |Указывает, имеет ли этот пользователь лицензию Intune. |Истина/ложь |
| IsDeleted |Указывает, обновлена ли запись пользователя.  True — этот пользователь имеет новую запись с обновленными полями в этой таблице. False — последняя запись для этого пользователя. |Истина/ложь |
| StartDateInclusiveUTC |Дата и время (в формате UTC) создания этого пользователя в хранилище данных. |23/11/2016 12:00:00 |
| EndDateExclusiveUTC |Дата и время (в формате UTC), когда значение IsDeleted изменилось на True. |23/11/2016 12:00:00 |
| IsCurrent |Указывает, является ли эта запись пользователя актуальной или не находится в хранилище данных. |Истина/ложь |
| RowLastModifiedDateTimeUTC |Дата и время (в формате UTC) последнего изменения этого пользователя в хранилище данных. |23/11/2016 12:00:00 |

