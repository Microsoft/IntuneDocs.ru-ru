---
title: "Конечная точка API для хранилища данных Intune | Документация Майкрософт"
description: "Эта справочная статья описывает структуру URL-адресов API."
keywords: "Хранилище данных Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Конечная точка API для хранилища данных Intune

Вы можете использовать API хранилища данных Intune с помощью учетной записи, используя определенные меры управления доступом на основе ролей и учетные данные Azure AD. Позднее вы авторизуете свой клиент REST с помощью Azure AD, используя OAuth 2.0. Наконец, вы сформируете значимый URL-адрес для вызова ресурса хранилища данных.

## <a name="azure-ad-and-intune-credential-requirements"></a>Требования к учетным данным Azure AD и Intune

Проверка подлинности и авторизация основаны на учетных данных Azure AD и управлении доступом на основе ролей (RBAC) Intune. Все глобальные администраторы и администраторы служб Intune для вашего клиента по умолчанию имеют доступ к API. Используйте роли Intune, чтобы предоставить доступ к **ресурсам ведения отчетов** другим пользователям.

Требования для доступа к API:

  -  Пользователю должна быть присвоена лицензия Intune.
  -  Пользователь должен иметь разрешения одного из следующих уровней:
      -  Глобальный администратор Azure AD
      -  Администратор служб Intune
      -  Доступ на основе ролей к ресурсу **Отчеты**

## <a name="authorization"></a>Авторизация

Azure Active Directory (Azure AD) использует OAuth 2.0, чтобы предоставить возможность санкционировать доступ к веб-приложениям и веб-API в клиенте Azure AD. Это руководство не привязано к конкретному языку и описывает, как отправлять и получать сообщения HTTP без использования наших библиотек с открытым исходным кодом. Поток кода проверки подлинности OAuth 2.0 описан в [разделе 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) спецификации OAuth 2.0.

Дополнительные сведения см. в разделе [Разрешение доступа к веб-приложениям с помощью OAuth 2.0 и Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Структура URL-адресов API

Конечные точки API для хранилища данных считывают сущности для каждого набора. API поддерживает команду **GET** HTTP и подмножество параметров запроса.

URL-адрес для Intune использует следующий формат:  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

URL-адрес содержит следующие элементы:

| Элемент | Пример | Описание |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| местоположение | msua06 | Базовый URL-адрес можно узнать, просмотрев колонку API хранилища данных на портале Azure. |
| entity-collection | dates | Имя коллекции сущностей OData. Дополнительные сведения о коллекциях и сущностях в модели данных см. в разделе [Модели данных](reports-ref-data-model.md). |
| api-version | beta | Версия API, используемого для доступа. Дополнительные сведения см. в разделе [Версия](#API-version-information). |


## <a name="api-version-information"></a>Сведения о версии API

Текущая версия API: `beta`. 

## <a name="odata-query-options"></a>Параметры запроса OData

Текущая версия поддерживает следующие параметры запроса OData: `$skip, $top, $filter, $orderby`.