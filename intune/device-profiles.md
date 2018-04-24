---
title: Профили устройств в Microsoft Intune —Azure | Документы Майкрософт
description: На портале Azure приводятся общие сведения о различных профилях устройств Microsoft Intune, в том числе функции, ограничения, электронная почта, Wi-Fi, VPN, образование, сертификаты, обновления Windows 10, BitLocker и защитник Windows, Windows Information Protection и пользовательские параметры устройства. Используйте эти профили для управления и защиты данных и устройств в вашей компании.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b942f794136ce1a1d7851b0b04d6df70ea7174c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Что такое профили устройств в Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune включает в себя параметры и функции, которые можно включать или отключать на различных устройствах в вашей организации. Эти параметры и функции управляются с помощью профилей. Примеры профилей: 

- Профиль Wi-Fi, который предоставляет различным устройствам доступ к вашей корпоративной сети Wi-Fi
- Профиль VPN, предоставляющий различным устройствам доступ к VPN-серверу в корпоративной сети

В этой статье описываются различные профили, которые вы можете создать для устройств. С помощью этих профилей можно включать или отключать некоторые функции на устройствах.

## <a name="before-you-begin"></a>Подготовка к работе
Чтобы просмотреть доступные функции, откройте [портал Azure](https://portal.azure.com) и ресурс Intune. 

**Конфигурация устройства** включает следующие параметры:

- **Обзор**: состояния профилей и дополнительные сведения о профилях, назначенных для пользователей и устройств
- **Управление**: создание профилей устройств и отправка пользовательских [сценариев PowerShell](intune-management-extension.md) для запуска в профиле
- **Монитор**: проверка состояния профиля (успех или ошибка) и просмотр журналов для профилей
- **Настройка**: добавление ЦС (SCEP или PFX) или включение управления затратами на телекоммуникации для профиля

## <a name="create-the-profile"></a>Создание профиля

[Создание профилей устройств](device-profile-create.md) содержит пошаговые инструкции по созданию профиля. 

## <a name="device-features-profile"></a>Профиль возможностей устройства

[Возможности устройств](device-features-configure.md) позволяют управлять возможностями устройств с iOS и macOS, например AirPrint, уведомлениями и конфигурациями общих устройств.

Эта функция поддерживает:  
- iOS 
- macOS

## <a name="device-restrictions-profile"></a>Профиль ограничений устройств
[Ограничения устройств](device-restrictions-configure.md) позволяют управлять безопасностью, оборудованием, общим доступом к данным и другими параметрами на устройствах. Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств с iOS. 

Эта функция поддерживает: 

- Android
- iOS
- macOS
- Windows 10
- Windows 10 для совместной работы

## <a name="email-profile"></a>Email profile (Профиль электронной почты)
Профиль [параметров электронной почты](email-settings-configure.md) позволяет создавать, назначать и отслеживать параметры электронной почты Exchange ActiveSync на устройствах. Профили электронной почты обеспечивают согласованность, сокращение числа обращений в службу поддержки, а также предоставляют пользователям доступ к электронной почте компании с личных устройств без дополнительных настроек с их стороны. 

Эта функция поддерживает: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="wi-fi-profile"></a>Профиль Wi-Fi
[Параметры Wi-Fi](wi-fi-settings-configure.md) — параметры беспроводной сети для пользователей и устройств. При назначении профиля Wi-Fi пользователи получают доступ к корпоративной сети Wi-Fi, не настраивая ее самостоятельно. 

Эта функция поддерживает: 

- Android
- iOS
- macOS
- Windows 8.1 (только импорт)

## <a name="vpn-profile"></a>VPN profile (Профиль VPN)
[Параметры VPN](vpn-settings-configure.md) — назначение профилей VPN для пользователей и устройств в организации и обеспечение простого и безопасного подключения к сети. 

Виртуальная частная сеть (VPN) предоставляет пользователям безопасный удаленный доступ к сети компании. Устройства используют профиль VPN-подключения для создания подключения к VPN-серверу. 

Эта функция поддерживает: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="education-profile"></a>Профиль образования
[Параметры образования](education-settings-configure.md) — настройка параметров для [приложения Windows Take a Test](https://education.microsoft.com/gettrained/win10takeatest). После настройки этих параметров никакие другие приложения не смогут работать на устройстве до завершения теста.

## <a name="certificates-profile"></a>Профиль сертификатов
[Сертификаты](certificates-configure.md) — настройка доверенных сертификатов, сертификатов SCEP и PKCS, которые можно назначить устройствам и использовать для проверки подлинности Wi-Fi, VPN и профилей электронной почты.

Эта функция поддерживает: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="edition-upgrade-profile"></a>Профиль обновления выпусков
[Обновления выпуска Windows 10](edition-upgrade-configure-windows-10.md) — автоматическое обновление устройств, работающих под управлением одной из версий Windows 10.

Эта функция поддерживает: только Windows 10

## <a name="endpoint-protection-profile"></a>Профиль Endpoint Protection
[Параметры Endpoint Protection для Windows 10](endpoint-protection-windows-10.md) — настройка параметров BitLocker и защитника Windows для устройств Windows 10.

Сведения о внедрении Advanced Threat Protection в Защитнике Windows (WDATP) с помощью Microsoft Intune см. в статье [Настройка конечных точек с помощью средств управления мобильными устройствами (MDM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Эта функция поддерживает: только Windows 10

## <a name="windows-information-protection-profile"></a>Профиль Windows Information Protection
[Windows Information Protection](windows-information-protection-configure.md) позволяет предотвратить утечку данных, не влияя при этом на работу сотрудника. Кроме того, эта политика защищает от случайной утечки данных корпоративные приложения и данные на рабочих устройствах, принадлежащих организации или сотрудникам. Это делается без внесения изменений в вашу среду или другие приложения.

Эта функция поддерживает: только Windows 10

## <a name="custom-profile"></a>Пользовательский профиль
[Пользовательские параметры](custom-settings-configure.md) — возможность назначения устройствам параметров, не встроенных в Intune. Например, на устройствах Android можно ввести значения OMA-URI. Для устройств iOS можно импортировать файл конфигурации, созданный в Apple Configurator. 

Эта функция поддерживает:

- Android
- iOS
- macOS
- Windows Phone 8.1