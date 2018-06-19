---
title: Соединитель Intune с Exchange для Exchange Online
titleSuffix: ''
description: Подключения Intune к службе Office 365 Exchange для обеспечения поддержки управления мобильными устройствами с помощью Exchange ActiveSync.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 640d1a5cbd785248cb309bc250c95631295955b3
ms.sourcegitcommit: 71497f0215fc8bed454ac318b0548b1281a8fe0f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33914161"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Настройка соединителя службы Exchange для Intune и Exchange Online

В этой статье объясняется, как подключить службу Microsoft Intune к Exchange Online или к новой выделенной службе Exchange Online. Чтобы определить, используется ли в вашей выделенной среде Exchange Online **новая** или **устаревшая** версия, обратитесь к своему менеджеру по работе с клиентами.

## <a name="service-to-service-connector-requirements"></a>Требования к Service to Service Connector
**Service To Service Connector** поддерживает только Exchange Online и выделенную службу Exchange Online. Требования к локальной инфраструктуре отсутствуют.


|              Требование               |                                                                                                            Дополнительные сведения                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Настроенная и запущенная служба Exchange Online |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Центр управления мобильными устройствами   |                                                       [Укажите Microsoft Intune в качестве центра управления мобильными устройствами](mdm-authority-set.md).                                                       |
|       Версия Microsoft Exchange       |                                                                                      Exchange Online или новая выделенная служба Exchange Online                                                                                      |
|    Синхронизация Active Directory    | Прежде чем использовать любой соединитель Intune, необходимо [настроить синхронизацию Active Directory](/intune/users-add), чтобы локальные пользователи и группы безопасности синхронизировались с имеющимся экземпляром Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Требования к командлетам Exchange

Необходимо создать учетную запись пользователя Exchange Online, которую будет использовать соединитель службы Intune Exchange. Она должна иметь разрешение на выполнение следующих обязательных командлетов Windows PowerShell Exchange.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Настройка службы для соединителя службы

1. Войдите на [портал Azure](http://portal.azure.com) с использованием учетной записи с правами администратора Exchange и разрешениями для командлетов, [приведенных выше](#exchange-cmdlet-requirements). Для настройки подключения Microsoft Intune использует адрес электронной почты пользователя, вошедшего в систему.

2. Выберите **Все службы** в меню слева и введите **Intune** в текстовое поле фильтра.

3. Щелкните **Intune**, чтобы открыть панель мониторинга Microsoft Intune. Выберите **Условный доступ** и в разделе **Установка** щелкните **Соединитель службы Exchange**.

4.  На странице **Условный доступ — соединитель службы Exchange** щелкните **Настроить Service To Service Connector**. 
   
     ![Изображение с выделенной ссылкой "Настроить Service To Service Connector"](media/exchange_service_connector.png)

Service To Service Connector автоматически настроится и синхронизируется со средой Exchange Online или новой выделенной средой Exchange Online.

## <a name="validate-your-exchange-connection"></a>Проверка подключения к Exchange

Успешно настроив соединитель Exchange Service to Service, просмотрите информацию о соединителя Exchange Server на странице **Условный доступ — соединитель службы Exchange**.

Также можно проверить **состояние подключения**, время и дату последней успешной попытки синхронизации.

## <a name="next-steps"></a>Дальнейшие шаги
[Мониторинг условного доступа Exchange в Microsoft Intune](conditional-access-exchange-monitor.md)