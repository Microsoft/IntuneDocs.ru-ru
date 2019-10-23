---
title: Настройка регистрации для устройств Windows с помощью Microsoft Intune
titleSuffix: ''
description: Настройка регистрации для устройств Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55147de71d764feb89aa305c7e3282cfb1fff3c1
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503048"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Настройка регистрации для устройств Windows

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Эта статья поможет ИТ-администраторам упростить регистрацию Windows для пользователей организации. После [настройки Intune](../fundamentals/setup-steps.md) пользователи регистрируют устройства Windows, выполняя [вход](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) с использованием рабочей или учебной учетной записи.  

Как администратор Intune вы можете упростить регистрацию одним из следующих способов:

- [включение автоматической регистрации](#enable-windows-10-automatic-enrollment) (требуется Azure AD Premium);
- [регистрация CNAME](#simplify-windows-enrollment-without-azure-ad-premium);
- [включение массовой регистрации](../windows-bulk-enroll.md) (требуется Azure AD Premium и конструктор конфигураций Windows).

Ниже приведены два фактора, которые определяют способ упрощения регистрации устройств Windows.

- **Вы используете Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) входит в состав Enterprise Mobility + Security и других планов лицензирования.
- **Какие версии клиентов Windows будут регистрировать пользователи?** <br>Устройства с Windows 10 можно зарегистрировать автоматически, добавив рабочую или учебную учетную запись. Более ранние версии необходимо регистрировать с помощью приложения корпоративного портала.

||**Azure AD Premium**|**AD других версий**|
|----------|---------------|---------------|  
|**Windows 10**|[Автоматическая регистрация](#enable-windows-10-automatic-enrollment) |Регистрация пользователей|
|**Более ранние версии Windows**|Регистрация пользователей|Регистрация пользователей|

Организации, способные использовать автоматическую регистрацию, могут также настроить и [массовую регистрацию устройств](../windows-bulk-enroll.md) с помощью конструктора конфигураций Windows.

## <a name="device-enrollment-prerequisites"></a>Предварительные условия для регистрации устройств

Прежде чем администратор сможет регистрировать устройства в Intune для управления, лицензии должны уже быть назначены учетной записи администратора. [Узнайте о назначении лицензий для регистрации устройств](../fundamentals/licenses-assign.md)

## <a name="multi-user-support"></a>Поддержка нескольких пользователей

Intune поддерживает несколько пользователей на устройствах, которые:

- запускают обновление Windows 10 Creator;
- присоединены к домену Azure Active Directory.

Когда обычные пользователи входят в систему с помощью учетных данных Azure AD, они получают доступ ко всем приложениям и политикам, назначенным их пользовательским именам. Только [основной пользователь](../remote-actions/find-primary-user.md) устройства может использовать Корпоративный портал для сценариев самообслуживания, таких как установка приложений и выполнение действий устройства ("Удалить", "Сбросить"). Для общих устройств с Windows 10, которым не назначен основной пользователь, Корпоративный портал можно по-прежнему использовать для установки доступных приложений.

[!INCLUDE [AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Упрощение регистрации Windows без Azure AD Premium
Чтобы упростить регистрацию, создайте псевдоним сервера доменных имен (DNS-псевдоним; тип записи CNAME), который перенаправляет запросы на регистрацию на серверы Intune. В противном случае пользователям, пытающимся подключиться к Intune, потребуется ввести имя сервера Intune при регистрации.

**Шаг 1. Создание записи CNAME** (необязательно)<br>
Создайте запись ресурсов CNAME DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

Несмотря на то, что создавать записи CNAME в DNS не обязательно, записи CNAME позволяют упростить регистрацию для пользователей. Если запись CNAME для регистрации не обнаружена, пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

|Type|Имя узла|Указывает на|СРОК ЖИЗНИ|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

Если в организации используется несколько UPN-суффиксов, необходимо создать по одной записи CNAME для каждого доменного имени и указать для них EnterpriseEnrollment-s.manage.microsoft.com. Например, пользователи в компании Contoso используют следующие форматы электронной почты или UPN.

- name@contoso.com
- name@us.contoso.com
- name@eu.contoso.com

Администратору DNS в Contoso следует создать следующие записи CNAME.

|Type|Имя узла|Указывает на|СРОК ЖИЗНИ|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 час|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 час|

`EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

## <a name="additional-endpoints-are-supported-but-not-recommended"></a>Дополнительные конечные точки поддерживаются, но использовать их не рекомендуется
EnterpriseEnrollment-s.manage.microsoft.com — предпочтительное полное доменное имя для регистрации, но есть еще две конечные точки, которые использовались клиентами в прошлом и по-прежнему поддерживаются. Как EnterpriseEnrollment.manage.microsoft.com (без "-s"), так и manage.microsoft.com могут быть назначениями для сервера автоматического обнаружения, однако пользователю необходимо нажать кнопку "ОК" в подтверждении. Если вы используете конечную точку EnterpriseEnrollment-s.manage.microsoft.com, пользователю не нужно подтверждать действие, поэтому это рекомендуемый вариант.

## <a name="alternate-methods-of-redirection-are-not-supported"></a>Другие методы перенаправления не поддерживаются
Никакие другие методы, кроме настройки CNAME, не поддерживаются. Например, не поддерживается использование прокси-сервера для перенаправления с enterpriseenrollment.contoso.com/EnrollmentServer/Discovery.svc на enterpriseenrollment-s.manage.microsoft.com/EnrollmentServer/Discovery.svc или manage.microsoft.com/EnrollmentServer/Discovery.svc.

**Шаг 2. Проверка записи CNAME** (необязательно)<br>
1. В [Intune на портале Azure](https://aka.ms/intuneportal) последовательно выберите **Регистрация устройства**  >  **Регистрация Windows**  >  **Проверка CNAME**.
2. В поле **Домен** укажите веб-сайт организации и нажмите кнопку **Проверка**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Передайте пользователям инструкции по регистрации устройств Windows
Сообщите пользователям, как зарегистрировать устройства Windows и что произойдет при управлении ими.

> [!NOTE]
> Чтобы просмотреть приложения Windows, назначенные для конкретных версий Windows, конечные пользователи должны зайти на веб-сайт корпоративного портала с помощью Microsoft Edge. Другие браузеры, включая Google Chrome, Mozilla Firefox и Internet Explorer, не поддерживают этот тип фильтрации.

Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Вы также можете посоветовать пользователям изучить статью [Какие сведения ИТ-администратор может просматривать на моем устройстве?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Если автоматическая регистрация в системе MDM не включена, но у вас есть устройства с Windows 10, присоединенные к Azure Active Directory, после регистрации в консоли Intune будут отображаться две записи. Чтобы этого не происходило, пользователи устройств, присоединенных к Azure Active Directory, должны выбрать элемент **Учетные записи** > **Доступ к рабочей или учебной среде** и **подключиться**, используя ту же учетную запись. 

Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](../fundamentals/end-user-educate.md).

## <a name="next-steps"></a>Дальнейшие шаги

- [Рекомендации по управлению устройствами Windows с помощью Intune в Azure](../fundamentals/intune-legacy-pc-client.md).
