---
title: Добавление параметров VPN в Microsoft Intune для устройств в Azure | Документация Майкрософт
description: Для устройств Android, Android Enterprise, iOS, macOS и Windows используйте встроенные параметры для создания подключений к виртуальной частной сети (VPN) в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b96de28e517a989fc1e749176039e6c02ef51e0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723779"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>Создание профилей VPN для подключения к VPN-серверам в Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Виртуальная частная сеть (VPN) предоставляет пользователям безопасный удаленный доступ к сети организации. Устройства используют профиль VPN-подключения для установления подключения к VPN-серверу. Используйте **профили VPN** в Microsoft Intune, чтобы назначить параметры VPN пользователей и устройств в организации для обеспечения простого и безопасного подключения к сети организации.

Например, представим, что вам нужно настроить параметры для подключения к общей папке в сети организации на всех устройствах с iOS. Вы создаете профиль VPN, включающий эти параметры. Затем этот профиль назначается всем пользователям с устройствами iOS. VPN-подключение появится в списке доступных сетей, и пользователи смогут с легкостью использовать его.

> [!NOTE]
> С помощью [настраиваемых политик конфигураций Intune](custom-settings-configure.md) можно создать профили VPN для следующих платформ:
>
> * Android 4 и более поздней версии.
> * Зарегистрированные устройства под управлением Windows 8.1 и более поздней версии.
> * Windows Phone 8.1 и более поздней версии
> * Зарегистрированные устройства под управлением Windows 10 Desktop и более поздней версии.
> * Windows 10 Mobile
> * Windows Holographic for Business

## <a name="vpn-connection-types"></a>Типы VPN-подключений

Вы можете создать профили VPN, используя следующие типы подключений.

|Тип подключения|Платформа|
|-|-|
|Автоматически|Windows 10|
|Check Point Capsule VPN|– Android<br/>– Рабочие профили Android для бизнеса<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|Cisco AnyConnect|– Android<br/>– Рабочие профили Android для бизнеса<br/>– владельцы устройств Android для бизнеса (полностью управляемых)<br/>– iOS<br/>– macOS|
|Cisco (IPSec)|iOS|
|Citrix SSO|– Android<br/>– Рабочие профили Android для бизнеса: Используйте [политику настройки приложения](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|Пользовательская сеть VPN|– iOS<br/>– macOS|
|F5 Access|– Android<br/>– Рабочие профили Android для бизнеса<br/>– владельцы устройств Android для бизнеса (полностью управляемых)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|IKEv2|Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|– Рабочие профили Android для бизнеса: Используйте [политику настройки приложения](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|PPTP|Windows 10|
|Pulse Secure|– Android<br/>– Рабочие профили Android для бизнеса<br/>– владельцы устройств Android для бизнеса (полностью управляемых)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|SonicWall Mobile Connect|– Android<br/>– Рабочие профили Android для бизнеса<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|Zscaler|– Рабочие профили Android для бизнеса: Используйте [политику настройки приложения](../apps/app-configuration-policies-use-android.md)<br/>– iOS|

> [!IMPORTANT]
> Перед использованием назначенных устройству профилей VPN необходимо установить приложение VPN, подходящее для профиля. Чтобы назначить приложение с помощью Intune, см. инструкции в статье [Что такое управление приложениями с помощью Microsoft Intune](../apps/app-management.md).  

Чтобы узнать, как создать настраиваемые профили VPN с помощью параметров URI, см. [эту](custom-settings-configure.md) статью.

## <a name="create-a-device-profile"></a>Создание профиля устройства

1. В [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) последовательно выберите **Конфигурация устройств** > **Профили** > **Создать профиль**.
2. Укажите следующие свойства.

    - **Имя**. Введите описательное имя для нового профиля. Назначьте имена профилям, чтобы позже их можно было легко найти. Например, хорошее имя профиля — **Профиль VPN для всей компании**.
    - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите платформу устройств. Доступны следующие параметры:

      - **Android**
      - **Android для бизнеса** > **Только владелец устройства**
      - **Android для бизнеса** > **Только рабочий профиль**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 и более поздние версии**
      - **Windows 10 и более поздних версий**.

    - **Тип профиля**. Выберите **VPN**.

3. Доступные для настройки параметры различаются в зависимости от выбранной платформы. Дополнительные сведения о параметрах для каждой платформы см. по ссылкам ниже.

    - [Параметры Android](vpn-settings-android.md)
    - [Параметры Android Enterprise](vpn-settings-android-enterprise.md)
    - [Параметры iOS/iPadOS](vpn-settings-ios.md)
    - [Параметры macOS](vpn-settings-macos.md)
    - [Параметры Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Параметры Windows 8.1](vpn-settings-windows-8-1.md)
    - [Параметры Windows 10](vpn-settings-windows-10.md) (включая Windows Holographic for Business)

4. Закончив, нажмите кнопку **Создать**, чтобы создать профиль.

Созданный профиль отобразится в списке профилей. Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройств](device-profile-assign.md).

## <a name="secure-your-vpn-profiles"></a>Защита профилей VPN

Профили VPN могут использовать несколько разных типов и протоколов подключения от разных поставщиков. Эти подключения обычно защищаются с помощью следующих методов.

### <a name="certificates"></a>Сертификаты

При создании профиля VPN вы выбираете профиль сертификата SCEP или PKCS, созданный ранее в Intune. Этот профиль называется сертификатом удостоверения. Он используется для проверки подлинности по профилю доверенного сертификата (или *корневого сертификата*), созданного, чтобы разрешить подключение устройства пользователя. Доверенный сертификат назначается компьютеру, выполняющему проверку подлинности VPN-подключения, как правило VPN-сервера.

Дополнительные сведения о способах создания и использования профилей сертификатов см. в статье [о настройке сертификатов с помощью Microsoft Intune](../protect/certificates-configure.md).

### <a name="user-name-and-password"></a>Имя пользователя и пароль.

Пользователь проходит проверку на VPN-сервере, предоставляя свои имя пользователя и пароль.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но он пока ничего не делает. Далее нужно [назначить профиль](device-profile-assign.md) для устройств.

Кроме того, вы можете создавать и использовать VPN для каждого приложения на устройствах [Android](android-pulse-secure-per-app-vpn.md) и [iOS](vpn-setting-configure-per-app.md).
