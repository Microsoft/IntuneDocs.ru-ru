---
title: Настройка политики условного доступа на основе приложений в Intune
titlesuffix: Microsoft Intune
description: Узнайте, как настроить политику условного доступа на основе приложений в Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2026a446ffef3bd845affe45a7732ef3ab8ec24
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842923"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Настройка политик условного доступа на основе приложений в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настройте политики условного доступа на основе приложений для приложений, входящих в список утвержденных. В список утвержденных входят приложения, протестированные корпорацией Майкрософт.

> [!IMPORTANT]
> Эта статья описывает, как добавить политику условного доступа на основе приложения. Можно использовать одни и те же действия при добавлении таких приложений, как SharePoint Online, Microsoft Teams и Microsoft Exchange Online, из списка утвержденных приложений.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Создание политик условного доступа на основе приложений в рабочей нагрузке Azure AD

ИТ-администраторы могут создавать политики условного доступа на основе приложений из рабочей нагрузки Azure AD. При этом вам не придется переключаться между рабочими нагрузками Azure и Intune.

> [!IMPORTANT]
> У вас должна быть лицензия Azure AD Premium для создания политик условного доступа к Azure AD на портале Intune Azure.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Создание политики условного доступа на базе приложений

> [!IMPORTANT]
> Перед использованием политик условного доступа на основе приложений к приложениям должны быть применены [политики защиты приложений Intune](app-protection-policies.md).

1. На **панели мониторинга Intune** выберите **Условный доступ**.

2. На панели **Политики** выберите пункт **Создать политику**, чтобы создать новую политику условного доступа на основе приложений.

4. Указав имя политики и настроив параметры, доступные в разделе **Назначения**, выберите **Предоставить** в разделе **Управление доступом**.

5. Выберите **Требовать утвержденное клиентское приложение**, щелкните **Выбрать**, а затем **Создать** для сохранения новой политики.

## <a name="next-steps"></a>Дальнейшие шаги
[Блокировка приложений, не поддерживающих современные средства проверки подлинности](app-modern-authentication-block.md)

### <a name="see-also"></a>См. также

[Защита данных приложения с помощью политик защиты приложений](app-protection-policies.md)
[Условный доступ в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
