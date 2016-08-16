---
title: "Устранение неполадок в работе соединителя с Exchange | Microsoft Intune"
description: "Устранение неполадок, связанных с работой соединителя Intune с Exchange."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: 04ac69a30f6c1d91fe755f9720fbc2adc51745f7


---

# Устранение неполадок в работе соединителя с Exchange
В этом разделе описывается, как устранять неполадки, которые могут быть связаны с работой соединителя Intune с Exchange.

## Действия по проверке конфигурации соединителя 

Проверьте конфигурацию соединителя с Exchange, а затем убедитесь, что проблема устранена.

- При начальной настройке соединителя с Exchange не забудьте указать учетную запись уведомлений.
- Учетная запись службы соединителя с Exchange должна иметь необходимые разрешения на выполнение командлетов PowerShell, используемых соединителем с Exchange.
- При настройке соединителя с Exchange укажите сервер клиентского доступа (CAS), который должен быть как можно ближе к серверу, где размещен соединитель с Exchange. Задержка взаимодействия между CAS и соединителем с Exchange может привести к задержкам обнаружения устройств, особенно при использовании Office 365 Dedicated.
- Учитывайте, что между синхронизациями соединителя с Exchange и сервера клиентского доступа Exchange существует временной промежуток. Полная синхронизация выполняется один раз в день, а дельта-синхронизация (быстрая) — каждые два часа. Существует вероятность того, что пользователь с только что зарегистрированным устройством при попытке получения доступа столкнется с задержкой.
- 
## Устройство Exchange ActiveSync не обнаруживается из Exchange
Проверьте, выполняется ли синхронизация соединителя с Exchange и сервера Exchange. Для этого найдите журналы полной или дельта-синхронизации. Просмотрите журналы соединителя с Exchange. Если после подключения устройства успешно выполнялась полная или дельта-синхронизация, то этот вариант можно исключить из вероятных причин проблемы. Если синхронизация не выполнялась, соберите журналы синхронизации и вложите их в свой запрос на поддержку.

- Если у пользователя нет лицензии Intune, то соединитель с Exchange не сможет обнаружить устройства.
- Если основной SMTP-адрес пользователя отличается от его имени участника-пользователя в AAD, то соединитель с Exchange не сможет обнаружить устройства для этого пользователя Intune или AAD. Исправьте основной SMTP-адрес.
- Если сервер клиентского доступа, с которым соединитель с Exchange взаимодействует в цикле обнаружения, является сервером клиентского доступа Exchange 2010, при этом одновременно используются серверы почтовых ящиков Exchange 2010 и 2013, то соединитель с Exchange не обнаружит ни одно из устройств пользователей Exchange 2013. Для решения этой проблемы настройте соединитель с Exchange таким образом, чтобы он указывал на сервер клиентского доступа Exchange 2013.  Эта проблема в большей степени относится к топологиям Office 365 Dedicated, однако и в других топологиях рекомендуется указывать на сервер клиентского доступа Exchange 2013.
- Для сред Exchange Dedicated (Office 365 Dedicated) необходимо изначально настроить соединитель с Exchange таким образом, чтобы он указывал на сервер клиентского доступа Exchange 2013 (а не 2010) в выделенной среде, так как он будут взаимодействовать только с этим сервером при выполнении командлетов Powershell.


## Использование Powershell для получения дополнительных сведений о неполадках в работе соединителя с Exchange
- Чтобы получить список всех мобильных устройств для почтового ящика, используйте команду Get-ActiveSyncDeviceStatistics -mailbox mbx
- Чтобы получить список SMTP-адресов для почтового ящика, используйте команду Get-Mailbox -Identity user | select emailaddresses | fl.
- Чтобы получить подробные сведения о состоянии доступа устройства, используйте команду Get-CASMailbox <upn> | fl

### Дальнейшие действия
Если эта информация не помогла, обратитесь в службу поддержки Майкрософт, как описано в статье [Получение поддержки для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO1-->

