---
# required metadata

title: Настройка имени личного домена | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Настройка имени личного домена

По умолчанию Intune использует имя домена **<domain>.onmicrosoft.com**, созданное при первой подписке на службу. Если организации принадлежит личный домен, можно настроить имеющийся экземпляр Intune для использования этого имени домена вместо имени, предоставленного с подпиской.

Перед созданием учетных записей пользователей или синхронизацией учетных записей из локального каталога Active Directory настоятельно рекомендуется решить, будет ли использоваться только домен .onmicrosoft.com или нужно добавить одно или несколько настраиваемых имен доменов. Настройка домена до добавления пользователей позволяет упростить управление удостоверениями пользователей для подписки, позволив пользователям выполнять вход с учетными данными, которые они используют для доступа к другим ресурсам домена.

При оформлении подписки на облачную службу Майкрософт имеющийся экземпляр службы становится [клиентом Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), который предоставляет службы удостоверений и каталогов для вашей облачной службы. А поскольку задачи по настройке Intune для использования имени личного домена организации не отличаются от выполняемых для клиентов Azure AD, используйте сведения и процедуры из статьи [Добавление домена](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> Дополнительные сведения об использовании личного домена с облачной службой Майкрософт см. в статье [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) (Общие сведения об именах личных доменов в Azure Active Directory).

### Дальнейшие действия
Поздравляем! Вы завершили шаг 2 *краткого руководства по Intune*.

>[!div class="step-by-step"]

>[&larr; **Вход в Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Добавление пользователей в Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  


<!--HONumber=May16_HO2-->


