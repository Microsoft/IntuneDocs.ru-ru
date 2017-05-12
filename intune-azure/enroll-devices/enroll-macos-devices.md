---
title: "Регистрация устройств macOS в Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, как регистрировать устройства macOS в предварительной версии Intune Azure."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 6fcbeb30fb11b6bc8def3a1c245bff56b3f7cca4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Регистрация устройств macOS в предварительной версии Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune позволяет управлять устройствами macOS. Чтобы включить управление устройствами, пользователям необходимо зарегистрировать их, перейдя на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com) и выполнив указания. Когда устройства macOS будут зарегистрированы в системе управления, вы сможете [создавать для них пользовательские параметры](../configure-devices/custom-for-macos.md). Вскоре будут доступны и другие возможности.

## <a name="prerequisites"></a>Необходимые компоненты

Перед настройкой регистрации устройств macOS выполните следующие предварительные требования:

- [настройте домены](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2);
- [настройте центр MDM](set-mdm-authority.md);
- [Создание групп](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [настройте корпоративный портал](../manage-apps/company-portal-app.md);
- назначьте пользовательские лицензии на [портале Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854);
- [получите сертификат Apple MDM Push Certificate](get-an-apple-mdm-push-certificate.md).

## <a name="set-up-macos-enrollment"></a>Настройка регистрации устройств macOS

По умолчанию регистрация устройств macOS в Intune разрешена.

Сведения о том, как запретить регистрацию устройств macOS, см. в разделе [Установка ограничений по типу устройства](set-enrollment-restrictions.md#set-device-type-restrictions).

Сведения о том, как задать максимальное число устройств, которые может зарегистрировать пользователь, см. в разделе [Установка ограничений по числу устройств](set-enrollment-restrictions.md#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Вам нужно сообщить своим пользователям, что они должны перейти на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com) и зарегистрировать свои устройства, выполнив указания. Вы также можете отправить им ссылку инструкции по регистрации в Интернете: [Регистрация устройства Mac OS в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos).

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Использование устройства с iOS или Mac OS в Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)

