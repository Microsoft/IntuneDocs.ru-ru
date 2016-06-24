---
# required metadata

title: Возникновение ошибок при попытке регистрации устройства iOS в Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Возникновение ошибок при попытке регистрации устройства iOS в Intune

В следующей таблице приведены ошибки, с которыми вы можете столкнуться при регистрации устройств iOS в Intune. Отправьте эту ссылку своему ИТ-администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).

|Сообщение об ошибке|Проблема|Что нужно сообщить ИТ-администратору|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|Вы уже зарегистрировали слишком много мобильных устройств.|Пользователь должен удалить одно из уже зарегистрированных мобильных устройств с корпоративного портала перед регистрацией следующего. Обратитесь к инструкциям в зависимости от типа используемого устройства: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios), [Windows](unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Возникла проблема с сертификатом, который позволяет мобильному устройству взаимодействовать с корпоративной сетью.<br /><br />Обратитесь к ИТ-администраторам, укажите, что получили сообщение **APNSCertificateNotValid** при попытке зарегистрировать мобильное устройство, и подскажите искать решение в этой таблице.|Apple Push Notification Service (APNS) предоставляет возможность доступа к зарегистрированным устройствам под управлением iOS. Если действия по получению сертификата APNS выполнены не были или истек срок его действия, попытки регистрации завершатся выводом этого сообщения об ошибке.<br /><br />Просмотрите сведения о настройке пользователей в статьях [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) (Синхронизация Active Directory и добавление пользователей в Intune) и [Organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) (Организация пользователей и устройств).|
|AccountNotOnboarded|Возникла проблема с сертификатом, который позволяет мобильному устройству взаимодействовать с корпоративной сетью.<br /><br />Обратитесь к ИТ-администраторам, укажите, что получили сообщение **APNSNotOnboarded** при попытке зарегистрировать мобильное устройство, и подскажите искать решение в этой таблице.|Apple Push Notification Service (APNS) предоставляет возможность доступа к зарегистрированным устройствам под управлением iOS. Если действия по получению сертификата APNS выполнены не были или истек срок его действия, попытки регистрации завершатся выводом этого сообщения об ошибке.<br /><br />Дополнительные сведения см. в статье [Set up iOS and Mac management with Microsoft Intune](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune) (Настройка управления устройствами c iOS и Mac с помощью Microsoft Intune).|
|DeviceTypeNotSupported|Возможно, вы попытались зарегистрировать устройство без iOS. Тип регистрируемого мобильного устройства не поддерживается.<br /><br />Убедитесь, что устройство работает под управлением iOS версии 7.1 или более поздней.<br /><br />Обратитесь к ИТ-администраторам, укажите, что получили сообщение **DeviceTypeNotSupported** при попытке зарегистрировать мобильное устройство, и подскажите искать решение в этой таблице.|Убедитесь, что устройство пользователя работает под управлением iOS версии 7.1 или более поздней.|
|UserLicenseTypeInvalid|Нельзя зарегистрировать мобильное устройство, поскольку ваша учетная запись еще не входит в нужную группу пользователей.<br /><br />Обратитесь к ИТ-администраторам, укажите, что получили сообщение **UserLicenseTypeInvalid** при попытке зарегистрировать мобильное устройство, и подскажите искать решение в этой таблице.|Чтобы пользователь мог зарегистрировать свое устройство, он должен быть членом подходящей группы пользователей. Это сообщение означает, что пользователь располагает неправильным типом лицензии для назначенного центра управления мобильными устройствами. Например, если в качестве центра управления мобильными устройствами назначен Intune, а пользователь использует System Center 2012 R2 Configuration Manager, появится указанное сообщение об ошибке.<br /><br />Дополнительные сведения см. в следующих источниках:<br /><br />Изучите статью [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) (Настройка управления устройствами c iOS и Mac с помощью Microsoft Intune); сведения о настройке пользователей в статьях [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) (Синхронизация Active Directory и добавление пользователей в Intune) и [Organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) (Организация пользователей и устройств).|
|MdmAuthorityNotDefined|Вашему ИТ-администратору необходимо настроить способ управления мобильными устройствами в организации.<br /><br />Обратитесь к ИТ-администраторам, укажите, что получили сообщение **MdmAuthorityNotDefined** при попытке зарегистрировать мобильное устройство, и подскажите искать решение в этой таблице.|В Intune не был назначен центр управления мобильными устройствами.<br /><br />См. пункт 1 в разделе "Step 6: Enroll mobile devices and install an app" ("Шаг 6. Регистрация мобильных устройств и установка приложения") статьи [Get started with a 30-day trial of Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) (Начало работы с 30-дневной пробной версией Microsoft Intune).|

### См. также
[Использование устройства iOS или Mac OS X в Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=Jun16_HO2-->


