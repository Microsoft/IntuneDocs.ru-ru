---
title: Журнал изменений хранилища данных Intune
titlesuffix: Microsoft Intune
description: В этой статье представлен список изменений для API хранилища данных Microsoft Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/11/2010
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8e10549e05f814975337831e3eb9821d87a3f43
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834013"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Журнал изменений для API-интерфейса хранилища данных Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Следите за обновлениями хранилища данных Intune.

## <a name="1812"></a>1812 
_Выпуск в декабре 2018 г._

### <a name="enrollment-activities-collection-released-to-v10"></a>Выпущена версия 1.0 коллекции действий по регистрации 

Коллекция действий по регистрации теперь доступна в версии 1.0. Эту коллекцию можно использовать для понимания объема ошибок регистрации и тенденций в вашей среде. Дополнительные сведения см. в разделах [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories) и [ enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Выпущено в августе 2018 г._

### <a name="v10-collections"></a>Коллекции версии 1.0  

Теперь вы можете использовать версию 1.0 хранилища данных Intune, задав параметр запроса `api-version=v1.0`. Обновления коллекций в хранилище данных носят аддитивный характер и не нарушают существующие сценарии.

### <a name="enrollment-activities-collection-released-to-beta"></a>Выпущена бета-версия коллекции действий по регистрации

Выпущена бета-версия новой коллекции `Enrollment Activities`. С помощью этой коллекции можно отслеживать обработку своей регистрации, просмотрев наиболее распространенные сбои. 


## <a name="1805"></a>1805
_Выпущен: май 2018 г._

### <a name="correction-to-device-count-in-devices-collection"></a>Исправление числа устройств в коллекции **Устройства** 

В коллекцию **Устройства** были внесены изменения, которые могут уменьшить общее число устройств, для которых можно применить фильтр по атрибуту `isDeleted`. Уменьшение числа является результатом исправлений и не является ошибкой. Дополнительные сведения о коллекции **Устройства** можно узнать из статьи [Справочник по сущностям устройств](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Выпущен в январе 2018 г._

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Аутентификация в хранилище данных Intune, предназначенная только для приложений <!-- 1867540 -->

Вы можете настроить приложение с помощью Azure Active Directory (Azure AD) и выполнить аутентификацию в хранилище данных Intune. Дополнительные сведения см. в статье [Аутентификация в хранилище данных, предназначенная только для приложений](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Требования к учетным данным Azure AD и Intune <!-- 2077525 -->

- Для доступа пользователей к хранилищу данных Intune (включая API) больше не нужно предоставлять им лицензию Intune.
- Имя роли Intune было изменено с **Отчеты** на **Хранилище данных Intune**. 

    Дополнительные сведения см. в статье [Требования к ученым данным Azure AD и Intune](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Параметры запроса OData <!-- 2077711 -->

Можно использовать <code>$select</code> как параметр запроса OData. Текущая версия поддерживает следующие параметры запроса OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> и <code>$top</code>. Дополнительные сведения см. в статье [Параметры запроса OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Новые сущности в модели данных для хранилища данных <!-- 2077804 -->

 - Была добавлена сущность [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus). Сущность **MobileAppDeviceUserInstallStatus** представляет состояние установки мобильного приложения для заданного устройства или пользователя.
 - Была добавлена сущность [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate). Сущность **MobileAppInstallState** представляет состояние установки для мобильного приложения после его назначения группе, в состав которой входят устройства, пользователи или обе категории. 

## <a name="1710"></a>1710
_Выпущено: ноябрь 2017 г._

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Новая коллекция сущностей текущего пользователя содержит только данные активных сейчас пользователей <!-- 1544273 -->

Коллекция сущностей **пользователей** содержит всех пользователей Azure Active Directory (Azure AD) с назначенными лицензиями в вашей организации. Эти записи включают сведения о состояниях пользователя во время сбора данных, даже если этот пользователь удален. Например, пользователя добавили в Intune, а затем удалили в течение последнего месяца. Хотя этот пользователь отсутствовал на момент создания отчета, в данных хранятся записи о нем и его состоянии. Вы можете создать отчет, в котором указывалась бы продолжительность отображения данных о нем.

Напротив, новая коллекция сущностей **текущего пользователя** содержит только пользователей, которых не удаляли, то есть **активных пользователей**. Дополнительные сведения о коллекции сущностей **текущего пользователя**  см. в [этом справочнике](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Выпущено: октябрь 2017 г._

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>В модель данных хранилища данных Intune добавлена коллекция сущностей для сопоставления пользователей и устройств <!-- 1187917 -->

Теперь вы можете создавать отчеты и средства визуализации данных, используя сведения о сопоставлении пользователей и устройств, что позволяет сопоставлять коллекции сущностей для пользователей и устройств. Доступ к модели данных можно получить с помощью файла Power BI (PBIX), полученного на странице хранилища данных Intune, через конечную точку OData или путем разработки пользовательского клиента. Дополнительные сведения см. в статье [Сопоставление пользователя и устройства](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Новые сущности в модели данных для хранилища данных <!-- 1479526 --><!-- -->

 - Добавлена сущность [**UserDeviceAssociation**](reports-ref-user-device.md). Сущность **UserDeviceAssociation** содержит сопоставления пользователей и устройств в вашей организации. Теперь вы можете создавать отчеты и средства визуализации данных, используя сведения о сопоставлении пользователей и устройств, что позволяет сопоставлять коллекции сущностей для пользователей и устройств.  
 - Добавлена сущность [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md). **IntuneManagementExtension** содержит сущности для мобильных устройств, отслеживающие такую информацию, как версия и состояние установки.

## <a name="next-steps"></a>Дальнейшие шаги
 - Следите за [еженедельными новостями об улучшениях в Intune](whats-new.md). Кроме того, здесь можно узнать о предстоящих изменениях и получить важные уведомления относительно службы, а также сведения о прошлых выпусках.
 - Прочтите [блог Microsoft Intune](https://go.microsoft.com/fwlink/?LinkID=273882).
