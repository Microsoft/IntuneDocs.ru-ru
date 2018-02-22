---
title: "Регистрация устройств macOS в Intune"
titlesuffix: Azure portal
description: "Узнайте, как регистрировать устройства macOS в Intune.\""
keywords: 
author: ErikjeMS
ms.author: erikje
nmanager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f896ebd51f989c0e441043d320247946cdb8997b
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="enroll-macos-devices-in-intune"></a>Регистрация устройств macOS в Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune позволяет управлять устройствами macOS. Чтобы включить управление устройствами, пользователям необходимо зарегистрировать их, перейдя на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com) и выполнив указания. Когда устройства macOS будут зарегистрированы в системе управления, вы сможете [создавать для них пользовательские параметры](custom-settings-macos.md). Вскоре будут доступны и другие возможности.

## <a name="prerequisites"></a>Предварительные условия

Перед настройкой регистрации устройств macOS выполните следующие предварительные требования:

- [настройте домены](custom-domain-name-configure.md);
- [настройте центр MDM](mdm-authority-set.md);
- [Создание групп](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [настройте корпоративный портал](company-portal-app.md);
- назначьте пользовательские лицензии на [портале Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854);
- [получите сертификат Apple MDM Push Certificate](apple-mdm-push-certificate-get.md).

## <a name="set-up-macos-enrollment"></a>Настройка регистрации устройств macOS

По умолчанию регистрация устройств macOS в Intune разрешена.

Сведения о том, как запретить регистрацию устройств macOS, см. в разделе [Установка ограничений по типу устройства](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Сообщите пользователям, что они должны перейти на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com) и зарегистрировать свои устройства, следуя подсказкам. Вы также можете отправить им ссылку инструкции по регистрации в Интернете: [Регистрация устройства Mac OS в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](end-user-educate.md)
- [Использование устройства macOS в Intune](/intune-user-help/using-your-macos-device-with-intune)
