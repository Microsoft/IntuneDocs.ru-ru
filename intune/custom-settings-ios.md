---
title: "Пользовательские параметры Intune для устройств iOS"
titleSuffix: Azure portal
description: "Узнайте, какие параметры можно использовать в настраиваемом профиле iOS.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f7dfb69b8e837229eac9a4cdd68316a7559441f4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Пользовательские параметры Microsoft Intune для устройств iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Настраиваемый профиль iOS в Microsoft Intune можно использовать для назначения на устройствах iOS параметров, созданных с помощью [средства Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Это средство позволяет создавать множество параметров, управляющих работой таких устройств, и экспортировать их в профиль конфигурации. Затем этот профиль конфигурации можно импортировать в настраиваемый профиль iOS в Intune и назначить параметры пользователям и устройствам в организации.

Благодаря этой возможности вы можете назначить параметры iOS, которые невозможно настроить с помощью других типов профилей Intune.


1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** укажите следующее:

- **Имя пользовательского профиля конфигурации**. Укажите имя для политики, которое будет отображаться на устройстве и в отчете о состоянии Intune.
- **Файл профиля конфигурации**. Выберите профиль конфигурации, который был создан с помощью средства Apple Configurator.
Убедитесь, что параметры, экспортированные из средства Apple Configurator, совместимы с версией iOS на устройствах, где вы назначаете настраиваемую политику iOS. Для получения сведений о том, как обрабатываются несовместимые настройки, выполните поиск фраз **Справочник по профилям конфигурации** (Configuration Profile Reference) и **Справочник по протоколу управления мобильными устройствами** (Mobile Device Management Protocol Reference) на веб-сайте для [разработчиков Apple](https://developer.apple.com/).

Импортированный файл появится в области колонки **Содержимое файла**.
