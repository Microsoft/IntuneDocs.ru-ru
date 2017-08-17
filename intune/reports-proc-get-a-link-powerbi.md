---
title: "Подключение к хранилищу данных с помощью Power BI | Документация Майкрософт"
description: "Вы можете скачать файл для Microsoft Power BI, позволяющий загружать интерактивные и динамически создаваемые отчеты своего клиента Intune."
keywords: "Хранилище данных Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b70bf3410e20dd792c0fcff050292ddea714d63e
ms.sourcegitcommit: 99ffed621855357de427d6fdf7b70d4e543197e9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Подключение к хранилищу данных с помощью Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Вы можете скачать файл для Microsoft Power BI, позволяющий загружать интерактивные и динамически создаваемые отчеты своего клиента Intune. Файл Power BI для хранилища данных (PBIX) содержит параметры подключения для вашего клиента, а также следующие примеры отчетов и диаграмм:  

  -  Устройства
  -  Регистрация
  -  Политика защиты приложений
  -  Compliance policy (Политика соответствия требованиям)
  -  Профили конфигурации устройства
  -  Обновления программного обеспечения
  -  Журналы инвентаризации устройства

Кроме того, такой подход позволяет выявить тренды для регистрации, соответствия, профиля конфигурации устройства и обновлений программного обеспечения. Примеры диаграмм и отчетов применяют к холсту понятные и удобные фильтры. Чтобы использовать расширенные фильтры, откройте панель **Фильтр** в Power BI Desktop. 

Ниже показано, как скачать файл Power BI и использовать ссылку OData с помощью Power BI.

## <a name="install-power-bi"></a>Установка Power BI

Установите последнюю версию Power BI Desktop. Ее можно скачать с сайта: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop). 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Загрузка данных и отчетов с помощью файла Power BI (PBIX)

Файл Power BI (PBIX) содержит сведения о подключении для клиента и набор готовых отчетов, основанных на модели данных хранилища данных. Откройте файл в Power BI Desktop и войдите в Azure AD. Отчет загружает данные из вашего клиента Intune.

> [!Important]  
> Каждый файл Power BI (PBIX) может отличаться в зависимости от расположения клиента. При управлении несколькими клиентами Intune необходимо использовать файл, скачанный с портала Azure, во время нахождения в этом клиенте.  

1.  Войдите на портал Azure и выберите **Мониторинг и управление** > **Intune**. Вы также можете выполнить поиск в ресурсах по слову **Intune**.  
2.  Откройте колонку **API хранилища данных Microsoft Intune (предварительная версия)**.
3.  Щелкните **Скачать файл Power BI**. Файл с расширением (PBIX) скачивается в указанное вами расположение.
4.  Откройте файл в Power BI. Загружается компонент *отчетов хранилища данных Intune*, что может занять несколько секунд, так как он получает данные клиента.
5.  Нажмите кнопку **Обновить**, чтобы загрузить данные клиента и просмотреть отчеты.
6.  Если Power BI еще не прошел проверку подлинности с учетными данными Azure Active Directory, Power BI предлагает указать учетные данные. При выборе учетных данных укажите метод проверки подлинности **Учетная запись в организации**.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Загрузка данных в Power BI с помощью ссылки OData

После того, как клиент прошел проверку подлинности в Azure AD, URL-адрес OData подключается к конечной точке RESTful в API хранилища данных, который предоставляет вашему клиенту отчетов модель данных. Следуйте этим инструкциям, чтобы использовать Power BI Desktop для подключения и создания собственных отчетов. Вы не ограничены Power BI Desktop и можете использовать любой аналитический инструмент с URL-адресом OData при условии, что клиент поддерживает проверку подлинности OAUTH2.0 и стандарт OData версии 4.0.

1.  Получите **URL-адрес OData** из колонки отчетности, например `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
2.  Откройте **Power BI Desktop**.
3.  Выберите **Домашняя** > **Получить данные**. Выберите **Канал OData**.
4.  Выберите **Базовый**.
5.  Введите или вставьте **URL-адрес OData** в поле URL-адреса.
6.  Нажмите кнопку **ОК**.
7.  Если вы не выполняли проверку подлинности в Azure AD для своего клиента из клиента Power BI Desktop, введите свои учетные данные.  
    а.  Выберите **Учетная запись в организации**.  
    b.  Введите имя пользователя и пароль.  
    в.  Нажмите кнопку **Войти**.  
    г.  Нажмите кнопку **Подключиться**.  
8.  Нажмите кнопку **Загрузить**.

## <a name="next-steps"></a>Дальнейшие действия

Вы можете найти ответы на вопросы о своей среде, например число ежедневно регистрируемых устройств на прошлой неделе. Вы можете получить представление о своей популяции клиентов Intune с помощью отчетов, используя файл Intune хранилища данных Power BI (PBIX), полученный из колонки в Azure. Кроме того, Intune предоставляет несколько дополнительных способов для расширения или повторного использования этих данных. Power BI и API хранилища данных Intune предоставляют вам гораздо больше возможностей, например:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Данные клиента упорядочиваются, чтобы помочь вам извлекать из них ценные сведения. Дополнительные сведения об упорядочении данных см. в разделе [Модель данных для хранилища данных](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->