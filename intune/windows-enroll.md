---
title: "Регистрация устройств Windows"
titleSuffix: Intune on Azure
description: "Включение управления мобильными устройствами Intune (MDM) для устройств Windows.\""
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 08/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b5b5e2cdf2b31c33a02a90560e4abf955d398b0
ms.sourcegitcommit: d5b5cb9b6dcb59094e436e07f8ed46924b37ac94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2017
---
# <a name="enroll-windows-devices"></a>Регистрация устройств Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Этот раздел поможет ИТ-администраторам упростить регистрацию Windows для пользователей организации. После [настройки Intune](setup-steps.md) пользователи регистрируют устройства Windows, выполняя [вход](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) с использованием рабочей или учебной учетной записи.  

Как администратор Intune вы можете упростить регистрацию одним из следующих способов:
- включение автоматической регистрации (требуется Azure AD Premium);
- регистрация CNAME;
- включение массовой регистрации (требуется Azure AD Premium и конструктор конфигураций Windows).

Ниже приведены два фактора, которые определяют способ упрощения регистрации устройств Windows.

- **Вы используете Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) входит в состав Enterprise Mobility + Security и других планов лицензирования.
- **Какие версии клиентов Windows будут регистрировать пользователи?** <br>Устройства с Windows 10 можно зарегистрировать автоматически, добавив рабочую или учебную учетную запись. Более ранние версии необходимо регистрировать с помощью приложения корпоративного портала.

||**Azure AD Premium**|**AD других версий**|
|----------|---------------|---------------|  
|**Windows 10**|[Автоматическая регистрация](#enable-windows-10-automatic-enrollment) |[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|
|**Более ранние версии Windows**|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|

Организации, способные использовать автоматическую регистрацию, могут также настроить и [массовую регистрацию устройств](windows-bulk-enroll.md) с помощью конструктора конфигураций Windows.

**Поддержка нескольких пользователей**<br>
Мы добавили поддержку управления несколькими пользователями с помощью Intune для устройств под управлением Windows 10 Creators Update, присоединенных к домену Azure Active Directory. Когда обычные пользователи входят в систему с помощью учетных данных Azure AD, они получают доступ ко всем приложениям и политикам, назначенным их пользовательским именам. Сейчас пользователи не могут использовать корпоративный портал для таких сценариев самообслуживания, как установка приложений.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Включение регистрации Windows без Azure AD Premium
Вы можете упростить регистрацию, создав DNS-псевдоним (тип записи CNAME), который автоматически перенаправляет запросы регистрации на серверы Intune. Если не создать запись ресурса CNAME DNS, пользователям, пытающимся подключиться к Intune, потребуется ввести имя сервера Intune при регистрации.

**Шаг 1. Создание записи CNAME** (необязательно)<br>
Создайте запись ресурсов CNAME DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

Несмотря на то, что создавать записи CNAME в DNS не обязательно, записи CNAME позволяют упростить регистрацию для пользователей. Если запись CNAME для регистрации не обнаружена, пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

|Тип|Имя узла|Указывает на|СРОК ЖИЗНИ|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

При наличии нескольких UPN-суффиксов необходимо создать по одной записи CNAME для каждого имени домена и указать для них EnterpriseEnrollment-s.manage.microsoft.com. Если в качестве электронной почты или UPN пользователи используют name@contoso.com, а также name@us.contoso.com и name@eu.constoso.com, администратору Contoso DNS нужно создать следующие записи CNAME.

|Type|Имя узла|Указывает на|СРОК ЖИЗНИ|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|

`EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

**Шаг 2. Проверка записи CNAME** (необязательно)<br>
На портале Azure Intune выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**. В колонке Intune выберите пункты **Регистрация устройств** > **Регистрация Windows**. Введите URL-адрес веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Передайте пользователям инструкции по регистрации устройств Windows
Сообщите пользователям, как зарегистрировать устройства Windows и что произойдет при управлении ими. Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Вы также можете посоветовать пользователям изучить статью [Какие сведения ИТ-администратор может просматривать на моем устройстве?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](end-user-educate.md).
