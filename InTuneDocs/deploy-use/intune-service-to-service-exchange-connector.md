---
title: "Соединитель с Exchange для Exchange Online | Microsoft Intune"
description: "Подключения Intune к службе Office 365 Exchange для обеспечения поддержки управления мобильными устройствами с помощью Exchange ActiveSync."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: b6d67391b50954e591817610164d8fe80fda8fd5


---

# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Настройка Service To Service Connector Intune для Exchange Online

Эта статья поможет вам подключить Microsoft Intune и Exchange Online или новую выделенную службу Exchange Online. Чтобы определить, используется ли в вашей выделенной среде Exchange Online **новая** или **устаревшая** версия, обратитесь к своему менеджеру по работе с клиентами. Intune поддерживает только одно подключение соединителя с Exchange любого типа на подписку.

## <a name="service-to-service-connector-requirements"></a>Требования к Service to Service Connector
**Service To Service Connector** поддерживает только Exchange Online и выделенную службу Exchange Online. Требования к локальной инфраструктуре отсутствуют.

|Требование|Дополнительные сведения|
|---------------|--------------------|
|Настроенная и запущенная служба Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Центр управления мобильными устройствами| [Укажите Microsoft Intune в качестве центра управления мобильными устройствами](prerequisites-for-enrollment.md#step-2-set-mdm-authority).|
|Версия Microsoft Exchange|Exchange Online или новая выделенная служба Exchange Online|
|Синхронизация Active Directory|Прежде чем использовать любой соединитель Intune, необходимо [настроить синхронизацию Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), чтобы локальные пользователи и группы безопасности синхронизировались с имеющимся экземпляром Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Требования к командлетам Exchange

Необходимо создать учетную запись пользователя Exchange Online, которую будет использовать соединитель Intune Exchange. Она должна иметь разрешение на использование консоли администрирования Intune и выполнение следующих обязательных командлетов Windows PowerShell Exchange, приведенных ниже.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Настройка службы для соединителя службы

1. Откройте [консоль администрирования Microsoft Intune](http://manage.microsoft.com) с использованием учетной записи с правами администратора Exchange и разрешениями для командлетов, [приведенных выше](#exchange-cmdlet-requirements). Для настройки подключения Microsoft Intune использует адрес электронной почты пользователя, вошедшего в систему.

2.  На панели ярлыков рабочей области последовательно выберите пункты **Администрирование**>**Управление мобильными устройствами** > **Microsoft Exchange** > **Настройка подключения Exchange**.
![Страница настройки Service To Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  На странице **Настройка подключения Exchange** щелкните **Настроить службу для соединителя службы**.


Service To Service Connector автоматически настроится и синхронизируется со средой Exchange Online или новой выделенной средой Exchange Online.

## <a name="validate-your-exchange-connection"></a>Проверка подключения к Exchange

После успешной настройки Exchange Connector перейдите в [консоль администрирования Microsoft Intune](http://manage.microsoft.com). Последовательно выберите пункты **Администрирование**> **Управление мобильными устройствами** > **Microsoft Exchange**. Убедитесь, что указанные сведения отображаются в разделе **Сведения о подключении Exchange**.

Также можно проверить время и дату последней успешной попытки синхронизации.



<!--HONumber=Dec16_HO2-->

