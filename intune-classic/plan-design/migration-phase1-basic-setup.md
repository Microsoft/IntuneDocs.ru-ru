---
title: "Базовая настройка Intune | Документация Майкрософт"
description: "В этой статье предоставлены необходимые действия по настройке Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc5e14656b4f6dd883881a8dcb33df1dce6b29d7
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-basic-setup"></a>Этап 1. Базовая настройка

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

После оценки среды нужно установить Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Внешние зависимости развертывания Intune

### <a name="identity"></a>Удостоверение

Intune требуется Azure Active Directory (AAD) в качестве поставщика групп идентификаторов и пользователей.

-   Дополнительные сведения о [требованиях к удостоверениям](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Дополнительные сведения о [требованиях к синхронизации каталогов](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Дополнительные сведения о [требованиях к многофакторной проверке подлинности](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Дополнительные сведения о [планировании групп пользователей и устройств](/intune-classic/deploy-use/plan-your-user-and-device-groups).

-   Дополнительные сведения о [создании групп пользователей и устройств](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

Если ваша организация уже использует Office 365, важно, чтобы Intune использовала ту же среду Azure Active Directory.

### <a name="pki-optional"></a>PKI (необязательно)

Если вы планируете использовать проверку подлинности на основе сертификатов с профилями VPN, Wi-Fi или электронной почты в Intune, следует убедиться в наличии поддерживаемой [инфраструктуры открытых ключей](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles), готовой к созданию и развертыванию профилей сертификатов.

По ссылкам ниже можно получить дополнительные сведения о настройке сертификатов в Intune.

-   [Настройка инфраструктуры сертификатов для SCEP](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Настройка инфраструктуры сертификатов для PFX](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Настройка профилей сертификатов Intune](/intune-classic/deploy-use/configure-intune-certificate-profiles).

-   [Настройка политик доступа к ресурсам](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="task-list-for-an-intune-setup"></a>Список задач для настройки Intune

### <a name="task-1-intune-subscription"></a>Задача 1. Подписка Intune

Перед миграцией в Intune потребуется подписка Intune.

-   [На этой странице](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) приведены инструкции по следующим операциям:

    -   Создание подписки Intune, связанной с новым клиентом AAD.

    -   Связывание подписки Intune при входе в существующий клиент AAD.

### <a name="task-2-assign-intune-user-licenses"></a>Задача 2. Назначение лицензий пользователя Intune

-   Узнайте, как можно [назначить лицензии пользователя Intune](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   Узнайте, как можно [создать пользователей или синхронизировать пользователя из локальной службы Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) (при создании клиента Azure Active Directory).

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Задача 3. Установка Intune в качестве центра MDM

Intune можно управлять с помощью портала Azure или консоли Configuration Manager Current Branch. Мы рекомендуем управлять Intune с [портала Azure](https://portal.azure.com), если вам не нужно интегрировать Intune с развертыванием Configuration Manager Current Branch.

Установите **Intune** в качестве центра MDM, чтобы включить портал Azure. При использовании другого центра MDM служба Intune может передать управление MDM альтернативной консоли управления Майкрософт. Но это случается редко.

> [!IMPORTANT]
> Если вы передаете управление мобильными устройствами службе Intune впервые, ее следует задать в качестве центра управления мобильными устройствами.

-   Узнайте, как [установить центр управления мобильными устройствами](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## <a name="next-step"></a>Дальнейшие действия

[Этап 1. Настройка политик соответствия устройств и управления приложениями](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

