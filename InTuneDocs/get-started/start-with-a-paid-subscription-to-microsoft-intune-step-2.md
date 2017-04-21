---
title: "Настройка имени личного домена | Документы Майкрософт"
description: "Добавление пользовательского домена для подписки Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 86062a73092f6e438de7a315d9ec1c2f395c9c50
ms.lasthandoff: 04/14/2017


---


# <a name="configure-a-custom-domain-name"></a>Настройка имени домена

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В этом разделе администраторы узнают, как создать запись DNS CNAME, чтобы упростить или настроить процедуру входа.

При регистрации организации в облачной службе Майкрософт, такой как Intune, ей предоставляется исходное доменное имя в Azure Active Directory (AD) следующего вида: **имя_домена.onmicrosoft.com**. В этом примере **имя_домена** — это имя домена, выбранное при регистрации, а **onmicrosoft.com** — суффикс, назначенный учетным записям, добавленным в подписку. Если организации принадлежит личный домен, можно настроить имеющийся экземпляр Intune для использования этого имени домена вместо имени, предоставленного с подпиской.

Перед созданием учетных записей пользователей или синхронизацией локального каталога AD мы настоятельно рекомендуем решить, будет ли использоваться только домен .onmicrosoft.com или нужно добавить одно или несколько настраиваемых доменных имен. Настройка домена до добавления пользователей позволяет упростить управление удостоверениями пользователей для подписки, позволив пользователям выполнять вход с учетными данными, которые они используют для доступа к другим ресурсам домена.

При оформлении подписки на облачную службу Майкрософт имеющийся экземпляр службы становится [клиентом Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), который предоставляет службы удостоверений и каталогов для вашей облачной службы. А поскольку задачи по настройке Intune для использования имени личного домена организации не отличаются от выполняемых для клиентов Azure AD, используйте сведения и процедуры из статьи [Добавление домена](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Дополнительные сведения об использовании личного домена с облачной службой Майкрософт см. в статье [Общие сведения об именах личных доменов в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Переименовать или удалить исходное имя домена нельзя. Однако можно добавлять, проверять и удалять имена пользовательских доменов для использования с Intune, что полезно, когда нужно как-то обозначить свой бизнес.

## <a name="to-add-and-verify-your-custom-domain"></a>Добавление и проверка пользовательского домена

1. Перейдите на [портал управления Office 365](https://portal.office.com/Admin/Default.aspx) и войдите в учетную запись администратора.

2. В области навигации выберите **Параметры** &gt; **Домены**.

3. Выберите **Добавить домен** и введите имя пользовательского домена.

4. Откроется диалоговое окно **Проверка домена**, в котором можно указать значения для создания записи TXT у поставщика услуг размещения DNS.
    - **Пользователи GoDaddy**: портал управления Office 365 перенаправит вас на страницу входа GoDaddy. Запись типа TXT создается автоматически после ввода учетных данных и принятия соглашения о разрешении изменения домена. Можно также [создать запись типа TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Пользователи Register.com**: выполните [пошаговые инструкции](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) для создания записи типа TXT.

    > [!TIP]
    > Обязательно создайте DNS-псевдоним (CNAME) для [регистрации устройств с Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) во время внесения изменений у своего поставщика услуг размещения DNS.

Шаги для добавления и проверки личного домена также можно [выполнить в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Вы можете подробнее узнать о [своем первоначальном домене onmicrosoft.com в Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)

>[!div class="step-by-step"]

>[&larr; **Вход в Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md) [**Добавление пользователей в Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  

