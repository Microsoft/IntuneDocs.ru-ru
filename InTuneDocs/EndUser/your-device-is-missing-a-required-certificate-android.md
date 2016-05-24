---
# required metadata

title: Устройство не имеет необходимого сертификата | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
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

5. Убедитесь, что для параметра **Использование учетных данных** задано значение **Использовать для VPN и приложений**, и нажмите кнопку **ОК**.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Закройте веб-браузер и приложение корпоративного портала.

7. Снова откройте приложение корпоративного портала. Теперь вы сможете войти в приложение корпоративного портала. Если вам нужна помощь, обратитесь к системному администратору.

<!--HONumber=May16_HO2-->


