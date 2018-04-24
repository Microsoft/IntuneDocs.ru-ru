---
title: Разрешение доступа к ресурсам компании
description: Профили Wi-Fi, VPN и электронной почты в совокупности позволяют пользователям получать доступ к нужным файлам и ресурсам.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5bfc02f5f10ce88b992d0ea250d7b36fdf3f66dc
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="enable-access-to-company-resources-with-microsoft-intune"></a>Разрешение доступа к ресурсам компании с помощью Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Профили Wi-Fi, VPN и электронной почты в Microsoft Intune совместно позволяют пользователям получать доступ к файлам и ресурсам, необходимым для работы в любом месте. Профили сертификатов помогают защитить этот доступ.

## <a name="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms"></a>[Профили Wi-Fi](wi-fi-connections-in-microsoft-intune.md) и поддерживаемые платформы

Разверните параметры беспроводной сети для пользователей. Эти параметры упрощают подключение к корпоративной сети.
#### <a name="supported-platforms"></a>Поддерживаемые платформы

|Windows 8.1 и более поздние версии|Windows Phone 8.1 и более поздней версии|iOS|Android|Samsung KNOX Standard|
|---------------------|---------------------------|---|-------|------------|
|Да (вы можете импортировать профиль Wi-Fi Windows)|Да (вы можете настроить OMA-URI) |Да|Да|Да|

## <a name="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms"></a>[Профили VPN](vpn-connections-in-microsoft-intune.md) и поддерживаемые платформы
Разверните параметры виртуальной частной сети (VPN) для своих пользователей. Эти параметры упрощают подключение к ресурсам в корпоративной сети.

|Windows 8.1 и более поздние версии|Windows Phone 8.1 и более поздней версии|iOS|Android|Samsung KNOX Standard|
|---------------------|---------------------------|---|-------|------------|
|Да|Да|Да|Да|Да|

## <a name="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms"></a>[Профили электронной почты](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) и поддерживаемые платформы
Создание, развертывание и отслеживание параметров собственных почтовых клиентов на устройствах в организации.


| Windows 8.1 и более поздние версии | Windows Phone 8.1 и более поздней версии | iOS | Android | Samsung KNOX Standard |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          Нет           |             да             | Да |   Нет    |          Да          |

> [!NOTE]
> Сведения о настройке профиля Wi-Fi для Windows Phone 8.1 с помощью OMA-URI см. в [этой записи блога по Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/).

## <a name="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms"></a>[Профили сертификатов](secure-resource-access-with-certificate-profiles.md) и поддерживаемые платформы
Помогите обеспечить безопасный доступ к ресурсам компании, включая беспроводные сети и VPN-подключения.


| Windows 8.1 и более поздние версии | Windows Phone 8.1 и более поздней версии | iOS | Android | Samsung KNOX Standard |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          Да          |             Да             | Да |   Да   |          Да          |

