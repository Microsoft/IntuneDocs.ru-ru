---
title: "Настройка управления устройствами Windows с помощью Microsoft Intune | Документы Майкрософт"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для компьютеров с Windows, включая устройства с Windows 10."
keywords: 
author: staciebarker
manager: stabar
ms.date: 01/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 526830839aa801a7ac78aeb4baaa790d6bb5da5c
ms.openlocfilehash: f4f3b89cf066bcc98d043f66d4d40fd9d9ca3fd5


---

# <a name="set-up-windows-device-management"></a>Настройка управления устройствами Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Как администратор Intune вы можете включить регистрацию и управление для компьютеров с Windows двумя способами.

- **[Автоматическая регистрация с помощью Azure Active Directory](#azure-active-directory-enrollment)** — пользователи Windows 10 и Windows 10 Mobile регистрируют свои устройства, добавляя на них рабочую или учебную учетную запись.

- **[Регистрация на корпоративном портале](#set-up-company-portal-app-enrollment)** — пользователи устройств с Windows 8.1 и более поздних версий регистрируют их посредством загрузки и установки приложения корпоративного портала с последующим вводом в нем данных рабочей или учебной учетной записи.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Настройка регистрации в приложении корпоративного портала
Вы можете разрешить пользователям устанавливать приложение корпоративного портала Intune и регистрировать свои устройства с его помощью. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера.

1. **Настройка Intune**<br>
Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) службу **Microsoft Intune** и затем настроив MDM.

2. **Создание записей CNAME** (необязательно)<br>Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

    Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии записи CNAME для регистрации пользователям предлагается вручную ввести имя сервера MDM — это https://enrollment.manage.microsoft.com. 

    Если у вас уже есть запись CNAME в службе DNS, которая перенаправляет EnterpriseEnrollment.contoso.com на manage.microsoft.com, предполагается, следует заменить ее записью CNAME в службе DNS, которая перенаправляет EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com. Это рекомендуемое изменение, так как конечная точка manage.microsoft.com в будущем выпуске не будет использоваться для регистрации.

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


### <a name="see-also"></a>См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO4-->


