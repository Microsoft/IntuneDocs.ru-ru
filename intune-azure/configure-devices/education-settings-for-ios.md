---
title: "Настройка параметров образования Intune для iOS"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


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

