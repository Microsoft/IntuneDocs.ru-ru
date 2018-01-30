---
title: "Использование хранилища данных Intune | Документация Майкрософт"
description: "Используйте хранилище данных Intune для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде."
keywords: "Хранилище данных Intune"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37ad088d722cfa2c543f43e4aa579a879dd4a4dd
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="use-the-intune-data-warehouse"></a>Использование хранилища данных Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Используйте хранилище данных Intune для создания отчетов, предоставляющих ценные сведения о вашей корпоративной мобильной среде. Например, некоторые отчеты включают в себя следующее:
-   Тренд по регистрации пользователей в Intune, чтобы вы могли оптимизировать покупку лицензий.
-   Разделение по версиям приложений и ОС, чтобы вы могли просматривать подобное состояние мобильных устройств.
-   Тренды по регистрации и соответствию устройств, чтобы вы могли беспрепятственно развертывать обновления политик.

Хранилище данных предоставляет больше сведений о мобильной среде, чем портал Azure. Благодаря хранилищу данных Intune вы получаете доступ к:

  -  данным журнала Intune;
  -  ежедневно обновляемым данным;
  -  модели данных, использующей стандарт OData.

> [!Note]
> Если вы используете гибридное управление мобильными устройствами (MDM) с помощью System Center Configuration Manager и Microsoft Intune, можно извлекать данные из SCCM. Хранилище данных Intune содержит только данные Intune. Для создания пользовательских отчетов можно использовать панель мониторинга SCCM Power BI. Дополнительные сведения см. в статьях [Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) (Представление шаблона решения Power BI для System Center Configuration Manager) и [Create a Power BI report and dashboard](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard) (Создание панели мониторинга и отчета Power BI).


> [!Important]  
> Вы можете самостоятельно оценить новые функциональные возможности хранилища данных с помощью бета-версии. Для ее использования URL-адрес должен содержать параметр запроса `api-version=beta`. Бета-версия позволяет воспользоваться функциями до того, как они станут общедоступными в виде поддерживаемой службы. По мере добавления новых возможностей в Intune поведение и контракты данных в бета-версии могут изменяться. Любые средства ведения отчетов или пользовательский код, зависящие от бета-версии, с выходом обновлений могут начать работать неправильно.

**Дальнейшие шаги**

- Вы можете получить ссылку и использовать Power BI для сбора ценных сведений. Инструкции см. в разделе [Подключение к хранилищу данных Intune с помощью Power BI](reports-proc-get-a-link-powerbi.md).
- Используя эту ссылку, вы можете создать пользовательский отчет с помощью Power BI. Инструкции см. в статье [Создание отчета из веб-канала OData с помощью Power BI](reports-proc-create-with-odata.md).
- Вы можете получить дополнительные сведения об API хранилища данных Intune, модели данных и связях между сущностями<!-- , and an example of creating a custom client to retrieve data,--> в разделе [API хранилища данных Intune](reports-nav-intune-data-warehouse.md).