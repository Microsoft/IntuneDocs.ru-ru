---
title: Использование параметров VPN для устройств Android в Microsoft Intune в Azure | Документация Майкрософт
description: Просмотрите все параметры для создания VPN-подключений на устройствах Android в Microsoft Intune. Введите имя подключения, IP-адрес или полное доменное имя VPN-сервера, выберите способ проверки подлинности пользователей и выберите Citrix, SonicWall, Check Point капсула и типы подключения Pulse Secure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f9945198f8ed575b26762c1f8f356885d5b9dc5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734184"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Параметры устройства Android для настройки VPN в Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

В этой статье перечислены и описаны различные параметры VPN-подключения, которыми можно управлять на устройствах Android. В рамках решения по управлению мобильными устройствами (MDM) Используйте эти параметры для создания VPN-подключения, выбора способа проверки подлинности VPN, выбора типа VPN-сервера и т. д.

Администратор Intune может создавать и назначать параметры VPN устройствам Android. 

Дополнительные сведения о профилях VPN в Intune см. в статье [Профили VPN](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Подготовка к работе

[Создайте профиль конфигурации устройства](vpn-settings-configure.md#create-a-device-profile) и выберите **Android**.

## <a name="base-vpn"></a>Базовая VPN

- **Имя подключения**. Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений. Например, введите `Contoso VPN`.
- **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому подключаются устройства. Например, введите **192.168.1.1** или **vpn.contoso.com**.

  - **Метод проверки подлинности**. Укажите, как устройства будут проходить проверку подлинности на VPN-сервере. Доступны следующие параметры:

    - **Сертификаты**. Выберите существующий профиль сертификата SCEP или PKCS для проверки подлинности подключения. В разделе [Настройка сертификатов](../protect/certificates-configure.md) перечислены шаги для создания профиля сертификата.
    - **Имя пользователя и пароль**. При входе на VPN-сервер пользователям будет предложено ввести имя пользователя и пароль.

- **Тип подключения**. Выберите тип подключения VPN. Доступны следующие параметры:

  - **Check Point Capsule VPN**;
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**;
  - **F5 Access**
  - **Pulse Secure**
  - **Citrix SSO**

- **Отпечаток** (только Check Point Capsule VPN). Укажите строку (например, **Contoso Fingerprint Code**), которая будет использоваться для проверки надежности VPN-сервера. Клиенту отправляется отпечаток пальца, чтобы клиент мог доверять любому серверу, имеющему тот же отпечаток. Если на устройстве еще нет отпечатка, пользователь получит запрос на доверие к VPN-серверу с отображением отпечатка. Пользователь должен вручную проверить отпечаток и нажать кнопку "Доверять" для подключения.
- **Введите пары "ключ-значение" для атрибутов Citrix VPN** (только Citrix): введите пары "ключ-значение", предоставленные Citrix. Эти значения настраивают свойства VPN-подключения. 

  Также можно **импортировать** файл значений с разделителями-запятыми (CSV) с парами ключей и значений. Обязательно ознакомьтесь с **разделом** **Мои данные с заголовками** и ключевыми свойствами.

  После добавления пар ключей и значений используйте **Export** для резервного копирования данных в CSV-файл.

## <a name="next-steps"></a>Дальнейшие шаги

[Назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Вы также можете создавать профили VPN для устройств [Android Enterprise](vpn-settings-android-enterprise.md), [iOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 и более поздних версий](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md)и [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) .
