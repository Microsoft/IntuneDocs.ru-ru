---
title: Настройка Microsoft Intune
description: Требования и предварительные условия, которые следует выполнить перед использованием подписки Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36f7e2105d27ccb996f4544ec6633babcff032b1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721725"
---
# <a name="set-up-intune"></a>Настройка Intune

Эти шаги по настройке позволяют включить управление мобильными устройствами (MDM) с помощью Intune. Прежде чем предоставить пользователям доступ к корпоративным ресурсам или управлять параметрами этих устройств, необходимо включить управление устройствами.

Некоторые действия, такие как настройка подписки Intune и установка центра управления мобильными устройствами, являются обязательными в большинстве сценариев. Другие действия, такие как настройка личного домена или добавление приложений, являются необязательными в зависимости от потребностей вашей организации.

Если в данный момент вы используете Microsoft System Center Configuration Manager для управления компьютерами и серверами, можно [расширить функции Configuration Manager на облако, чтобы использовать совместное управление](https://docs.microsoft.com/sccm/comanage/overview).

>[!TIP]
>При покупке по меньшей мере 150 лицензий для Intune в соответствующем плане можно использовать *преимущество Center FastTrack*. Благодаря этой службе специалисты Майкрософт помогут вам подготовить среду к работе с Intune. См. статью [Программа FastTrack для Enterprise Mobility](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Шаги |                                                                                                                       Состояние                                                                                                                       |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   1   |                                        [Поддерживаемые конфигурации](supported-devices-browsers.md). Что необходимо знать перед началом работы. Сюда входят поддерживаемые конфигурации и требования к сети.                                         |
|   2   |                                                                 [Вход в Intune](account-sign-up.md). Вход в пробную подписку или создание подписки Intune.                                                                  |
|   3   |                [Настройка имени домена](custom-domain-name-configure.md). Настройка регистрации DNS для подключения к доменному имени организации с помощью Intune. При этом пользователи получают знакомый домен при подключении к Intune и использовании ресурсов.                |
|   4   |                                   [Добавление пользователей](users-add.md). Ручное добавление пользователей или подключение к Active Directory для синхронизации пользователей с помощью Intune. Требуется, если устройства не являются устройствами киоска без пользователей.                                    |
|   5   |                                            [Назначение лицензий](../licenses-assign.md). Предоставление пользователям разрешения на использование Intune. Каждому пользователю или устройству без пользователя требуется лицензия Intune для доступа к службе.                                             |
|   6   |                                               [Добавление групп](../groups-add.md). Использование групп пользователей и устройств для упрощения задач управления. Группы используются для назначения приложений, параметров и других ресурсов.                                                |
|   7   |                                                                        [Добавление приложений](../apps/apps-add.md). Приложения могут быть назначены группам автоматически или установлены в случае необходимости.                                                                         |
|   8   | [Настройка устройств](../configuration/device-profiles.md). Настройка профилей для управления параметрами устройств. Профили устройств позволяют предварительно настроить параметры для электронной почты, VPN, Wi-Fi и функций устройств. Они также могут ограничить устройства для защиты как устройств, так и данных. |
|   9   |       [Настройка корпоративного портала](../apps/company-portal-app.md). Настройка корпоративного портала Intune, с помощью которого пользователи регистрируют устройства и устанавливают приложения. Эти параметры отображаются в приложении корпоративного портала и на веб-сайте корпоративного портала.       |
|  10   |                                [Включение регистрации устройств](mdm-authority-set.md). Включение управления Intune устройствами iOS, Windows, Mac и Android путем установки центра управления мобильными устройствами и включения конкретных платформ.                                 |
|  11   |                                                        [Настроить политики приложений](../apps/app-protection-policy.md). Задайте параметры в соответствии с политиками защиты приложений в Microsoft Intune.                                                         |
