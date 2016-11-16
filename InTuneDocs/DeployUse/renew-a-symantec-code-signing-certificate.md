---
title: "Обновление сертификата подписи кода Symantec Enterprise, используемого с Intune | Microsoft Intune"
description: "Руководство по обновлению сертификата Symantec, используемого для управления определенными мобильными устройствами с Windows и Windows Phone."
keywords: 
author: staciebarker
manager: stabar
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8fd2a90025ae9310a214978cd2d42ea7ad035fa3
ms.openlocfilehash: 2479f8065a2bb46e63b0e3971700a8d2c0982755


---

# <a name="renew-a-symantec-enterprise-codesigning-certificate-for-windows-devices"></a>Обновление сертификата подписи кода Symantec Enterprise для устройств Windows

Сертификат Symantec, используемый для развертывания мобильных приложений Windows и Windows Phone, должен периодически обновляться.

## <a name="how-to-renew-the-symantec-enterprise-codesigning-certificate"></a>Инструкции по обновлению корпоративного сертификата Symantec для подписи кода

1.  Дождитесь сообщения электронной почты об обновлении, которое отправляет компания Symantec приблизительно за 14 дней до истечения срока действия сертификата. Это сообщение электронной почты содержит указания компании Symantec об обновлении корпоративного сертификата.

    Для получения дополнительных сведений о сертификатах Symantec посетите сайт [www.symantec.com](http://www.symantec.com) или позвоните по телефону +7 (495) 641-22-91 или +44 11 89-22-4660.

2.  Откройте веб-сайт (например, [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) и выполните вход с использованием идентификатора издателя Symantec, а также адреса электронной почты, связанного с сертификатом. Не забудьте использовать тот же компьютер для запуска обновления, который будет использоваться для загрузки сертификата.

3.  После утверждения и оплаты обновления загрузите сертификат.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-80"></a>Установка обновленного сертификата для Windows Phone 8.0

1.  Скачайте и подпишите последнюю версию портала компании Windows Phone по адресу: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Откройте консоль администрирования Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) и перейдите в раздел **Администрирование**, **Управление мобильными устройствами** &gt; **Windows Phone**, а затем нажмите кнопку **Отправить подписанное приложение**.

3.  Отправьте вновь подписанный корпоративный портал. Вам понадобятся вновь подписанный SSP.xap и новый PFX-файл, полученный от Symantec, или маркер регистрации приложения, который был создан с использованием этого нового PFX-файла.

4.  После завершения передачи удалите старую версию корпоративного портала в рабочей области **Программное обеспечение** консоли управления Intune.

5.  Снова подпишите все бизнес-приложения предприятия, используя тот же сертификат, а затем отправьте и замените существующие приложения.

Предоставление подписанного файла SSP.xap в настоящее время является единственным способом предоставления обновленного сертификата подписи кода. Для поддержки подписанных бизнес-приложений необходимо подписать и отправить приложение портала компании, даже несмотря на то, что пользователи будут самостоятельно устанавливать приложение портала компании из магазина.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-81-and-later-devices"></a>Установка обновленного сертификата для Windows Phone 8.1 и более поздних устройств

1.  Скачайте и подпишите последнюю версию портала компании Windows Phone из Центра загрузки по адресу: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Откройте [консоль администрирования Intune](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) и перейдите в раздел **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows Phone**, а затем нажмите кнопку **Отправить подписанное приложение**.

3.  Отправьте вновь подписанный корпоративный портал. Вам понадобятся вновь подписанный SSP.xap и новый PFX-файл, полученный от Symantec, или маркер регистрации приложения, который был создан с использованием этого нового PFX-файла.

4.  После завершения передачи удалите старую версию портала компании в рабочей области **Программное обеспечение**  .

5.  Подпишите все новые и обновленные корпоративные бизнес-приложения с помощью нового сертификата. Существующие приложения не требуется заново подписывать и развертывать.


### <a name="see-also"></a>См. также
[Настройка управления Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Настройка управления Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


