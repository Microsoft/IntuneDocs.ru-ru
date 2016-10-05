---
title: "Соединитель с Exchange для Exchange Online | Microsoft Intune"
description: "Подключения Intune к службе Office 365 Exchange для обеспечения поддержки управления мобильными устройствами с помощью Exchange ActiveSync."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Настройка Service To Service Connector Intune для Exchange Online

Эта статья поможет вам подключить Microsoft Intune и Exchange Online или новую службу выделенной среды Exchange Online. Чтобы определить, используется ли в вашей выделенной среде Exchange Online **новая** или **устаревшая** конфигурация, обратитесь к своему менеджеру по работе с клиентами. Intune поддерживает только одно подключение соединителя с Exchange любого типа на подписку.

## Требования к Service To Service Connector
**Service To Service Connector** поддерживает только Exchange Online и новую службу выделенной среды Exchange Online. Требования к локальной инфраструктуре отсутствуют.

|Требование|Дополнительные сведения|
|---------------|--------------------|
|Настроенная и запущенная служба Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Центр управления мобильными устройствами| [Задайте Microsoft Intune в качестве центра управления мобильными устройствами.](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Версия Microsoft Exchange|Exchange Online или новая служба выделенной среды Exchange Online|
|Синхронизация Active Directory|Прежде чем использовать любой соединитель Intune, необходимо [настроить синхронизацию Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), чтобы локальные пользователи и группы безопасности синхронизировались с имеющимся экземпляром Azure Active Directory.|

### Требования к командлетам Exchange

Необходимо создать учетную запись пользователя Exchange Online, которую будет использовать соединитель Intune Exchange. Она должна иметь разрешение на использование консоли администрирования Intune и выполнение обязательных командлетов Windows PowerShell Exchange, приведенных ниже.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Настройка Service To Service Connector

1. Откройте [консоль администрирования Microsoft Intune](http://manage.microsoft.com) с использованием учетной записи с правами администратора Exchange и разрешениями для командлетов, приведенных [выше](#exchange-cmdlet-requirements). Для настройки подключения Microsoft Intune использует адрес электронной почты текущего выполнившего вход пользователя.

2.  На панели ярлыков рабочей области выберите **Администрирование**, а затем — **Управление мобильными устройствами** > **Microsoft Exchange** > **Настройка подключения к Exchange**.
![Страница настройки Service To Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  На странице **Настройка подключения Exchange** щелкните **Настроить службу для соединителя службы**.


Service To Service Connector автоматически настроится и синхронизируется со средой Exchange Online или новой выделенной средой Exchange Online.

## Проверка подключения к Exchange

После успешной настройки соединителя Exchange в [консоли администрирования Microsoft Intune](http://manage.microsoft.com) щелкните **Администрирование**, выберите **Управление мобильными устройствами** > **Microsoft Exchange** и проверьте правильность данных, указанных в разделе **Сведения о подключении к Exchange**.

Также можно проверить время и дату последней успешной попытки синхронизации.



<!--HONumber=Sep16_HO4-->


