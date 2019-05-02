---
title: Использование хранилища данных Intune
titleSuffix: Microsoft Intune
description: Используйте хранилище данных Intune для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0728fefc40bc82db7926faf282a69d0471c3a1ea
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798125"
---
# <a name="use-the-microsoft-intune-data-warehouse"></a>Использование хранилища данных Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Используйте хранилище данных Intune для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде. Например, некоторые отчеты включают в себя следующее:
-   Тренд по регистрации пользователей в Intune, чтобы вы могли оптимизировать покупку лицензий.
-   Разделение по версиям приложений и ОС, чтобы вы могли просматривать подобное состояние мобильных устройств.
-   Тренды по регистрации и соответствию устройств, чтобы вы могли беспрепятственно развертывать обновления политик.

## <a name="data-warehouse-benefits"></a>Преимущества, обеспечиваемые хранилищем данных

Хранилище данных предоставляет больше сведений о мобильной среде, чем портал Azure. Благодаря хранилищу данных Intune вы получаете доступ к:

  -  данным журнала Intune;
  -  ежедневно обновляемым данным;
  -  модели данных, использующей стандарт OData.

> [!Note]
> Если вы используете совместное управление мобильными устройствами (MDM) с помощью System Center Configuration Manager и Microsoft Intune, можно извлекать данные из Configuration Manager. Хранилище данных Intune содержит только данные Intune. Панель мониторинга Power BI Configuration Manager можно использовать для создания пользовательских отчетов. Дополнительные сведения см. в статьях [Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) (Представление шаблона решения Power BI для System Center Configuration Manager) и [Power BI content for Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page) (Содержимое Power BI для Dynamics 365).

> [!Important]  
> Теперь вы можете использовать версию 1.0 хранилища данных Intune, задав параметр запроса `api-version=v1.0`. Обновления коллекций в хранилище данных носят аддитивный характер и не нарушают существующие сценарии.<br><br>
> Вы можете самостоятельно оценить новые функциональные возможности хранилища данных с помощью бета-версии. Для ее использования URL-адрес должен содержать параметр запроса `api-version=beta`. Бета-версия позволяет воспользоваться функциями до того, как они станут общедоступными в виде поддерживаемой службы. По мере добавления новых возможностей в Intune поведение и контракты данных в бета-версии могут изменяться. Любые средства ведения отчетов или пользовательский код, зависящие от бета-версии, с выходом обновлений могут начать работать неправильно.

## <a name="next-steps"></a>Дальнейшие шаги

- Вы можете получить ссылку и использовать Power BI для сбора ценных сведений. Инструкции см. в разделе [Подключение к хранилищу данных Intune с помощью Power BI](reports-proc-get-a-link-powerbi.md).
- Используя эту ссылку, вы можете создать пользовательский отчет с помощью Power BI. Инструкции см. в статье [Создание отчета из веб-канала OData с помощью Power BI](reports-proc-create-with-odata.md).
- Вы можете получить дополнительные сведения об API хранилища данных Intune, модели данных и связях между сущностями<!-- , and an example of creating a custom client to retrieve data,--> в разделе [API хранилища данных Intune](reports-nav-intune-data-warehouse.md).
