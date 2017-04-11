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
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: f66bc5a26f137f62defef4a83a36b22247be4ec1
ms.lasthandoff: 03/22/2017


---

# <a name="set-up-windows-device-management"></a>Настройка управления устройствами Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Чтобы настроить регистрацию устройств Windows, воспользуйтесь одним из описанных ниже методов.

- [**Автоматическая регистрация Windows 10 и Windows 10 Mobile с помощью Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium).
 -  Этот метод подходит только для устройств Windows 10 и Windows 10 Mobile.
 -  Для использования этого метода необходима служба Azure Active Directory Premium. Если у вас ее нет, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.
 -  Если вы решили не включать автоматическую регистрацию, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.


- [**Регистрация Windows 8.1 и Windows Phone 8.1 путем настройки CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname).
 - Этот метод следует использовать для регистрации устройств Windows 8.1 и Windows Phone 8.1.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Настройка регистрации Windows 8.1 и Windows Phone 8.1 путем настройки CNAME
Вы можете разрешить пользователям устанавливать и регистрировать свои устройства с помощью корпоративного портала Intune. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера.

### <a name="step-1-set-up-intune"></a>Шаг 1. Настройте Intune.

Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) службу **Microsoft Intune** и затем настроив MDM.

### <a name="step-2-create-cnames-optional"></a>Шаг 2. Создайте записи CNAME (необязательно).

Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.


   Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии регистрационной записи CNAME пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

   Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  `EnterpriseRegistration.windows.net` — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будут зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

### <a name="step-3-verify-cname"></a>Шаг 3. Проверьте CNAME.

В [консоли администратора Intune](http://manage.microsoft.com) последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>Шаг 4. Сообщите пользователям, как зарегистрировать устройства и что произойдет при управлении ими.

   Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows).

   Дополнительные сведения о задачах конечных пользователей см. в разделах [Инструкции по использованию Microsoft Intune для конечных пользователей](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) и [Руководство конечного пользователя для устройств с Windows](https://docs.microsoft.com/intune-user-help/using-your-windows-device-with-intune).

### <a name="see-also"></a>См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)

