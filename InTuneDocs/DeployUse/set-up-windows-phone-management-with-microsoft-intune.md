---
title: "Настройка управления устройствами Windows 10 Mobile и Windows Phone | Microsoft Intune"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для компьютеров с Windows 10 Mobile или Windows Phone."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: a077d5a6cd111d84cb98bfcb5e05cab0c0c4d49c


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Настройка управления устройствами Windows 10 Mobile и Windows Phone с помощью Microsoft Intune

Как администратор Intune вы можете включить регистрацию и управление для устройств Windows 10 Mobile и Windows Phone двумя способами.

- **[Автоматическая регистрация с помощью Azure Active Directory](#azure-active-directory-enrollment)** — пользователи Windows 10 и Windows 10 Mobile регистрируют свои устройства, добавляя на них рабочую или учебную учетную запись.
- **[Регистрация на корпоративном портале](#company-portal-app-enrollment)** — пользователи устройств с Windows Phone 8.1 и более поздних версий регистрируют их посредством загрузки и установки приложения корпоративного портала с последующим вводом в нем данных рабочей или учебной учетной записи.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Регистрация в приложении корпоративного портала
Вы можете разрешить пользователям устанавливать приложение корпоративного портала Intune и регистрировать свои устройства с его помощью. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера.

1.  **Настройка Intune**<br>Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) службу **Microsoft Intune** и затем настроив MDM.

2.  **Создание записей CNAME** (необязательно)<br>Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, которая выполняет перенаправление с EnterpriseEnrollment.contoso.com на manage.microsoft.com. Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  `EnterpriseRegistration.windows.net` — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будут зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

3.  **Проверка CNAME**<br>В [консоли администрирования Intune](http://manage.microsoft.com) щелкните **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows Phone**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

    ![Диалоговое окно "Настройка управления мобильными устройствами для Windows"](../media/windows-phone-enrollment.png)

4.  **Дополнительные шаги**<br>Для Windows 10 шаг **Добавление ключей для загрузки неопубликованных приложений** не требуется. Шаг **Отправка сертификата подписи кода** необходим только в том случае, если планируется распространять на устройства бизнес-приложения, недоступные в Магазине Windows.

5.  **Оповещение пользователей**<br>Вашим пользователям потребуется узнать, как зарегистрировать устройства и чего ожидать после того, как они начнут управлять ими.
    - [Что нужно сообщить конечным пользователям об использовании Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Руководство конечного пользователя для устройств с Windows](../enduser/using-your-windows-device-with-intune.md)

Дополнительные действия требуются только в случае развертывания корпоративного портала на устройствах.  Шаги 2 и 3 в консоли администрирования можно спокойно пропустить.



<!--HONumber=Nov16_HO1-->


