---
title: Перенос учетной записи хранилища данных Intune
titlesuffix: Microsoft Intune
description: Узнайте, как создать резервную копию данных хранилища данных Intune при переносе учетной записи.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ee3ccbf9-82fc-4fbf-9d3d-8f05e431d090
ms.reviewer: aanavath
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: f1b2af2723ddb4c89f7f3d6409ced12f7a16883a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="move-your-intune-data-warehouse-account-data"></a>Перенос учетной записи хранилища данных Intune 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Запросив перенос учетной записи, вы запрашиваете перенос центра обработки данных в другое расположение. После переноса будет выполнен сброс хранилища данных и данные начнут записываться в новое расположение с дня начала переноса. Для резервного копирования данных в предыдущем хранилище необходимо выполнить следующие шаги **перед** переносом учетной записи. Большинство таблиц хранилища данных хранят данные в течение 30 дней, поэтому незаархивированные данные этих таблиц не будут доступны спустя 30 дней после переноса учетной записи. Дополнительные сведения о диапазоне хранения для отдельных таблиц см. в разделе [Модель данных для хранилища данных](reports-ref-data-model.md). 

## <a name="back-up-your-data-warehouse-data"></a>Резервное копирование данных хранилища данных 

Чтобы создать резервную копию данных хранилища, необходимо сохранить эти данные в *CSV-файле* с помощью API хранилища данных:  

1. При первом входе в API хранилища данных выполните одноразовый процесс, описанный в статье [Получение данных из API хранилища данных через клиент REST](reports-proc-data-rest.md).
2. Используйте пример PowerShell с названием [Access the Intune Data Warehouse with PowerShell](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/PowerShell) (Получение доступа к хранилищу данных Intune с помощью PowerShell), чтобы скачать все данные в CSV-файлы. 

## <a name="back-up-your-trend-charts-from-the-azure-portal"></a>Резервное копирование диаграмм тенденций с портала Azure

Некоторые диаграммы тенденций в представлении портала Azure будут сброшены. Можно создать резервную копию этих диаграмм путем выполнения следующего скрипта в **Graph**:   

### <a name="terms--conditions-acceptance-reports"></a>Отчеты о принятии условий
1. На портале Azure перейдите к **Microsoft Intune** -> **Регистрация устройств** -> **Условия**.
2. Для каждого элемента **условий** выберите **Acceptance Report** (Отчет о принятии условий), а затем **Экспорт**.
3. Сохраните отчет локально.
 
### <a name="app-protection-reports"></a>Отчет о защите приложений  
1. На портале Azure перейдите к **Microsoft Intune** -> **Мобильные приложения** -> **Состояние защиты приложений**.
2. Щелкните значок скачивания ( ⤓ ), чтобы сохранить каждый отчет.

### <a name="device-configuration-charts"></a>Диаграммы конфигурации устройства 
1. На портале Azure перейдите к **Microsoft Intune** -> **Конфигурация устройства**.
2. С помощью [обозревателя Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) скачайте данные, связанные с диаграммами. 
    - Сведения о состоянии развертывания всех профилей конфигурации устройств для всех устройств см. в [этой статье](https://graph.microsoft.com/beta/reports/deviceConfigurationDeviceActivity/content).

    - Сведения о состоянии развертывания всех профилей конфигурации устройств для всех пользователей см. в [этой статье](https://graph.microsoft.com/beta/reports/deviceConfigurationUserActivity/content).

    - Сведения о состоянии развертывания профиля см. в [этой статье](https://graph.microsoft.com/beta/deviceManagement/deviceConfigurations?$select=id,displayName,lastModifiedDateTime,deviceStatusOverview&$expand=deviceStatusOverview).
  
    > [!NOTE]
    > Чтобы получить доступ к конфигурации устройства и информации о состоянии развертывания, необходим допустимый маркер проверки подлинности.

## <a name="device-enrollment-charts"></a>Диаграммы регистрации устройств
1. На портале Azure перейдите к **Microsoft Intune** -> **Регистрация устройства**.
2. С помощью [обозревателя Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) скачайте данные, связанные с диаграммами.
    - состояние регистрации; 
    - основные ошибки регистрации на этой неделе. 
    - (Чтобы получить состояние регистрации, скопируйте этот [запрос состояния регистрации](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentFailureTrends()/content) и вставьте его в [обозреватель Graph](https://developer.microsoft.com/graph/graph-explorer).)
    - (Чтобы получить основные ошибки регистрации, скопируйте этот [запрос ошибок регистрации](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentTopFailures(period=null)/content) и вставьте его в [Обозреватель Graph](https://developer.microsoft.com/graph/graph-explorer).)

    > [!NOTE]
    > Чтобы получить доступ к данным регистрации устройства, необходим допустимый маркер проверки подлинности. 

## <a name="after-a-data-warehouse-account-move"></a>После переноса учетной записи в хранилища данных

После переноса учетной записи хранилища данных в Intune будет видно, что хранилище данных было сброшено и ваши данные теперь сохраняются в новом расположении. Диаграммы и параметры экспорта будут сброшены, и вы увидите уведомление, щелкнув которое, перейдете к статье, где объясняется, почему это случилось.  

## <a name="data-warehouse-move-example"></a>Пример переноса хранилища данных 

Клиент Х запрашивает перенос учетной записи начиная с 1.06.2018. В ответ на этот запрос клиент получит ссылку для просмотра документации с подробными сведениями о действиях, которые необходимо выполнить для резервного копирования данных предыдущего хранилища данных. Начиная с 1.06.2018 хранилище данных и диаграммы, которые оно поддерживает, будут сброшены и данные будут сохраняться в новом центре обработки данных. 

## <a name="next-steps"></a>Дальнейшие шаги

 - Следите за [еженедельными новостями об улучшениях в Intune](whats-new.md). Кроме того, здесь можно узнать о предстоящих изменениях и получить важные уведомления относительно службы, а также сведения о прошлых выпусках.
 - Прочтите [блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
