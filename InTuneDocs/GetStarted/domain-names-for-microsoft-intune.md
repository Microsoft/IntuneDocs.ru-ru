---
# required metadata

title: Доменные имена для Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Доменные имена для Microsoft Intune

Перед настройкой Microsoft Intune ознакомьтесь с этим разделом и другими требованиями в разделе [Предварительные сведения для установки Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

При регистрации организации в облачной службе Майкрософт, такой как Intune, ей предоставляется доменное имя, которое имеет следующий вид: **contoso.onmicrosoft.com**. В этом примере **contoso** — это имя, выбранное при регистрации, а **onmicrosoft.com** — суффикс, назначенный учетным записям, добавленным в подписку. После завершения процесса регистрации имя домена изменить нельзя. Однако глобальный администратор может добавлять собственные имена доменов, которые должны использоваться со службой, или удалять ранее добавленные домены.

По умолчанию при использовании домена onmicrosoft каждый импортируемый пользователь к своему имени участника-пользователя (UPN) получает суффикс **onmicrosoft.com**.

Чтобы использовать собственное доменное имя, а не имя, полученное при регистрации, можно добавить его в Azure Active Directory. После того, как подтвердится, что добавленный домен действительно принадлежит вам, можно создавать учетные записи и группы, включающие это имя домена, путем изменения записей DNS на сайте поставщика размещения DNS. Для упрощения управления учетными записями пользователей при использовании личного домена настройте имя личного домена для своей подписки перед синхронизацией пользователей из локальной службы Active Directory.

Доменные имена и записи ресурсов DNS настраиваются для Intune так же, как для других клиентов Azure Active Directory. Инструкции см. в статье [Добавление имени личного домена для упрощения входа в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### См. также
[Предварительные сведения для установки Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO2-->


