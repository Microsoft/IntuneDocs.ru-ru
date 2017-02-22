---
title: "Настройка параметров образования Intune для iOS | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте о настройках, которые можно использовать для контроля параметров образования на устройствах iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: e52fdf8c30a680d62071cd31e308dd0180e8b9dc


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Как настроить параметры образования Intune для iOS в предварительной версии Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Создание профиля устройства с параметрами образования iOS

1. Войдите на портал Azure.
2. Выберите **Больше служб** > **Другое** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создание профиля**.
4. В колонке **Создание профиля** введите **имя** и **описание** для профиля обновления выпуска.
5. В раскрывающемся списке **Платформа** выберите **iOS**.
6. В раскрывающемся списке **Тип профиля** выберите **Образование**.
7. В колонке **Образование** выберите следующее:
    - **файл корневого сертификата преподавателя**;
    - **профиль PKCS12/PFX преподавателя**;
    - **файл корневого сертификата учащегося**;
    - **профиль PKCS12/PFX учащегося**.
8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.



<!--HONumber=Feb17_HO1-->


