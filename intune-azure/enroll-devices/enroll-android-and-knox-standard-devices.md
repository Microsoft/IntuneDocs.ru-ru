---
title: "Регистрация устройств Android в Intune | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте, как регистрировать устройства Android в предварительной версии Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Регистрация устройств Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Как администратор Intune вы можете включить управление устройствами Android (в т. ч. устройства Samsung Knox Standard) из корпоративного портала. После этого пользователи могут зарегистрировать свои устройства с помощью доступного в Google Play приложения корпоративного портала.

## <a name="prerequisite"></a>Необходимое условие

Чтобы подготовиться к управлению мобильными устройствами, в качестве центра MDM необходимо указать **Microsoft Intune**. Инструкции см. в статье [Установка центра управления мобильными устройствами](set-mdm-authority.md). Этот параметр указывается только один раз при первой настройке Intune для управления мобильными устройствами, поэтому, возможно, он уже настроен. 

## <a name="set-up-android-enrollment"></a>Настройка регистрации устройств Android

По умолчанию в службе Intune разрешена регистрация устройств с Android и Samsung Knox Standard. 

Чтобы просмотреть параметры, которые разрешают или запрещают регистрацию устройств Android, откройте на портале Azure колонку Intune и щелкните **Регистрация** > **Ограничения регистрации**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). При регистрации пользователи будут уведомлены о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Использование устройства Android с Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


