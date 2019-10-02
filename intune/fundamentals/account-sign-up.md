---
title: Регистрация или вход в Microsoft Intune
description: Описывается, как зарегистрировать подписку Microsoft Intune или выполнить вход, чтобы начать использовать подписку.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f3ce07a-b718-42a9-bace-f99a8b8abd94
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: fe3f856a2faba2c140fa92fa9ab486213c38a1c1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722258"
---
# <a name="sign-up-or-sign-in-to-microsoft-intune"></a>Регистрация или вход в Microsoft Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

В этом разделе системные администраторы узнают, как зарегистрировать учетную запись Intune.

Прежде чем регистрироваться в Intune, проверьте, нет ли у вас учетной записи Microsoft Online Services, соглашения Enterprise или эквивалентного соглашения корпоративного лицензирования. Соглашение о корпоративном лицензировании Майкрософт или подписка на другие облачные службы Майкрософт, такие как Office 365, обычно включает рабочую или учебную учетную запись.

Если уже есть рабочая или учебная учетная запись, выполните **вход** под этой учетной записью и добавить в свою подписку Intune. Если же нет, **зарегистрируйте** новую учетную запись для использования Intune в своей организации.

>[!WARNING]
>Зарегистрировав новую учетную запись, вы не сможете объединить ее с уже существующей рабочей или учебной учетной записью.

## <a name="how-to-sign-up-for-intune"></a>Регистрация для использования Intune

1. Откройте страницу [Регистрация в Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

   ![Снимок экрана веб-страницы для регистрации пробной учетной записи Microsoft Intune](./media/account-sign-up/account-sign-up-site.png)

2. На странице регистрации выполните вход или зарегистрируйтесь для управления новой подпиской Intune.

## <a name="post-sign-up-considerations"></a>Действия после регистрации
После регистрации новой учетной записи на электронный адрес, указанный в процессе регистрации, отправляется сообщение с информацией об учетной записи. Оно является подтверждением активации подписки.

После регистрации вы будете направлены в Центр администрирования Microsoft 365, где можно добавить пользователей и назначить им лицензии. Если вы будете использовать только облачные учетные записи с именем домена по умолчанию onmicrosoft.com, то добавить пользователей и назначить лицензии можно уже на этом этапе. Если же вы планируете использовать [имя личного домена организации](custom-domain-name-configure.md) или хотите [синхронизировать учетные записи пользователей](users-add.md#sync-active-directory-and-add-users-to-intune) из локальной службы Active Directory, можно закрыть это окно браузера.

## <a name="sign-in-to-microsoft-intune"></a>Вход в Microsoft Intune
После регистрации в Intune можно выполнять администрирование службы, войдя [в Intune](https://go.microsoft.com/fwlink/?linkid=2090973) с использованием [любого устройства с поддерживаемым браузером](supported-devices-browsers.md#intune-supported-web-browsers).

По умолчанию учетная запись должна иметь одно из следующих разрешений в Azure AD:
- глобальный администратор
- Администратор служб Intune (также известный как администратор Intune).

Чтобы предоставить доступ к администрированию службы для пользователей с другими разрешениями, перейдите к статье об [управлении доступом на основе ролей](role-based-access-control.md).

### <a name="intune-admin-portal-url"></a>URL-адрес портала администрирования Intune

Центр администрирования Microsoft 365: https://devicemanagement.microsoft.com

Портал Intune Azure: https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade

Intune для образования: https://intuneeducation.portal.azure.com

Классический портал Intune: https://manage.microsoft.com Классический портал Intune используется только для управления устройствами, зарегистрированными с помощью клиентского программного обеспечения Intune.

### <a name="urls-for-intune-services-provided-by-office-365"></a>URL-адреса для служб Intune, предоставляемых Office 365

Microsoft 365 бизнес: https://portal.microsoft.com/adminportal

Управление мобильными устройствами Office 365: https://portal.office.com/adminportal/home#/MifoDevices

## <a name="see-also"></a>См. также
[Вы не можете войти в Office 365, Azure или Intune](https://support.microsoft.com/help/2412085)
