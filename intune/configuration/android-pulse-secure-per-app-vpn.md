---
title: Пользовательский профиль VPN на уровне приложения в Android
titleSuffix: Microsoft Intune
description: Сведения о том, как создать профиль VPN на уровне приложения для устройств Android, находящихся под управлением Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e8635abe2b1f927147d5a30085efb9884ec7813
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724286"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Использование пользовательского профиля Microsoft Intune с целью создания профиля VPN для каждого приложения на устройствах Android

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Для устройств Android 5.0 и более поздней версии, находящихся под управлением Intune, можно создать профиль VPN на уровне приложения. Сначала создайте профиль VPN, который использует тип подключения Pulse Secure или Citrix. Затем создайте настраиваемую политику конфигурации, которая связывает профиль VPN с конкретным приложением.

После назначения политики группам пользователей или устройств Android пользователям следует запустить клиент VPN Pulse Secure или Citrix. Затем клиент VPN позволит использовать открытое VPN-подключение только для трафика из указанных приложений.

> [!NOTE]
>
> Для этого профиля поддерживаются только типы подключений Pulse Secure и Citrix.


## <a name="step-1-create-a-vpn-profile"></a>Шаг 1. Создание профиля VPN


1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. На панели **Intune** выберите пункт **Конфигурация устройства**.
2. На панели **Конфигурации устройства** в разделе **Управление** выберите **Профили**.
2. На панели списка профилей выберите **Создать профиль**.
3. На панели **Создать профиль** введите **имя** и **описание** (необязательно) для профиля VPN.
4. В раскрывающемся списке **Платформа** выберите **Android**.
5. В раскрывающемся списке **Тип профиля** выберите **VPN**.
3. Выберите **Параметры** > **Настройка**. Затем настройте профиль VPN, следуя инструкциям в статьях о [настройке параметров VPN](vpn-settings-configure.md) и [параметрах Intune VPN для устройств Android](vpn-settings-android.md).

Запишите значение параметра **Имя подключения**, которое было указано при создании профиля VPN. Оно потребуется на следующем шаге. Например, **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Шаг 2. Создание настраиваемой политики конфигурации

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. На панели **Intune** выберите пункт **Конфигурация устройства**.
2. На панели **Конфигурации устройства** в разделе **Управление** выберите **Профили**.
3. На панели профилей выберите **Создать профиль**.
4. На панели **Создать профиль** введите **имя** и **описание** для пользовательского профиля.
5. В раскрывающемся списке **Платформа** выберите **Android**.
6. В раскрывающемся списке **Тип профиля** выберите **Пользовательский**.
7. Выберите **Параметры** > **Настроить**.
3. На панели **Настраиваемые параметры OMA-URI** выберите **Добавить**.
    - Введите имя параметра.
    - В поле **OMA-URI** укажите следующую строку: **./Vendor/MSFT/VPN/Profile/*Имя*/PackageList**, где *Имя* — это название подключения из шага 1. В нашем примере строка будет такой: **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - В поле **Тип данных** укажите **Строка**.
    - В поле **Значение** укажите имена пакетов, которые должны быть связаны с профилем, разделяя их точкой с запятой. Например, если вы хотите, чтобы VPN-подключение использовали Excel и браузер Google Chrome, введите: **com.microsoft.office.excel;com.android.chrome**.

![Пример настраиваемой политики VPN на уровне приложения для Android](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Отметьте список приложений как список разрешенных или запрещенных (необязательно)
  Приложениям в списке можно *запретить* использование VPN-подключения. Для этого укажите значение **BLACKLIST**. Все остальные приложения будут подключаться через VPN.
Кроме того, можно использовать значение **WHITELIST**, чтобы указать список приложений, которым *разрешено* использовать VPN-подключение. Приложения, которые не входят в список, не подключаются через VPN.
  1. На панели **Настраиваемые параметры OMA-URI** выберите **Добавить**.
  2. Введите имя параметра.
  3. В поле **OMA-URI** укажите следующую строку: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, где *Name* — имя профиля VPN, записанное на шаге 1. В нашем примере строка будет такой: **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  4. В поле **Тип данных** укажите **Строка**.
  5. В поле **Значение** введите **BLACKLIST** или **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Шаг 3 Назначение обеих политик

Следуйте указаниям в статье о [назначении профилей устройств](device-profile-assign.md), чтобы присвоить оба профиля соответствующим пользователям или устройствам.