---
title: Пользовательские параметры Microsoft Intune для устройств под управлением macOS
titleSuffix: ''
description: Узнайте, какие параметры можно использовать в настраиваемом профиле macOS в Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 66a935b96b802a05831118cd9dc0adbc62bb4bae
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Пользовательские параметры Microsoft Intune для устройств под управлением macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настраиваемый профиль macOS в Microsoft Intune можно использовать для назначения на устройствах macOS параметров, созданных с помощью [средства Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Это средство позволяет создавать множество параметров, управляющих работой таких устройств, и экспортировать их в профиль конфигурации. Затем этот профиль конфигурации можно импортировать в настраиваемый профиль macOS в Intune и назначить параметры пользователям и устройствам в организации.

Благодаря этой возможности вы можете назначить параметры macOS, которые невозможно настроить с помощью других типов профилей Intune.


1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. На панели **Пользовательский профиль конфигурации** настройте все следующие параметры.

- **Имя пользовательского профиля конфигурации**. Укажите имя для политики, которое будет отображаться на устройстве и в состоянии на Intune.
- **Файл профиля конфигурации**. Выберите профиль конфигурации, который был создан с помощью средства Apple Configurator.
Убедитесь, что параметры, экспортированные из средства Apple Configurator, совместимы с версией macOS на устройствах, где вы назначаете настраиваемую политику macOS. Для получения сведений о том, как обрабатываются несовместимые настройки, выполните поиск фраз **Справочник по профилям конфигурации** (Configuration Profile Reference) и **Справочник по протоколу управления мобильными устройствами** (Mobile Device Management Protocol Reference) на веб-сайте для [разработчиков Apple](https://developer.apple.com/).

Импортированный файл появится в области панели **Содержимое файла**.
