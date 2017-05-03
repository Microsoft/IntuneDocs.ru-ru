---
title: "Регистрация устройств Windows"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: включение управления мобильными устройствами Intune (MDM) для устройств Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 3c764b269916ae1a9b076617842eb26d7fd13bab
ms.lasthandoff: 04/19/2017


---

# <a name="enroll-windows-devices"></a>Регистрация устройств Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Этот раздел поможет ИТ-администраторам упростить регистрацию Windows для пользователей организации.  Устройства Windows можно регистрировать без выполнения дополнительных действий, но вы можете упростить регистрацию для пользователей.

Мы добавили поддержку управления несколькими пользователями с помощью Intune для устройств под управлением Windows 10 Creators Update, присоединенных к домену Azure Active Directory. Это означает, что все обычные пользователи, входящие на устройство с помощью учетных данных Azure AD, получат доступ ко всем приложениям и политикам, которые назначены их пользовательским именам. Сейчас пользователи не могут использовать корпоративный портал для таких сценариев самообслуживания, как установка приложений.

Ниже приведены два фактора, которые определяют способ упрощения регистрации устройств Windows.

- **Вы используете Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) входит в состав Enterprise Mobility + Security и других планов лицензирования.
- **Какие версии клиентов Windows будут регистрироваться?** <br>Устройства с Windows 10 можно зарегистрировать автоматически, добавив рабочую или учебную учетную запись. Более ранние версии необходимо регистрировать с помощью приложения корпоративного портала.

||**Azure AD Premium**|**AD других версий**|
|----------|---------------|---------------|  
|**Windows 10**|[Автоматическая регистрация](#enable-windows-10-automatic-enrollment) |[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|
|**Более ранние версии Windows**|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Включение регистрации Windows без Azure AD Premium
Вы можете разрешить пользователям регистрировать свои устройства без автоматической регистрации в Azure AD Premium. После того как вы назначили пользователям лицензии, они могут регистрироваться после добавления их рабочей учетной записи на личные устройства или после присоединения их корпоративных устройств к Azure AD. Создание DNS-псевдонима (тип записи CNAME) упрощает регистрацию устройств для пользователей. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера Intune.

**Шаг 1. Создание записи CNAME** (необязательно)<br>
Создайте запись ресурсов CNAME DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. Если запись CNAME для регистрации не обнаружена, пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

|Тип|Имя узла|Указывает на|СРОК ЖИЗНИ|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|

При наличии нескольких UPN-суффиксов необходимо создать по одной записи CNAME для каждого имени домена и указать для них EnterpriseEnrollment-s.manage.microsoft.com. Например, если в качестве электронной почты или UPN пользователи используют name@contoso.com, а также name@us.contoso.com и name@eu.constoso.com, администратору Contoso DNS необходимо создать следующие записи CNAME.

|Тип|Имя узла|Указывает на|СРОК ЖИЗНИ|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|

`EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

**Шаг 2. Проверка записи CNAME** (необязательно)<br>
На портале Azure Intune выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**. В колонке Intune выберите пункты **Регистрация устройств** > **Регистрация Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Передайте пользователям инструкции по регистрации устройств Windows
Сообщите пользователям, как зарегистрировать устройства Windows и что произойдет при управлении ими. Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Вы также можете перенаправить пользователей к статье [Какие сведения становятся доступными моей организации при регистрации устройства в Intune?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

