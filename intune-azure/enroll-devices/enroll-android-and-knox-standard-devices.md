---
title: "Подготовка к регистрации устройств Android в Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, как регистрировать устройства Android в предварительной версии Intune Azure."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b7188dd8163334429396e7b7c8687810a6e63bb2
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-android-devices"></a>Регистрация устройств Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune позволяет управлять устройствами Android, включая устройства Samsung Knox Standard. Чтобы обеспечить управление устройствами, пользователям необходимо зарегистрировать их, скачав приложение корпоративного портала Intune, которое доступно в Google Play, а затем открыв это приложение и выполнив указания по установке. Когда устройства Android будут зарегистрированы в системе управления, вы можете [создавать политики соответствия требованиям](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [управлять приложениями](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) и выполнять другие действия.

## <a name="prerequisite"></a>Необходимое условие

Чтобы подготовиться к управлению мобильными устройствами, в качестве центра MDM необходимо указать **Microsoft Intune**. Инструкции см. в статье [Установка центра управления мобильными устройствами](set-mdm-authority.md). Этот параметр указывается только один раз при первой настройке Intune для управления мобильными устройствами, поэтому, возможно, он уже настроен. 

## <a name="set-up-android-enrollment"></a>Настройка регистрации устройств Android

По умолчанию в службе Intune разрешена регистрация устройств Android и Samsung Knox Standard. 

Чтобы заблокировать регистрацию всех или только личных устройств Android, см. инструкции в разделе [Установка ограничений по типу устройства](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions). 

Сведения о том, как задать максимальное число устройств, которые может зарегистрировать пользователь, см. в разделе [Установка ограничений по числу устройств](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Вам следует сообщить пользователям о том, что им необходимо перейти в Google Play, чтобы скачать приложение корпоративного портала Intune, а затем открыть это приложение и зарегистрировать устройство, выполнив указания. Приложение помогает пользователям пройти процедуру регистрации, уведомляя их о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.

Вы также можете отправить им ссылку инструкции по регистрации в Интернете: [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). 

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Использование устройства Android с Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
