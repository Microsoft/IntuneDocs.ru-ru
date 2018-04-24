---
title: Конечная точка API для хранилища данных Intune
titlesuffix: Microsoft Intune
description: В этой справочной статье описывается структура URL-адресов API хранилища данных Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b25140cb5c3c8c70ff42186352362c57dcf6ee7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Конечная точка API для хранилища данных Intune

Вы можете использовать API хранилища данных Intune с помощью учетной записи, используя определенные меры управления доступом на основе ролей и учетные данные Azure AD. Позднее вы авторизуете свой клиент REST с помощью Azure AD, используя OAuth 2.0. Наконец, вы сформируете значимый URL-адрес для вызова ресурса хранилища данных.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Авторизация

Azure Active Directory (Azure AD) использует OAuth 2.0, чтобы предоставить возможность санкционировать доступ к веб-приложениям и веб-API в клиенте Azure AD. Это руководство не привязано к конкретному языку и описывает, как отправлять и получать сообщения HTTP без использования наших библиотек с открытым исходным кодом. Поток кода проверки подлинности OAuth 2.0 описан в [разделе 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) спецификации OAuth 2.0.

Дополнительные сведения см. в разделе [Разрешение доступа к веб-приложениям с помощью OAuth 2.0 и Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Структура URL-адресов API

Конечные точки API для хранилища данных считывают сущности для каждого набора. API поддерживает команду **GET** HTTP и подмножество параметров запроса.

URL-адрес для Intune использует следующий формат:  
https://fef.{<strong><em>местоположение</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>коллекция_сущностей</em></strong>}?api-version={<strong><em>версия_api</em></strong>}

URL-адрес содержит следующие элементы:

| Элемент | Пример | Описание |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| местоположение | msua06 | Базовый URL-адрес можно узнать, просмотрев колонку API хранилища данных на портале Azure. |
| entity-collection | dates | Имя коллекции сущностей OData. Дополнительные сведения о коллекциях и сущностях в модели данных см. в разделе [Модели данных](reports-ref-data-model.md). |
| api-version | beta | Версия API, используемого для доступа. Дополнительные сведения см. в разделе [Версия](#API-version-information). |


## <a name="api-version-information"></a>Сведения о версии API

Текущая версия API: `beta`. 

## <a name="odata-query-options"></a>Параметры запроса OData

Текущая версия поддерживает следующие параметры запроса OData: `$filter, $orderby, $select, $skip,` и `$top`.