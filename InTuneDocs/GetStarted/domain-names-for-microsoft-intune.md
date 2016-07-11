---
title: "Доменные имена для Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d99669f90fe7ebec7854b7a800b09b0685c314e
ms.openlocfilehash: aaede1500f28c6eb8c2a21924d7c3b7f633eca26


---



# Управление пользовательскими доменами с помощью Microsoft Intune

Шаги для добавления и проверки пользовательского домена можно [выполнить в Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

При регистрации организации в облачной службе Майкрософт, такой как Intune, ей предоставляется исходное доменное имя в Azure Active Directory, которое имеет следующий вид: **имя_домена.onmicrosoft.com**. В этом примере **имя_домена** — это имя домена, выбранное при регистрации, а **onmicrosoft.com** — суффикс, назначенный учетным записям, добавленным в подписку.

Переименовать или удалить исходное имя домена нельзя. Однако можно добавлять, проверять и удалять имена пользовательских доменов для использования с Intune, что полезно, когда нужно как-то обозначить свой бизнес.

## Добавление и проверка пользовательского домена 

1. Перейдите на [портал управления Office 365](https://portal.office.com/Admin/Default.aspx) и войдите в учетную запись администратора.
    > [!IMPORTANT]
    > В объявлении     [Портал учетных записей Intune объединен с порталом управления Office 365](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) имеются дополнительные сведения о том, где осуществляется управление пользователями, группами и доменами Microsoft Intune.
2. В области навигации выберите **Параметры** &gt; **Домены**.
3. Выберите **Добавить домен** и введите имя пользовательского домена.
4. Откроется диалоговое окно **Проверка домена**, в котором можно указать значения для создания записи TXT у поставщика услуг размещения DNS.
    > [!TIP]
    > При использовании домена GoDaddy портал управления Office 365 перенаправит вас на страницу входа GoDaddy. Запись TXT создается автоматически после ввода учетных данных и принятия соглашения о разрешении изменения домена.
    > 
    > Также можно [создать запись TXT вручную при использовании домена GoDaddy](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US) на основании значений, предоставленных на этом этапе.

    > [!NOTE]
    > Выполните [пошаговые инструкции](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) для создания записи TXT при использовании домена Register.com на основании значений, предоставленных на этом этапе.

5. Обязательно создайте DNS-псевдоним (CNAME) для [регистрации устройств Windows](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) во время внесения изменений у своего поставщика услуг размещения DNS.

В гибридной облачной среде после добавления имени пользовательского домена и подтверждения того, что он принадлежит вашей организации, можно продолжить управление учетными записями пользователей в локальном каталоге Active Directory, а затем синхронизировать его с Azure AD.

## Синхронизация локальных пользователей с Azure AD##

1. [Добавьте суффикс имени участника-пользователя](https://technet.microsoft.com/en-us/library/cc772007.aspx) для своего пользовательского домена в локальном каталоге Active Directory.
2. Задайте новый суффикс имени участника-пользователя для локальных пользователей, которых планируется импортировать.
3. Запустите [синхронизацию Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) для объединения локальных пользователей с Azure AD.
4. После успешной синхронизации данных учетной записи пользователя можно назначить лицензии Microsoft Intune с помощью [портала управления Office 365](https://portal.office.com/Admin/Default.aspx).

### См. также

[Обзор исходного домена onmicrosoft.com в Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Предварительные сведения перед началом работы с Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jun16_HO5-->


