---
title: Настройка имени домена
titleSuffix: Microsoft Intune
description: Добавление личного доменного имени для подписки Microsoft Intune
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04708842373abf296b5350d9f77e02fa08ce48ed
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414618"
---
# <a name="configure-a-custom-domain-name"></a>Настройка имени домена

В этой статье администраторы узнают, как создать запись DNS CNAME, чтобы упростить или настроить процедуру входа с помощью Microsoft Intune.

Когда организация регистрируется в облачной службе Майкрософт, такой как Intune, ей предоставляется исходное доменное имя в Azure Active Directory (AD) следующего вида: **имя_домена.onmicrosoft.com**. В этом примере **имя_домена** — это имя домена, выбранное при регистрации, а **onmicrosoft.com** — это суффикс, назначаемый учетным записям, которые вы добавляете в подписку. Вместо доменного имени, предоставленного вам при подписке, вы можете настроить для своей организации пользовательский домен для доступа к Intune.

Перед созданием учетных записей пользователей или синхронизацией локального каталога AD мы настоятельно рекомендуем решить, будет ли использоваться только домен .onmicrosoft.com или нужно добавить одно или несколько настраиваемых доменных имен. Чтобы упростить управление пользователями, настройте пользовательский домен до того, как добавить пользователей. Установка личного домена позволяет пользователям выполнять вход, указывая те же учетные данные, под которыми они получают доступ к другим ресурсам домена.

При оформлении подписки на облачную службу Майкрософт имеющийся экземпляр службы становится [клиентом Microsoft Azure AD](https://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), который предоставляет службы удостоверений и каталогов для вашей облачной службы. А поскольку задачи по настройке Intune для использования имени личного домена организации не отличаются от выполняемых для клиентов Azure AD, используйте сведения и процедуры из статьи [Добавление домена](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Дополнительные сведения о пользовательских доменах см. в статье [Общие сведения об именах личных доменов в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Переименовать или удалить исходное имя домена onmicrosoft.com нельзя, Вы можете добавлять, верифицировать и удалять личные имена доменов в Intune, указывая на их принадлежность вашей организации.

## <a name="to-add-and-verify-your-custom-domain"></a>Добавление и проверка пользовательского домена

1. Откройте [Центр администрирования Microsoft 365](https://admin.microsoft.com/) и войдите под учетной записью администратора.

2. В области навигации выберите **Настройка** &gt; **Домены**.

3. Выберите **Добавить домен** и введите имя пользовательского домена. Выберите **Далее**.
   ![Снимок экрана, демонстрирующий выбор меню "Параметры > Домены" в Центре администрирования Microsoft 365 и добавление нового доменного имени](./media/custom-domain-name-configure/domain-custom-add.png)
4. Откроется диалоговое окно **Проверка домена**, в котором можно указать значения для создания записи TXT у поставщика услуг размещения DNS.
    - **Пользователи GoDaddy**. Центр администрирования Microsoft 365 перенаправит вас на страницу входа GoDaddy. Запись типа TXT создается автоматически после ввода учетных данных и принятия соглашения о разрешении изменения домена. Можно также [создать запись типа TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Пользователи Register.com**. Выполните [пошаговые инструкции](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) для создания записи типа TXT.
5. [Возможно, потребуется создать дополнительные записи DNS для регистраций Intune](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium).

Шаги для добавления и проверки личного домена также можно [выполнить в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Вы можете подробнее узнать о [своем первоначальном домене onmicrosoft.com в Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)

Вы можете узнать о том, как [упростить регистрацию Windows без Azure AD Premium](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium), создав запись DNS CNAME, которая перенаправляет регистрацию на серверы Intune.
