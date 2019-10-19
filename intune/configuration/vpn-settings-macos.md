---
title: Настройка параметров VPN для устройств macOS в Microsoft Intune в Azure | Документация Майкрософт
description: Добавьте или создайте профиль конфигурации виртуальной частной сети (VPN), включая сведения о подключении, разделите туннелирование, настраиваемые параметры VPN с идентификатором, парой "ключ — значение", параметрами прокси-сервера с помощью скрипта конфигурации, IP-адреса или полного доменного имени и порта TCP в Microsoft Intune на устройствах под macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 044b35b34a9a5b01537e82dcfddca74a284ebdcc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72491008"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Добавление параметров VPN на устройства macOS в Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Сведения о параметрах Intune, используемых для настройки VPN-подключений на устройствах macOS.

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="before-you-begin"></a>Подготовка к работе

[Создайте профиль конфигурации устройства](vpn-settings-configure.md).

> [!NOTE]
> Эти параметры доступны для всех типов регистрации. Дополнительные сведения о типах регистрации см. в разделе [macOS регистрация](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Основные параметры VPN

**Имя подключения**. Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений.
- **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому подключаются устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
- **Метод проверки подлинности**. Укажите, как устройства будут проходить проверку подлинности на VPN-сервере.
  - **Сертификаты**. В разделе **Сертификат проверки подлинности** выберите профиль сертификата SCEP или PKCS, созданный ранее для проверки подлинности подключения. Дополнительные сведения о профилях сертификатов см. в статье о [настройке сертификатов](../protect/certificates-configure.md).
  - **Имя пользователя и пароль**. Пользователям необходимо ввести имя пользователя и пароль для входа на VPN-сервер.
- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
  - **Check Point Capsule VPN**;
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**;
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Пользовательская сеть VPN**.
- **Раздельное туннелирование**. Выберите **Включить** или **Отключить** этот параметр, чтобы позволить устройствам выбрать нужное подключение в зависимости от трафика. Например, пользователь в отеле использует VPN-подключение для доступа к рабочим файлам, а стандартную сеть отеля — для обычного просмотра веб-страниц.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Пользовательские параметры VPN

Если вы выбрали **пользовательскую сеть VPN**, настройте эти дополнительные параметры.

- **Идентификатор VPN**. Введите идентификатор для приложения VPN, которое вы используете. Этот идентификатор предоставляется поставщиком услуг VPN.
- **Enter key and value pairs for the custom VPN attributes** (Введите пары "ключ-значение" для пользовательских атрибутов VPN). Добавьте или импортируйте **ключи** и **значения**, позволяющие настроить VPN-подключение. Эти значения обычно также предоставляет поставщик VPN.

## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Скрипт автоматической настройки.** Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера**, содержащий файл конфигурации. Например, введите `http://proxy.contoso.com`.
- **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса)
- **Номер порта**. Введите номер порта, связанного с прокси-сервером.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но он пока ничего не делает. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Настройка параметров VPN на устройствах [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [iOS](vpn-settings-ios.md)и [Windows 10](vpn-settings-windows-10.md) .
