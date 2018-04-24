---
title: Настраиваемые параметры Microsoft Intune для устройств под управлением iOS
titleSuffix: ''
description: Узнайте, какие параметры можно использовать в настраиваемом профиле iOS в Microsoft Intune.
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
ms.openlocfilehash: ada36b11489adbbcaf67db9192c7dd66caadb525
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Настраиваемые параметры Microsoft Intune для устройств под управлением iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настраиваемый профиль iOS в Microsoft Intune можно использовать для назначения на устройствах iOS параметров, созданных с помощью [средства Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Это средство позволяет создавать множество параметров, управляющих работой таких устройств, и экспортировать их в профиль конфигурации. Затем этот профиль конфигурации можно импортировать в настраиваемый профиль iOS в Intune и назначить параметры пользователям и устройствам в организации.

Благодаря этой возможности вы можете назначить параметры iOS, которые невозможно настроить с помощью других типов профилей Intune.


1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. На панели **Пользовательский профиль конфигурации** настройте все следующие параметры.

- **Имя пользовательского профиля конфигурации**. Укажите имя для политики, которое будет отображаться на устройстве и в состоянии на Intune.
- **Файл профиля конфигурации**. Выберите профиль конфигурации, который был создан с помощью средства Apple Configurator.
Убедитесь, что параметры, экспортированные из средства Apple Configurator, совместимы с версией iOS на устройствах, где вы назначаете настраиваемую политику iOS. Для получения сведений о том, как обрабатываются несовместимые настройки, выполните поиск фраз **Справочник по профилям конфигурации** (Configuration Profile Reference) и **Справочник по протоколу управления мобильными устройствами** (Mobile Device Management Protocol Reference) на веб-сайте для [разработчиков Apple](https://developer.apple.com/).

Импортированный файл появится в области панели **Содержимое файла**.
