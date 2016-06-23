---
# required metadata

title: Устройство не имеет необходимого сертификата | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Устройство не имеет необходимого сертификата
Если устройство Android не зарегистрировано в Intune и на нем отсутствует сертификат, который обычно уже установлен на телефоне, вы не сможете войти в приложение корпоративного портала Android. При попытке выполнить вход вы увидите следующее сообщение:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

Чтобы устранить эту проблему и получить требуемый сертификат, выполните следующие действия:

1.  В браузере перейдите на [страницу сертификата Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Найдите и скачайте сертификат Baltimore CyberTrust Root (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Перетащите верхнюю панель вниз, чтобы открыть уведомления, и выберите **BaltimoreCyberTrustRoot.crt** в списке уведомлений.

4.  На экране **Имя сертификата** примите имя сертификата по умолчанию.

5. Убедитесь, что для параметра **Credential Use** (Использование учетных данных) задано значение **Used for VPN and apps** (Использовать для VPN и приложений), и нажмите кнопку **ОК**.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Закройте веб-браузер и приложение корпоративного портала.

7. Снова откройте приложение корпоративного портала. Теперь вы сможете войти в приложение корпоративного портала. Если вам нужна помощь, обратитесь к системному администратору.

По-прежнему нужна помощь? Обратитесь к ИТ-администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).

<!--HONumber=Jun16_HO2-->


