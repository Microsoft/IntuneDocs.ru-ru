---
title: "Настройка управления устройствами Windows с помощью Microsoft Intune | Документация Майкрософт"
description: "Включение управления мобильными устройствами (MDM) для устройств Windows с помощью Microsoft Intune"
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6b99854e17e00a0dd0f91fa82fd1b79d1dfe5663
ms.openlocfilehash: 6277f82483eb8fb7f5a4e4a832a909490ba0050c
ms.lasthandoff: 02/18/2017


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

1. **Настройка Intune**<br>
Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) службу **Microsoft Intune** и затем настроив MDM.

2. **Создание записей CNAME** (необязательно)<br>
Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.


    Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии записи CNAME для регистрации пользователям предлагается вручную ввести имя сервера MDM — это https://enrollment.manage.microsoft.com.


    Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  `EnterpriseRegistration.windows.net` — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будут зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

3.  **Проверка CNAME**<br>В [консоли администратора Intune](http://manage.microsoft.com) последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

4.  **Сообщите пользователям, как зарегистрировать устройства и что произойдет при управлении ими.**

    Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Дополнительные сведения о задачах пользователей см. в разделе       - [Ресурсы по пользовательскому интерфейсу Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
      - [Руководство конечного пользователя по устройствам Windows](../enduser/using-your-windows-device-with-intune.md).

### <a name="see-also"></a>См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)

