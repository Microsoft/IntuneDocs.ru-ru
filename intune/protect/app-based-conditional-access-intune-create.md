---
title: Настройка политики условного доступа на основе приложений в Intune
titleSuffix: Microsoft Intune
description: Узнайте, как настроить политику условного доступа на основе приложений в Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9cbe57d0cf69f036cd36d2c1b95c48b198645e7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723090"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Настройка политик условного доступа на основе приложений в Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Настройте политики условного доступа на основе приложений для приложений, входящих в список утвержденных. В список утвержденных входят приложения, протестированные корпорацией Майкрософт.

> [!IMPORTANT]
> Эта статья описывает, как добавить политику условного доступа на основе приложения. Можно использовать одни и те же действия при добавлении таких приложений, как SharePoint Online, Microsoft Teams и Microsoft Exchange Online, из списка утвержденных приложений.

## <a name="create-app-based-conditional-access-policies"></a>Создание политик условного доступа на основе приложений
Условный доступ — это технология Azure Active Directory (Azure AD). Узел условного доступа, доступ к которому осуществляется из *Intune*, является тем же узлом, доступ к которому осуществляется из *Azure AD*. Это означает, что для настройки политик нет необходимости переключаться между Intune и Azure AD.

> [!IMPORTANT]
> У вас должна быть лицензия Azure AD Premium для создания политик условного доступа на портале Intune.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Создание политики условного доступа на базе приложений

> [!IMPORTANT]
> Перед использованием политик условного доступа на основе приложений к приложениям должны быть применены [политики защиты приложений Intune](../apps/app-protection-policies.md).

1. На **панели мониторинга Intune** выберите **Условный доступ**.

2. На панели **Политики** выберите пункт **Создать политику**, чтобы создать новую политику условного доступа на основе приложений.

4. Указав имя политики и настроив параметры, доступные в разделе **Назначения**, выберите **Предоставить** в разделе **Управление доступом**.

5. Выберите **Требовать утвержденное клиентское приложение**, щелкните **Выбрать**, а затем **Создать** для сохранения новой политики.

## <a name="next-steps"></a>Дальнейшие шаги
[Блокировка приложений, не поддерживающих современные средства проверки подлинности](app-modern-authentication-block.md)

## <a name="see-also"></a>См. также

[Защита данных приложения с помощью политик защиты приложений](../apps/app-protection-policies.md)
[Условный доступ в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
