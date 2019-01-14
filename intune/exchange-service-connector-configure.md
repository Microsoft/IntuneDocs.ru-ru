---
title: Соединитель Intune с Exchange для Exchange Online | Microsoft Intune
description: Подключения Intune к службе Office 365 Exchange для обеспечения поддержки управления мобильными устройствами с помощью Exchange ActiveSync.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9845ed1b809b611975c07c6c8335acd237d845c0
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816707"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Настройка соединителя службы Exchange для Intune и Exchange Online
В этой статье объясняется, как подключить службу Microsoft Intune к Exchange Online или к новой выделенной службе Exchange Online. Чтобы определить, используется ли в вашей выделенной среде Exchange Online **новая** или **устаревшая** версия, обратитесь к своему менеджеру по работе с клиентами.

Используя **соединитель служб**, вы можете управлять устройствами Exchange ActiveSync (EAS) и управляемыми устройствами Intune с одной консоли администрирования.  Соединитель не требуется для настройки условного доступа к Exchange Online.

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

1. Войдите на [портал Azure](https://portal.azure.com) с учетной записью, которая обладает правами администратора Exchange, разрешениями для командлетов, [приведенными выше](#exchange-cmdlet-requirements), действительной лицензией Intune и ролью глобального администратора. Для настройки подключения Microsoft Intune использует адрес электронной почты пользователя, вошедшего в систему.

2. Выберите **Все службы** в меню слева и введите **Intune** в текстовое поле фильтра.

3. Щелкните **Intune**, чтобы открыть панель мониторинга Microsoft Intune. Выберите **Условный доступ** и в разделе **Установка** щелкните **Соединитель службы Exchange**.

4.  На странице **Условный доступ — соединитель службы Exchange** щелкните **Настроить Service To Service Connector**. 
   
     ![Изображение с выделенной ссылкой "Настроить Service To Service Connector"](media/exchange_service_connector.png)

Service To Service Connector автоматически настроится и синхронизируется со средой Exchange Online или новой выделенной средой Exchange Online.

## <a name="validate-your-exchange-connection"></a>Проверка подключения к Exchange

Успешно настроив соединитель Exchange Service to Service, просмотрите информацию о соединителя Exchange Server на странице **Условный доступ — соединитель службы Exchange**.

Также можно проверить **состояние подключения**, время и дату последней успешной попытки синхронизации.

 