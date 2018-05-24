---
title: Настройка политики условного доступа на основе приложений в Intune
description: Узнайте, как настроить политику условного доступа на основе приложений в Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c505e881fe06d6f4da217533d0507731ac22a29f
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Настройка политик условного доступа на основе приложений в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

В этой статье описывается, как настроить политики условного доступа на основе приложений для приложений, входящих в список утвержденных. В список утвержденных входят приложения, протестированные корпорацией Майкрософт.

> [!IMPORTANT]
> Эта статья описывает, как добавить политику условного доступа на основе приложения. Обратите внимание, что можно использовать одни и те же действия при добавлении приложений, таких как SharePoint Online, Microsoft Teams и Microsoft Exchange Online, из списка утвержденных приложений.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Создание политик условного доступа на основе приложений в рабочей нагрузке Azure AD

ИТ-администраторы могут создавать политики условного доступа на основе приложений из рабочей нагрузки Azure AD. Это удобно, так как вам не нужно переключаться между рабочими нагрузками Azure и Intune.

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

### <a name="see-also"></a>См. также:

[Защита данных приложения с помощью политик защиты приложений](app-protection-policies.md)
[Условный доступ в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
