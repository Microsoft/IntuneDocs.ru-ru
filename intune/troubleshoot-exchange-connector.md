---
title: Устранение проблем в работе соединителя с Exchange
titleSuffix: Microsoft Intune
description: Устранение неполадок, связанных с работой соединителя Intune с локальной организацией Exchange.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/18/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd6d24b5a897c5a6bcd075da111fa579d8d74154
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044553"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Устранение неполадок в работе соединителя Intune с локальной организацией Exchange

Эта статья описывает устранение неполадок, связанных с работой соединителя Intune с локальной организацией Exchange.

## <a name="steps-for-checking-the-connector-configuration"></a>Действия по проверке конфигурации соединителя 

Проверьте [установку соединителя Intune с локальной организацией Exchange](exchange-connector-install.md), чтобы убедиться, что соединитель настроен правильно. Ниже приведены некоторые распространенные проблемы. После внесения исправлений проверьте, устранена ли проблема.

 - В диалоговом окне "Microsoft Intune Exchange Connector" убедитесь, что указана учетная запись пользователя, имеющая соответствующие разрешения на выполнение [необходимых командлетов Exchange в Windows PowerShell](exchange-connector-install.md#exchange-cmdlet-requirements).
- Включите уведомления и укажите учетную запись уведомлений.
 - При настройке соединителя Exchange укажите сервер клиентского доступа (CAS), расположенный как можно ближе к серверу, где размещен соединитель Exchange. Задержка взаимодействия между CAS и соединителем Exchange может привести к задержкам обнаружения устройств, особенно при использовании Exchange Online (цен. категория "Выделенный").
 - Пользователь с только что зарегистрированным устройством может испытывать задержки доступа, пока соединитель Exchange синхронизируется с Exchange CAS. Полная синхронизация выполняется один раз в день, а разностная (быстрая) синхронизация — несколько раз в день.  Чтобы минимизировать задержки, вы можете [принудительно выполнить быструю или полную синхронизацию вручную](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Устройство Exchange ActiveSync не обнаруживается из Exchange
[Отслеживайте активность соединителя Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support), чтобы узнать, выполняется ли синхронизация соединителя Exchange с сервером Exchange. Если после присоединения устройства успешно выполнялась полная или быстрая синхронизация, вы можете выполнить поиск других возможных проблем, указанных ниже. Если синхронизация не выполнялась, соберите журналы синхронизации и вложите их в свой запрос на поддержку.

 - У пользователей должна быть лицензия Intune, иначе соединитель Exchange не обнаружит их устройства.
 - Если основной SMTP-адрес пользователя отличается от его имени субъекта-пользователя в Azure Active Directory (Azure AD), то соединитель Exchange не сможет обнаружить устройства для этого пользователя. Для устранения проблемы исправьте основной SMTP-адрес.
 - Если в вашей среде используются серверы почтовых ящиков Exchange 2010 и Exchange 2013, рекомендуется нацелить соединитель Exchange на сервер клиентского доступа Exchange 2013. В противном случае, если соединитель Exchange настроен для взаимодействия с сервером клиентского доступа Exchange 2010, соединитель Exchange не будет обнаруживать устройства пользователей Exchange 2013. 
- Для сред Exchange (цен. категория "Выделенный") нужно изначально настроить соединитель Exchange таким образом, чтобы он указывал на сервер клиентского доступа Exchange 2013 (а не Exchange 2010) в выделенной среде, так как при выполнении командлетов Powershell соединитель будет взаимодействовать только с этим сервером.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Использование Powershell для получения дополнительных сведений о неполадках в работе соединителя с Exchange
- Чтобы получить список всех мобильных устройств для почтового ящика, используйте команду Get-ActiveSyncDeviceStatistics -mailbox mbx.
- Чтобы получить список SMTP-адресов для почтового ящика, используйте команду Get-Mailbox -Identity user | select emailaddresses | fl.
- Чтобы получить подробные сведения о состоянии доступа устройства, используйте команду Get-CASMailbox <upn> | fl.

### <a name="next-steps"></a>Дальнейшие шаги
Если эта информация не помогла, вы можете [получить поддержку для Microsoft Intune](get-support.md).
