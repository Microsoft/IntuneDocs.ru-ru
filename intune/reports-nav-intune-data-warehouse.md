---
title: API хранилища данных Intune
titlesuffix: Microsoft Intune
description: Вы можете использовать API хранилища данных Intune для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f67d7679c79836b6cce1692253c887f88960aead
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231619"
---
#  <a name="microsoft-intune-data-warehouse-api"></a>API хранилища данных Microsoft Intune

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

## <a name="odata-custom-client"></a>Пользовательский клиент OData

Для доступа к модели данных для хранилища данных Intune можно использовать конечные точки RESTful. Для получения доступа к данным клиент должен авторизоваться в Azure Active Directory (Azure AD) с помощью OAuth 2.0. Сначала следует настроить веб-приложение и клиентское приложение в Azure и предоставить разрешения клиенту. Локальный клиент пройдет авторизацию и затем сможет взаимодействовать с конечными точками хранилища данных.

Дополнительные сведения см. в статье [Получение данных из API хранилища данных через клиент REST](reports-proc-data-rest.md).

> [!Note]  
> Образцы кода можно получить в [репозитории хранилища данных Intune](https://github.com/Microsoft/Intune-Data-Warehouse) в GitHub.

## <a name="interacting-with-the-api"></a>Взаимодействие с API

Этому API требуется авторизация с помощью Azure AD. Azure AD использует OAuth 2.0. После авторизации вы можете получить данные из API с помощью команды HTTP GET и обращения к предоставленным коллекциям сущностей. Более подробные сведения см. в статье

 -  [Авторизация](reports-api-url.md)
 -  [Структура URL-адресов API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Модель данных для хранилища данных Intune

OData определяет абстрактную модель данных и протокол, позволяющие любому клиенту получить доступ к сведениям, предоставляемым любым источником данных. Раздел о документации по модели данных содержит пояснения для пространств имен, сущностей и возвращаемых объектов в модели данных хранилища данных Intune. Дополнительные сведения см. в разделе [Модель данных для хранилища данных](reports-ref-data-model.md).

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения о работе с Azure AD см. в статье [Сценарии проверки подлинности в Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

Ресурсы OData можно найти на сайте [odata.org](https://www.odata.org).
  
Ознакомиться со стандартом OData версии 4.0 можно на странице [OData версии 4.0] (https://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
