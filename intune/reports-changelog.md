---
title: Журнал изменений хранилища данных Intune
titleSuffix: Microsoft Intune
description: В этой статье представлен список изменений для API хранилища данных Microsoft Intune.
keywords: Хранилище данных Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0aaa305ac216e0f80f82116e626b21f3ae7a8510
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "71303313"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Журнал изменений для API-интерфейса хранилища данных Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Следите за обновлениями хранилища данных Intune.

## <a name="1903-part-2"></a>1903 (часть 2)
_Дата выпуска: апрель 2019 г._

### <a name="beta-changes"></a>Изменения в бета-версии

Ниже перечислены последние удаленные коллекции и их замена в хранилище данных Intune.

|    Коллекция                          |    Изменение     |    Дополнительные сведения                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Удалено    |    Используйте [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts).                                                                                                                                                                                                                                                                     |
|    enrollmentTypes                     |    Удалено    |    Используйте [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes).                                                                                                                                                                                                                                                                                      |
|    mdmStatuses                         |    Удалено    |    Используйте [complianceStates](intune-data-warehouse-collections.md#compliancestates).                                                                                                                                                                                                                                                                                               |
|    workPlaceJoinStateTypes             |    Удалено    |    Используйте свойство `azureAdRegistered` в коллекциях [devices](intune-data-warehouse-collections.md#devices) и [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories).                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Удалено    |    Используйте [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates).                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Удалено    |    Используйте коллекцию [users](intune-data-warehouse-collections.md#users).                                                                                                                                                                                                                                                                                                      |
|    mdmDeviceInventoryHistories         |    Удалено    |    Многие свойства были избыточны, или их теперь можно найти в коллекциях [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) или [devices](intune-data-warehouse-collections.md#devices). Любые свойства **mdmDeviceInventoryHistories**, которые еще не были указаны с помощью этих двух коллекций, будут недоступны. Дополнительные сведения см. ниже.    |

В следующей таблице перечислены старые свойства, которые ранее размещались в коллекции **mdmDeviceInventoryHistories** и подверглись изменению или замене. Все свойства, которые были в **mdmDeviceInventoryHistories**, но отсутствуют в списке ниже, будут удалены.

|    Старое свойство                |    Замена или изменение                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    cellularTechnology          |    cellularTechnology в коллекции devices                                     |
|    deviceClientId              |    deviceId в коллекции devices                                               |
|    deviceManufacturer          |    manufacturer в коллекции devices                                           |
|    deviceModel                 |    model в коллекции devices                                                  |
|    deviceName                  |    deviceName в коллекции devices                                             |
|    deviceOsPlatform            |    deviceTypeKey в коллекции devices                                          |
|    deviceOsVersion             |    osVersion в коллекции devicePropertyHistories                              |
|    deviceType                  |    deviceTypeKey в коллекции devices, ссылается на коллекцию deviceTypes    |
|    encryptionState             |    Свойство encryptionState в коллекции devices                           |
|    exchangeActiveSyncId        |    Свойство easDeviceId в коллекции devices                               |
|    exchangeDeviceId            |    easDeviceId в коллекции devices                                            |
|    imei                        |    imei в коллекции devices                                                   |
|    isSupervised                |    Свойство isSupervised в коллекции devices                              |
|    jailBroken                  |    jailBroken in devicePropertyHistories collection                             |
|    meid                        |    Свойство meid в коллекции devices                                      |
|    oem                         |    manufacturer в коллекции devices                                           |
|    osName                      |    deviceTypeKey в коллекции devices, ссылается на коллекцию deviceTypes    |
|    phoneNumber                 |    phoneNumber в коллекции devices                                            |
|    platformType                |    model в коллекции devices                                                  |
|    product                     |    deviceTypeKey в коллекции devices                                          |
|    productVersion              |    osVersion в коллекции devicePropertyHistories                              |
|    серийный номер                |    serialNumber в коллекции devices                                           |
|    storageFree                 |    Свойство freeStorageSpaceInBytes в коллекции devices                   |
|    storageTotal                |    Свойство totalStorageSpaceInBytes в коллекции devices                |
|    subscriberCarrierNetwork    |    Свойство subscriberCarrier в коллекции devices                         |
|    wifimac                     |    wiFiMacAddress в коллекции devices                                         |

В следующей таблице перечислены изменения свойств в коллекции [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories): 

|    Старое свойство                  |    Замена или изменение                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, ссылается на коллекцию deviceCategories       |
|    certExpirationDate            |    Удалено                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime в коллекции devices                           |
|    deviceTypeKey                 |    deviceTypeKey в коллекции devices                              |
|    easID                         |    easDeviceId в коллекции devices                                |
|    enrolledByUser                |    userId в коллекции devices                                     |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey в коллекции devices                    |
|    graphDeviceIsCompliant        |    Удалено                                                          |
|    graphDeviceIsManaged          |    Удалено                                                          |
|    lastContact                   |    lastSyncDateTime в коллекции devices                           |
|    lastContactNotification       |    Удалено                                                          |
|    lastContactWorkplaceJoin      |    Удалено                                                          |
|    lastExchangeStatusUtc         |    Удалено                                                          |
|    lastModifiedDateTimeUTC       |    Удалено                                                          |
|    lastPolicyUpdateUtc           |    Удалено                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    manufacturer                  |    manufacturer в коллекции devices                               |
|    mdmStatusKey                  |    complianceStateKey, ссылается на коллекцию complianceStates    |
|    для базы данных модели                         |    model в коллекции devices                                      |
|    osFamily                      |    operatingSystem в коллекции devices                            |
|    osRevisionNumber              |    osVersion в коллекции devices                                  |
|    processorArchitecture         |    Удалено                                                          |
|    referenceId                   |    azureAdDeviceId в коллекции devices                            |
|    серийный номер                  |    serialNumber в коллекции devices                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

В следующей таблице перечислены изменения свойств в коллекции [devices](intune-data-warehouse-collections.md#devices): 

|    Старое свойство                  |    Замена или изменение                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, ссылается на коллекцию deviceCategories       |
|    certExpirationDate            |    Удалено                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    enrolledByUser                |    userId                                                           |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    graphDeviceIsCompliant        |    Удалено                                                          |
|    graphDeviceIsManaged          |    Удалено                                                          |
|    lastContact                   |    lastSyncDateTime                                                 |
|    lastContactNotification       |    Удалено                                                          |
|    lastContactWorkplaceJoin      |    Удалено                                                          |
|    lastExchangeStatusUtc         |    Удалено                                                          |
|    lastPolicyUpdateUtc           |    Удалено                                                          |
|    mdmStatusKey                  |    complianceStateKey, ссылается на коллекцию complianceStates    |
|    osFamily                      |    operatingSystem                                                  |
|    processorArchitecture         |    Удалено                                                          |
|    referenceId                   |    azureAdDeviceId                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

В следующей таблице перечислены изменения свойств в коллекции [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities): 

|    Старое свойство         |    Замена или изменение         |
|-------------------------|-------------------------------|
|    enrollmentTypeKey    |    deviceEnrollmentTypeKey    |

В следующей таблице перечислены изменения свойств в коллекции [mamApplications](intune-data-warehouse-collections.md#mamapplications): 

|    Старое свойство       |    Замена или изменение    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    applicationName    |    mamApplicationName    |
|    applicationId      |    mamApplicationId      |

В следующей таблице перечислены изменения свойств в коллекции [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances): 

|    Старое свойство     |    Замена или изменение    |
|---------------------|--------------------------|
|    applicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    mamDeviceName         |

В следующей таблице перечислены изменения свойств в коллекции [mamCheckins](intune-data-warehouse-collections.md#mamcheckins): 

|    Старое свойство      |    Замена или изменение    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

В следующей таблице перечислены изменения свойств в коллекции [users](intune-data-warehouse-collections.md#users): 

|    Старое свойство             |    Замена или изменение    |
|-----------------------------|--------------------------|
|    startDateInclusiveUtc    |    Удалено               |
|    endDateInclusiveUtc      |    Удалено               |
|    isCurrent                |    Удалено               |

## <a name="1903"></a>1903
_Выпуск от марта 2019 г._

### <a name="v10-changes-reflecting-back-to-beta"></a>Привнесение изменений из версии 1.0 обратно в бета-версию
Когда версия 1.0 впервые появилась в выпуске 1808, она имела несколько значительных отличий от бета-версии API. В выпуске 1903 эти изменения будут привнесены обратно в бета-версии API. Если у вас есть важные отчеты, использующие бета-версию API, мы настоятельно рекомендуем переключить их на версию 1.0 во избежание критических изменений. Обратитесь к [сведениям о версии API](reports-api-url.md), чтобы получить дополнительные сведения о версиях API хранилища данных и обеспечении обратной совместимости. 

## <a name="1902"></a>1902 
_Выпущено в феврале 2019 г._

### <a name="power-bi-compliance-app"></a>Приложение соответствия требованиям Power BI 

Вы можете получить доступ к своему хранилищу данных Intune в Power BI Online с помощью приложения [соответствия требованиям Intune (хранилище данных)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). С помощью этого приложения Power BI теперь можно обращаться к предварительно созданным отчетам и предоставлять их для общего доступа без какой-либо настройки и без выхода из веб-браузера. 

> [!NOTE]
> Существует два дополнительных фильтра, которые можно применить к приложению соответствия Intune.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Добавить дополнительные фильтры для приложения соответствия Intune
1. Откройте приложение [Соответствие Intune (хранилище данных)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) в веб-браузере.
2. Нажмите кнопку **Несоответствующие устройства** и выберите **Несоответствующие** в фильтре **complianceStatus**. 
3. Нажмите кнопку **Неизвестные устройства** и выберите **Пока недоступен** в фильтре **complianceStatus**. 

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

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Аутентификация в хранилище данных, предназначенная только для приложений <!-- 1867540 -->

Вы можете настроить приложение с помощью Azure Active Directory (Azure AD) и выполнить аутентификацию в хранилище данных Intune. Дополнительные сведения см. в статье [Аутентификация в хранилище данных, предназначенная только для приложений](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Требования к учетным данным Azure AD и Intune <!-- 2077525 -->

- Для доступа пользователей к хранилищу данных Intune (включая API) больше не нужно предоставлять им лицензию Intune.
- Имя роли Intune было изменено с **Отчеты** на **Хранилище данных Intune**. 

    Дополнительные сведения см. в статье [Требования к ученым данным Azure AD и Intune](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Параметры запроса OData <!-- 2077711 -->

Можно использовать <code>$select</code> как параметр запроса OData. Текущая версия поддерживает следующие параметры запроса OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> и <code>$top</code>. Дополнительные сведения см. в статье [Параметры запроса OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Новые сущности в модели данных для хранилища данных <!-- 2077804 -->

- Была добавлена сущность [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md). Сущность **MobileAppDeviceUserInstallStatus** представляет состояние установки мобильного приложения для заданного устройства или пользователя.
- Добавлена сущность [**MobileAppInstallStates**](reports-ref-application.md#mobileappinstallstates). Сущность **MobileAppInstallState** представляет состояние установки для мобильного приложения после его назначения группе, в состав которой входят устройства, пользователи или обе категории. 

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
