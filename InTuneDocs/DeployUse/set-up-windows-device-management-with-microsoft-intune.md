---
title: "Настройка управления устройствами Windows с помощью Microsoft Intune | Microsoft Intune"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для компьютеров с Windows, включая устройства с Windows 10."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 149508942b89b15308591e17723884add3ac78ae


---

# Настройка управления устройствами Windows

Как администратор Intune, вы можете включить регистрацию и управление для компьютеров с Windows двумя способами:

- **[Автоматическая регистрация с помощью Azure AD](#azure-active-directory-enrollment)** — пользователи Windows 10 и Windows 10 Mobile регистрируют свои устройства, добавляя на них рабочую или учебную учетную запись.
- **[Регистрация на корпоративном портале](#company-portal-app-enrollment)** — устройства с Windows 8.1 и более поздних версий регистрируются посредством скачивания и установки приложения корпоративного портала с последующим вводом в нем данных рабочей или учебной учетной записи.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Настройка регистрации в приложении корпоративного портала
Вы можете разрешить пользователям регистрировать свои устройства посредством установки приложения корпоративного портала Intune. Создание DNS CNAME помогает пользователям подключиться к Intune и выполнять регистрацию без ввода имени сервера.

1. **Настройка Intune**<br>
Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами](prerequisites-for-enrollment.md#set-mobile-device-management-authority) службу **Microsoft Intune** и настроив MDM.

2. **Создание записей CNAME** (необязательно)<br>Создайте запись ресурсов **CNAME** DNS для домена вашей организации, чтобы упростить регистрацию. Хотя создание записей CNAME DNS и не является обязательным, оно упрощает процедуру регистрации для пользователей. При отсутствии записи CNAME для регистрации пользователям предлагается вручную ввести имя сервера MDM `https://manage.microsoft.com`.  Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  `EnterpriseRegistration.windows.net` — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будут зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

3.  **Проверка CNAME**<br>В [консоли администрирования Intune](http://manage.microsoft.com) выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

  ![Диалоговое окно "Управление устройствами Windows"](../media/enroll-intune-winenr.png)

4.  **Дополнительные шаги**<br>Для Windows 10 шаг **Добавление ключей для загрузки неопубликованных приложений** не требуется. Шаг **Отправка сертификата подписи кода** необходим только в том случае, если планируется распространять на устройства бизнес-приложения, недоступные в Магазине Windows. [Дополнительные сведения](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Оповещение пользователей**<br>Вам следует сообщить пользователям, как зарегистрировать устройства и чего ожидать после начала управления ими:
      - [Что нужно сообщить конечным пользователям об использовании Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Руководство конечного пользователя для устройств с Windows](../enduser/using-your-windows-device-with-intune.md)

### См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Sep16_HO4-->


