---
title: "API хранилища данных Intune | Документация Майкрософт"
description: "Вы можете использовать этот API для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде."
keywords: "Хранилище данных Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2017
---
#  <a name="intune-data-warehouse-api"></a>API хранилища данных Intune

API хранилища данных Intune предоставляет доступ к данным Intune в машиночитаемом формате, чтобы их можно было использовать в удобном вам средстве анализа. Вы можете использовать этот API для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде. Этот API использует протокол OData, который применяет стандартные шаблоны для следующих объектов:

  -   Заголовки запросов и ответов
  -   Коды состояния
  -   Методы HTTP
  -   Соглашения по URL-адресам
  -   Типы мультимедиа
  -   Форматы полезных данных
  -   Параметры запроса

OData (Open Data Protocol) — это стандарт организации Advancement of Structured Information Standards (OASIS), который определяет рекомендации по созданию и использованию API-интерфейсов RESTful. Хранилище данных Intune использует OData версии 4.0.

Эта справочная статья содержит общие сведения о конечных точках, поддерживаемых методами HTTP, форматах возвращаемых полезных данных и документации по модели данных хранилища данных Intune .

> [!Important]  
> Вы можете самостоятельно оценить новые функциональные возможности хранилища данных с помощью бета-версии. Для ее использования URL-адрес должен содержать параметр запроса `api-version=beta`. Бета-версия позволяет воспользоваться функциями до того, как они станут общедоступными в виде поддерживаемой службы. По мере добавления новых возможностей в Intune поведение и контракты данных в бета-версии могут изменяться. Любые средства ведения отчетов или пользовательский код, зависящие от бета-версии, с выходом обновлений могут начать работать неправильно. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>Взаимодействие с API

Этому API требуется авторизация с помощью Azure AD. Azure AD использует OAuth 2.0. После авторизации вы можете получить данные из API с помощью команды HTTP GET и обращения к предоставленным коллекциям сущностей. Более подробные сведения см. в статье

 -  [Авторизация](reports-api-url.md)
 -  [Структура URL-адресов API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Модель данных для хранилища данных Intune

OData определяет абстрактную модель данных и протокол, позволяющие любому клиенту получить доступ к сведениям, предоставляемым любым источником данных. Раздел о документации по модели данных содержит пояснения для пространств имен, сущностей и возвращаемых объектов в модели данных хранилища данных Intune. Дополнительные сведения см. в разделе [Модель данных для хранилища данных](reports-ref-data-model.md).

## <a name="for-more-information"></a>Дополнительные сведения

[Сценарии проверки подлинности для Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData версии 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
