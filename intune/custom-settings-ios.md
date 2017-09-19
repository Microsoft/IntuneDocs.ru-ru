---
title: "Пользовательские параметры Intune для устройств iOS"
titleSuffix: Azure portal
description: "Узнайте, какие параметры можно использовать в настраиваемом профиле iOS.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
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
ms.openlocfilehash: 6ef1d45946b22a2e41e1b6ea758a7cb1a472fefd
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2017
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
