---
title: "Настройка управления устройствами Windows 10 Mobile и Windows Phone с помощью Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c5d1b53f09ce2f475cd934e36ddb19d019737431
ms.openlocfilehash: e67a5be851b68d87a4cdda871824cf0ecb14579e


---


# Настройка управления устройствами Windows 10 Mobile и Windows Phone с помощью Microsoft Intune
Чтобы устройствами Windows 10 Mobile или Windows Phone можно было управлять в Microsoft Intune, они должны иметь возможность взаимодействовать с Intune. Для упрощения этого процесса можно создать запись DNS, чтобы пользователям не приходилось вводить адрес сервера. Приведенные ниже действия позволяют упростить регистрацию для пользователей.  

Для большинства сценариев пользователи могут установить приложение корпоративного портала из магазина Windows. Если вы управляете устройствами Windows Phone 8.0 или хотите развернуть корпоративный портал на устройства Windows Phone, необходимо скачать и подписать приложение корпоративного портала. См. статью [Настройка управления Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Настройка Intune** Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [задав в качестве центра управления мобильными устройствами](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) службу **Microsoft Intune** и настроив MDM.

2.  **Задать DNS-псевдоним для адреса сервера регистрации** (необязательно)

    Создание DNS-псевдонима (тип записи CNAME) упрощает регистрацию устройств для пользователей. Если вы не создаете DNS-псевдоним, пользователи должны сделать следующее.

  1.  Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, которая выполняет перенаправление с EnterpriseEnrollment.contoso.com на manage.microsoft.com. Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

      |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

      Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

      **EnterpriseEnrollment-s.manage.microsoft.com** — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

      **EnterpriseRegistration.windows.net** — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будет зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

    2.  В [консоли администрирования Intune](http://manage.microsoft.com) щелкните **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows Phone**.

      ![Диалоговое окно "Настройка управления мобильными устройствами для Windows"](../media/windows-device-enrollment.png)

    3.  Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.



Дополнительные действия требуются только в случае развертывания корпоративного портала на устройствах.  Шаги 2 и 3 в консоли администрирования можно спокойно пропустить.



<!--HONumber=Jun16_HO4-->


