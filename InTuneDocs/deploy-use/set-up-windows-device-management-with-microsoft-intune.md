---
title: "Настройка управления устройствами Windows с помощью Microsoft Intune | Документация Майкрософт"
description: "Включение управления мобильными устройствами (MDM) для устройств Windows с помощью Microsoft Intune"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: f1291d6eec32ad834d33fcbfff320ce173521a25
ms.lasthandoff: 04/24/2017


---

# <a name="set-up-windows-device-management"></a>Настройка управления устройствами Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Этот раздел поможет ИТ-администраторам упростить регистрацию Windows для пользователей организации.  Устройства Windows можно регистрировать без выполнения дополнительных действий, но вы можете упростить регистрацию для пользователей.

Ниже приведены два фактора, которые определяют способ упрощения регистрации устройств Windows.
- **Вы используете Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) входит в состав Enterprise Mobility + Security и других планов лицензирования.
- **Какие версии клиентов Windows будут регистрироваться?** <br>Устройства с Windows 10 можно зарегистрировать автоматически, добавив рабочую или учебную учетную запись. Более ранние версии необходимо регистрировать с помощью приложения корпоративного портала.

||**Azure AD Premium**|**AD других версий**|
|----------|---------------|---------------|  
|**Windows 10**|[Автоматическая регистрация](#enable-windows-10-automatic-enrollment) |[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|
|**Более ранние версии Windows**|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|[Регистрация пользователей](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Включение регистрации Windows без автоматической регистрации
Вы можете разрешить пользователям регистрировать свои устройства без автоматической регистрации в Azure AD Premium. После того как вы назначили пользователям лицензии, они могут регистрироваться после добавления их рабочей учетной записи на личные устройства или после присоединения их корпоративных устройств к Azure AD. Создание DNS-псевдонима (тип записи CNAME) упрощает регистрацию устройств для пользователей. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера Intune.

**Шаг 1. Создание записи CNAME** (необязательно)<br>
Создайте запись ресурсов CNAME DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии регистрационной записи CNAME пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

Записи ресурсов CNAME должны содержать следующие сведения:

|ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

`EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

**Шаг 2. Проверка записи CNAME** (необязательно)<br>
В [консоли администратора Intune](https://manage.microsoft.com) последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Передайте пользователям инструкции по регистрации устройств Windows
Сообщите пользователям, как зарегистрировать устройства Windows и что произойдет при управлении ими.
Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Вы также можете перенаправить пользователей к статье [Какие сведения становятся доступными моей организации при регистрации устройства в Intune?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)

