---
title: "Что собой представляют профили устройств в Microsoft Intune?"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте о профилях устройств Intune и о том, как они могут помочь в управлении и защите устройств в вашей компании."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: eb48265e4655117976c9847b1f5bee712f0c2e3c
ms.lasthandoff: 02/18/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Что такое профили устройств в Microsoft Intune?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Рабочая нагрузка **настройки устройств** Microsoft Intune позволяет управлять параметрами и функциями на всех устройствах. Эта рабочая нагрузка чаще всего используется для создания профилей устройств, которые позволяют управлять широким спектром возможностей и функций на управляемых устройствах.

Открыв ее, вы увидите следующие параметры:

- **Обзор.** На этой странице содержатся сведения о состоянии и отчеты, помогающие отслеживать конфигурации устройств, назначенных пользователям и устройствам.
- **Manage Profiles** (Управление профилями). В этом разделе вы сможете создать профили конфигурации устройств. Ниже представлен список всех типов профилей, которые можно создать.
- **Setup Certificate Authority** (Настройка центра сертификации). В данном рабочем процессе описаны шаги, необходимые для настройки сертификатов. Вам потребуется выполнить эти шаги, если вы хотите работать с профилями сертификатов Intune.

## <a name="getting-started"></a>Начало работы

Рабочий процесс создания профилей устройств одинаковый для всех профилей. Дополнительные сведения о создании профилей конфигурации устройств Microsoft Intune см. в [этой статье](/intune-azure/configure-devices/how-to-create-device-profiles). Далее приведены сведения о создании параметров для каждого типа профиля.

Ниже указаны возможности, которыми можно управлять на устройствах.

## <a name="device-restrictions"></a>Ограничения устройств
Ограничения устройств позволяют управлять параметрами и функциями разных категорий, включая безопасность, браузер, оборудование и общий доступ к данным. Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств iOS.
Дополнительные сведения см. в статье [о настройке параметров ограничения для устройств](how-to-configure-device-restrictions.md). Поддержка: устройства Android, iOS, macOS, Windows 10 и Windows 10 для совместной работы.

## <a name="email"></a>Электронная почта
Профили электронной почты позволяют создавать, развертывать и контролировать параметры электронной почты Exchange ActiveSync на управляемых устройствах. Развертывая эти параметры, вы обеспечиваете согласованность, сокращение числа обращений в службу поддержки, а также предоставляете пользователям доступ к электронной почте компании с личных устройств без дополнительных настроек с их стороны.
Дополнительные сведения см. в статье [о настройке параметров электронной почты](how-to-configure-email-settings.md). Поддержка: устройства Android, iOS, Windows Phone 8.1 и Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Используйте профили Wi-Fi, чтобы развернуть параметры беспроводной сети для пользователей и устройств в вашей организации. При развертывании профиля Wi-Fi пользователи получают доступ к корпоративной сети Wi-Fi, не настраивая его самостоятельно.
Дополнительные сведения см. в статье [о настройке параметров Wi-Fi](how-to-configure-wi-fi-settings.md). Поддержка: устройства Android, iOS, macOS и Windows 8.1 (только импорт).

## <a name="vpn"></a>VPN
Виртуальная частная сеть (VPN) предоставляет пользователям безопасный удаленный доступ к сети компании. Устройства используют профиль VPN-подключения для создания подключения к VPN-серверу. Используйте профили VPN, чтобы развернуть параметры VPN для пользователей и устройств в организации, чтобы обеспечить простое и безопасное подключение к сети.
Дополнительные сведения см. в статье [о настройке параметров VPN](how-to-configure-vpn-settings.md).
Поддержка: устройства Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 и Windows 10.

## <a name="certificates"></a>Сертификаты
Профиль этого типа позволяет настроить доверенные сертификаты, сертификаты SCEP и PKCS, которые можно назначить устройствам и использовать для проверки подлинности Wi-Fi, VPN и профилей электронной почты.
Дополнительные сведения см. в статье [о настройке сертификатов](how-to-configure-certificates.md). Поддержка: устройства Android, iOS, Windows Phone 8.1, Windows 8.1 и Windows 10.

## <a name="edition-upgrade"></a>Обновление выпусков
Профиль этого типа позволяет автоматически обновлять устройства под управлением некоторых версий Windows 10 до более новых выпусков. Дополнительные сведения см. в статье [о настройке обновлений выпусков Windows 10](how-to-configure-windows-10-edition-upgrade.md). Поддержка: только устройства Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
Windows Information Protection позволяет предотвратить утечку данных, не влияя при этом на работу сотрудника. Кроме того, эта политика обеспечивает защиту приложений и данных на устройствах, принадлежащих организации, и личных устройствах сотрудников от случайной утечки данных. При этом нет необходимости вносить какие-либо изменения в вашу среду или другие приложения.
Дополнительные сведения см. в статье [о настройке Windows Information Protection](how-to-configure-windows-information-protection.md). Поддержка: только устройства Windows 10.

## <a name="custom"></a>Особые настройки
На устройстве можно назначать настраиваемые параметры, не встроенные в Intune. Например, на устройствах Android можно указать значения OMA-URI для настройки устройства. Для устройств iOS можно импортировать файл конфигурации, созданный в Apple Configurator.
Дополнительные сведения см. в статье [о настройке особых параметров](how-to-configure-custom-settings.md). Поддержка: устройства Android, iOS, macOS и Windows Phone 8.1.
