---
title: "Регистрация устройств macOS в Intune | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте, как регистрировать устройства macOS в предварительной версии Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Регистрация устройств macOS в предварительной версии Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Администраторы Intune могут управлять устройствами macOS. По умолчанию пользователи могут регистрировать на портале Azure свои устройства macOS. Вам нужно только сообщить своим пользователям, что они должны перейти на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com) и зарегистрировать свои устройства macOS. 

## <a name="prerequisites"></a>Необходимые компоненты

Перед настройкой регистрации устройств macOS выполните следующие предварительные требования:

- [настройте домены](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2);
- [настройте центр MDM](set-mdm-authority.md);
- [создайте группы](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5);
- [настройте корпоративный портал](/intune-azure/manage-apps/company-portal-app.md);
- назначьте пользовательские лицензии на [портале Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854);
- [получите сертификат Apple MDM Push Certificate](get-an-apple-mdm-push-certificate.md).

## <a name="set-up-macos-enrollment"></a>Настройка регистрации устройств macOS

По умолчанию регистрация устройств macOS в Intune разрешена. 

Чтобы просмотреть параметры, которые разрешают или запрещают регистрацию устройств macOS, откройте на портале Azure колонку Intune и щелкните **Регистрация** > **Ограничения регистрации**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Инструкции по регистрации для пользователей см. в статье о [регистрации устройств macOS в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). При регистрации пользователи будут уведомлены о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Использование устройства с iOS или Mac OS в Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


