---
title: "Настройка Skycure для использования единого входа Azure Active Directory (SSO) | Документы Майкрософт"
description: "Настройка Skycure для использования единого входа Azure Active Directory (SSO)"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 228cecad4dc459e18d10e95253118943197bc55d
ms.lasthandoff: 03/22/2017


---

# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Настройка Skycure для использования единого входа Azure Active Directory (SSO)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

При интеграции Intune и Skycure используется единый вход Azure AD. Вот его основные преимущества.

-   **Администраторы** могут использовать одни и те же учетные данные без необходимости вводить их повторно при каждом входе и выходе для консоли управления Skycure и порталов Microsoft (Intune, Azure).

-   **Конечные пользователи** могут использовать одни и те же учетные данные Azure AD без необходимости вводить их повторно при каждом входе и выходе для приложений Skycure.

Ниже приведены действия для интеграции Skycure с единым входом Azure Active Directory (SSO).

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Для получения идентификатора клиента Azure Active Directory

Нужно получить идентификатор клиента Azure AD.

1.  Перейдите на [портал Azure](https://portal.azure.com/) и войдите с помощью своих учетных данных.

2.  Вы увидите **панель мониторинга**; выберите **Azure Active Directory**.

![Панель мониторинга Azure AD](../media/mtp/skycure-sso-1.png)

1.  Откроется колонка **Azure Active Directory**; выберите **Свойства**.

![Колонка свойств Azure AD](../media/mtp/skycure-sso-2.png)

1.  Нажмите **значок копирования** под **идентификатором клиента AD** в колонке **Свойства Azure Active Directory**.

> Вставьте скопированный идентификатор клиента AD в текстовый файл для использования далее. Этот идентификатор потребуется позже в процессе интеграции Skycure и Intune.

![Панель мониторинга Azure AD](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Разрешить Skycure взаимодействие с Azure Active Directory

1.  Введите в браузере следующий URL-адрес. Вместо **DIRECTORY_ID** введите идентификатор клиента Azure Active Directory, сохраненный ранее в текстовом файле.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Нужно войти в систему с использованием учетных данных Azure Active Directory. Нажмите кнопку **Принять** для продолжения.

![Страница Azure AD Dlogin](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Создание группы безопасности Azure AD для Skycure (необязательно)

Вам может понадобиться создать отдельную группу для пользователей, у которых работает Skycure (например, "Пользователи Skycure"). Это может быть полезно при анализе действий Skycure через отчеты.

-   Дополнительные сведения о том, [как создать группу и добавить членов в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Также можно использовать существующую группу безопасности Azure AD.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Настройка учетной записи Azure AD для интеграции Intune и Skycure

1.  В [консоли управления Skycure](https://aad.skycure.com/) введите идентификатор клиента Azure Active Directory, ранее сохраненный в текстовом файле.

![Поле идентификатора клиента AD Azure в консоли управления Skycure](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure проверяет существование идентификатора клиента Azure AD, запрашивая Azure AD. После нахождения идентификатора администратор может переходить к следующему шагу (базовой настройке).

## <a name="next-steps"></a>Дальнейшие действия

[Скачать политику конфигурации приложения Skycure для iOS](https://docs.microsoft.com/intune/deploy-use/download-skycure-ios-app-configuration-policy)

