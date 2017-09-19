---
title: "Пользовательские параметры для устройств macOS в Intune"
titleSuffix: Azure portal
description: "Узнайте, какие параметры можно использовать в настраиваемом профиле macOS.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d153ebf0693b04d8df7505bd2a69e19353ffbdeb
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Настраиваемые параметры для устройств macOS в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Настраиваемый профиль macOS в Microsoft Intune можно использовать для назначения на устройствах macOS параметров, созданных с помощью [средства Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Это средство позволяет создавать множество параметров, управляющих работой таких устройств, и экспортировать их в профиль конфигурации. Затем этот профиль конфигурации можно импортировать в настраиваемый профиль macOS в Intune и назначить параметры пользователям и устройствам в организации.

Благодаря этой возможности вы можете назначить параметры macOS, которые невозможно настроить с помощью других типов профилей Intune.


1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** укажите следующее:

- **Имя пользовательского профиля конфигурации**. Укажите имя для политики, которое будет отображаться на устройстве и в отчете о состоянии Intune.
- **Файл профиля конфигурации**. Выберите профиль конфигурации, который был создан с помощью средства Apple Configurator.
Убедитесь, что параметры, экспортированные из средства Apple Configurator, совместимы с версией macOS на устройствах, где вы назначаете настраиваемую политику macOS. Для получения сведений о том, как обрабатываются несовместимые настройки, выполните поиск фраз **Справочник по профилям конфигурации** (Configuration Profile Reference) и **Справочник по протоколу управления мобильными устройствами** (Mobile Device Management Protocol Reference) на веб-сайте для [разработчиков Apple](https://developer.apple.com/).

Импортированный файл появится в области колонки **Содержимое файла**.
