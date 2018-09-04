---
title: На устройстве отсутствует сертификат | Документация Майкрософт
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d51b141b09090119f7c9711ffd56d6b382f6e3dc
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43147957"
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>На устройстве Android отсутствует сертификат (обычно он предустановлен на телефоне)

Если устройство не зарегистрировано в Intune и на нем отсутствует предустановленный сертификат, вы не сможете войти в приложение корпоративного портала. При попытке выполнить вход вы увидите следующее сообщение:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Чтобы решить эту проблему, можно скачать требуемый сертификат на [странице сертификатов Digicert](https://www.digicert.com/digicert-root-certificates.htm).

1. Найдите и скачайте сертификат __Baltimore CyberTrust Root__. Его также можно скачать [отсюда](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

2. С помощью перетаскивания сверху вниз отобразите список последних уведомлений, а затем выберите файл **BaltimoreCyberTrustRoot.crt**.

3. Устройство предложит **присвоить сертификату имя**. Не изменяйте отображаемое имя сертификата по умолчанию.

4. Убедитесь, что для параметра **Credential Use** (Использование учетных данных) задано значение **Used for VPN and apps** (Использовать для VPN и приложений), и нажмите кнопку **ОК**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Закройте браузер и приложение корпоративного портала.

6. Снова откройте приложение корпоративного портала. Теперь вы сможете войти в приложение корпоративного портала. Если приложение "Корпоративный портал" по-прежнему недоступно, обратитесь за дальнейшими инструкциями в службу поддержки вашей компании с помощью сведений, указанных на [веб-сайте корпоративного портала](https://go.microsoft.com/fwlink/?linkid=2010980).

>[!NOTE]
> Если установка сертификата не решает проблему (более того, отображается еще одно сообщение об отсутствующем сертификате), выполните дополнительные действия по [установке отсутствующего сертификата](your-device-is-missing-an-IT-required-certificate-android.md).

По-прежнему нужна помощь? Обратитесь в службу поддержки вашей компании. Его контактные данные доступны на [веб-сайте корпоративного портала](https://go.microsoft.com/fwlink/?linkid=2010980).
