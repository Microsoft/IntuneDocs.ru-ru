---
title: "Пользовательские параметры для устройств macOS в Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, какие параметры можно использовать в настраиваемом профиле macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 84902bb0e7ea67b388debd8bd7992d396d981a7b
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Настраиваемые параметры для устройств macOS в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Настраиваемый профиль macOS в Microsoft Intune можно использовать для развертывания на устройствах macOS настроек, созданных с помощью [средства Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Это средство позволяет создавать множество параметров, управляющих работой таких устройств, и экспортировать их в профиль конфигурации. Затем этот профиль конфигурации можно импортировать в настраиваемый профиль macOS в Intune и назначить параметры пользователям и устройствам в организации.

Благодаря этой возможности вы можете развернуть параметры macOS, которые невозможно настроить с помощью других типов профилей Intune.


1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** укажите следующее:

- **Имя пользовательского профиля конфигурации**. Укажите имя для политики, которое будет отображаться на устройстве и в отчете о состоянии Intune.
- **Файл профиля конфигурации**. Выберите профиль конфигурации, который был создан с помощью средства Apple Configurator.
Убедитесь, что параметры, экспортированные из средства Apple Configurator, совместимы с версией macOS на устройствах, где вы развертываете настраиваемую политику macOS. Для получения сведений о том, как обрабатываются несовместимые настройки, выполните поиск фраз **Справочник по профилям конфигурации** (Configuration Profile Reference) и **Справочник по протоколу управления мобильными устройствами** (Mobile Device Management Protocol Reference) на веб-сайте для [разработчиков Apple](https://developer.apple.com/).

Импортированный файл появится в области колонки **Содержимое файла**.

