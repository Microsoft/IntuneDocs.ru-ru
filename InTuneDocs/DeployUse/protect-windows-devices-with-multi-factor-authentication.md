---
title: "Многофакторная проверка подлинности для Windows | Microsoft Intune"
description: "Сведения об интеграции многофакторной проверки подлинности (MFA) в Intune для защиты корпоративных ресурсов."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4993982adcfbc960ad71022268cc44d216d1c585
ms.openlocfilehash: fb4ae43ffcbec24147e2e3ce3c96ec795289c925


---

# Protect Windows devices with multi-factor authentication
Microsoft Intune интегрирует многофакторную проверку подлинности (MFA) для защиты корпоративных ресурсов. Многофакторная проверка подлинности требует использования факторов, таких как текстовая проверка подлинности, дополняющих имена пользователей и пароли. Intune поддерживает использование многофакторной проверки подлинности во время регистрации устройств Windows 8.1 или более поздней версии, Windows Phone 8.1 или Windows 10 Desktop и Mobile.

## Требования к локальной инфраструктуре для ADFS MFA
Чтобы настроить MFA, необходимо следующее:

-   **Домен Active Directory, к которому присоединяется сервер ADFS.**

-   **Сервер служб федерации Active Directory (ADFS), настроенный для MFA.** Сервер под управлением Windows Server 2012 R2, настроенный как сервер AD FS. Дополнительные сведения см. в статье [Защита облачных и локальных ресурсов с помощью сервера Azure Multi-Factor Authentication с Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/).

Все указанные выше серверы должны соответствовать требованиям к системе, приведенным в статье [Требования к системе и информация об установке для Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

#### MFA с Intune
Если в вашей организации используется локальная ИТ-инфраструктура, включающая домен Active Directory со службами федерации Active Directory (AD FS), на сервере федерации можно настроить MFA, а затем включить ее для среды Intune. Настроив многофакторную проверку подлинности в Intune, вы позволяете пользователям пройти проверку подлинности один раз — во время регистрации, а затем получать доступ к корпоративным ресурсам без повторения процедуры многофакторной проверки подлинности.

>[!NOTE]
>На сервере ADFS может требоваться многофакторная проверка подлинности на основе пользователей или на основе групп.  

#### Многофакторная проверка подлинности без Intune
Если вы настраиваете MFA на сервере федерации, но не включаете ее для регистрации в Intune, пользователи должны будут использовать MFA каждый раз при доступе к корпоративным ресурсам (а не только при регистрации устройства).

Можно также настроить MFA в Azure Active Directory (Azure AD) так, чтобы требовать прохождения MFA для каждого отдельного пользователя при каждом доступе к корпоративным ресурсам. Azure Active Directory MFA — это облачная служба, которая не требует какой-либо локальной ИТ-инфраструктуры. Сведения о настройке многофакторной проверки подлинности в Azure AD см. в статье [Приступая к работе с Azure Multi-Factor Authentication в облаке](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Запрос MFA ADFS во время регистрации устройств Windows
Сведения о включении MFA в ADFS см. в разделе [Управление рисками с помощью дополнительной Multi-Factor Authentication для приложений, содержащих конфиденциальные данные](http://technet.microsoft.com/library/dn280949.aspx).

## Настройка MFA регистрации устройств в Intune
>[!Important]  
>Включите MFA в клиенте Azure AD или в локальной среде, прежде чем запрашивать MFA для регистрации устройств Windows в Intune. Если этого не сделать, пользователи будут получать сообщение об ошибке при попытке зарегистрировать свои устройства Windows или подключить их к Azure AD, если настроена автоматическая регистрация во время подключения к Azure AD.

1.  В консоли администрирования Intune последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Multi-Factor Authentication**.

2.  Щелкните **Настройка Multi-Factor Authentication** и выберите **Включение Multi-Factor Authentication**.



<!--HONumber=Aug16_HO3-->


