---
title: "Соединитель Exchange для размещенного Exchange | Microsoft Intune"
description: "Подключения Intune к службе Office 365 Exchange для обеспечения поддержки управления мобильными устройствами с помощью Exchange ActiveSync."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 63697222f024169d9450b9f4fea8c666353e72cc


---

# Настройка Service To Service Connector Intune для Exchange Online

Используйте эти сведения для подключения Microsoft Intune и службы Exchange Online, размещенной в Office 365.

## Требования к Service To Service Connector
**Service To Service Connector** поддерживает только размещенный Exchange. Требования к локальной инфраструктуре отсутствуют.

|Требование|Дополнительные сведения|
|---------------|--------------------|
|Размещенный Exchange настроен и запущен|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Центр управления мобильными устройствами| [Задайте Microsoft Intune в качестве центра управления мобильными устройствами.](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Версия Microsoft Exchange|Наличие подписки Office 365 с клиентом Exchange Server 2013 или более поздней версии Пока клиентом является Exchange Server 2013, соединитель будет поддерживать Exchange Server 2010 в той же самой среде.|
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


Service To Service Connector будет автоматически настроен и синхронизирован со средой размещенного Exchange.

## Проверка подключения к Exchange

После успешной настройки соединителя Exchange в [консоли администрирования Microsoft Intune](http://manage.microsoft.com) щелкните **Администрирование**, выберите **Управление мобильными устройствами** > **Microsoft Exchange** и проверьте правильность данных, указанных в разделе **Сведения о подключении к Exchange**.

Также можно проверить время и дату последней успешной попытки синхронизации.



<!--HONumber=Jul16_HO3-->


