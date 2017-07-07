---
title: "Базовая настройка Intune"
description: "В этой статье предоставлены необходимые действия по настройке Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Базовая настройка

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

После оценки среды нужно установить Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Внешние зависимости развертывания Intune

### <a name="identity"></a>Удостоверение

Intune требуется Azure Active Directory (AAD) в качестве поставщика групп идентификаторов и пользователей.

-   Дополнительные сведения о [требованиях к удостоверениям](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Дополнительные сведения о [требованиях к синхронизации каталогов](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Дополнительные сведения о [требованиях к многофакторной проверке подлинности](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Дополнительные сведения о [планировании групп пользователей и устройств](/intune/users-permissions-add).

-   Дополнительные сведения о [создании групп пользователей и устройств](/intune/groups-get-started).

Если ваша организация уже использует Office 365, важно, чтобы Intune использовала ту же среду Azure Active Directory.

### <a name="pki-optional"></a>PKI (необязательно)

Если вы планируете использовать проверку подлинности на основе сертификатов с профилями VPN, Wi-Fi или электронной почты в Intune, следует убедиться в наличии поддерживаемой [инфраструктуры открытых ключей](/intune/certificates-configure), готовой к созданию и развертыванию профилей сертификатов.

По ссылкам ниже можно получить дополнительные сведения о настройке сертификатов в Intune.

-   [Настройка инфраструктуры сертификатов для SCEP](/intune/certificates-scep-configure).

-   [Настройка инфраструктуры сертификатов для PFX](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Список задач для настройки Intune

### <a name="task-1-intune-subscription"></a>Задача 1. Подписка Intune

Перед миграцией в Intune потребуется подписка Intune.

-   [На этой странице](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) приведены инструкции по следующим операциям:

    -   Создание подписки Intune, связанной с новым клиентом AAD.

    -   Связывание подписки Intune при входе в существующий клиент AAD.

### <a name="task-2-assign-intune-user-licenses"></a>Задача 2. Назначение лицензий пользователя Intune

-   Узнайте, как можно [назначить лицензии пользователя Intune](licenses-assign.md).

-   Узнайте, как можно [создать пользователей или синхронизировать пользователя из локальной службы Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) (при создании клиента Azure Active Directory).

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Задача 3. Установка Intune в качестве центра MDM

Intune можно управлять с помощью портала Azure или консоли Configuration Manager Current Branch. Мы рекомендуем управлять Intune с [портала Azure](https://portal.azure.com), если вам не нужно интегрировать Intune с развертыванием Configuration Manager Current Branch.

Установите **Intune** в качестве центра MDM, чтобы включить портал Azure. При использовании другого центра MDM служба Intune может передать управление MDM альтернативной консоли управления Майкрософт. Но это случается редко.

> [!IMPORTANT]
> Если вы передаете управление мобильными устройствами службе Intune впервые, ее следует задать в качестве центра управления мобильными устройствами.

-   Узнайте, как [установить центр управления мобильными устройствами](/intune/mdm-authority-set).

## <a name="next-step"></a>Дальнейшие действия

[Настройка политик управления устройствами и приложениями](migration-guide-configure-policies.md)
