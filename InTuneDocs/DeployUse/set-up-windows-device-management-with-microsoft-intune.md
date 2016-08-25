---
title: "Настройка управления устройствами Windows с помощью Microsoft Intune | Microsoft Intune"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для компьютеров с Windows, включая устройства с Windows 10."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: fae2aa496ec38d9ddc2cb6800bed10ccb32fd154


---

# Настройка управления устройствами Windows
Справку по настройке устройства с Windows см. [здесь](../enduser/using-your-windows-device-with-intune.md).

Благодаря Intune вы можете включить регистрацию устройства Windows BYOD ("принеси свое устройство"), чтобы предоставить доступ к корпоративной электронной почте и приложениям. Вместе с Azure Active Directory это также позволяет быстро реализовать управление новыми устройствами Windows 10 и получить доступ к корпоративным ресурсам без необходимости переустанавливать ОС на компьютере. После регистрации пользователи могут входить в систему, а к их устройствам могут применяться политики, приложения и параметры с помощью консоли администрирования Intune. Вы также можете [настроить управление Windows Phone с помощью Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) или [управлять компьютерами с помощью клиентского программного обеспечения Intune](manage-windows-pcs-with-microsoft-intune.md), используя клиент Intune.

Создание DNS CNAME помогает пользователям подключиться к Intune и выполнять регистрацию без ввода имени сервера.

### Настройка управления устройствами Windows

  1.  Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Несмотря на то, что запись CNAME DNS является необязательной для регистрации устройства с Windows, рекомендуется при необходимости создать одну или несколько записей, чтобы упростить процесс регистрации устройств с Windows. При отсутствии записей CNAME пользователю предлагается ввести имя сервера MDM вручную.

  Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

  **EnterpriseEnrollment-s.manage.microsoft.com** — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  **EnterpriseRegistration.windows.net** — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будет зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  2.  В [консоли администрирования Intune](http://manage.microsoft.com) выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows**.
  ![Диалоговое окно "Управление устройствами Windows"](../media/enroll-intune-winenr.png)

  3.  Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

  4.  Вашим пользователям потребуется узнать, как зарегистрировать устройства и чего ожидать после того, как они начнут управлять ими.
      - [Что нужно сообщить конечным пользователям об использовании Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Руководство конечного пользователя для устройств с Windows](../enduser/using-your-windows-device-with-intune.md)

### См. также
[Подготовка к регистрации устройств в Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


