---
title: Параметры VPN для устройств Windows 8.1 в Microsoft Intune
titleSuffix: ''
description: Сведения о параметрах Intune, используемых для настройки VPN-подключений на устройствах Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd48b6f75d68f8078eaa01508f01d13e8490da2a
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734119"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Настройка параметров VPN для устройств Windows 8.1 в Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Сведения о параметрах Intune, используемых для настройки VPN-подключений на устройствах Windows 8.1.

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>Основные параметры VPN


- **Apply all settings to Windows 8.1 only** (Применение всех параметров только к устройствам с Windows 8.1). Этот параметр можно настроить на классическом портале Intune. На портале Azure этот параметр изменить невозможно. Если задано значение **Настроено**, все параметры применяются только к устройствам Windows 8.1. Если выбрать значение **Не настроено**, эти параметры также применяются к устройствам Windows 10.
- **Имя подключения.** Введите имя подключения. Пользователи видят это имя при поиске устройства в списке доступных VPN-подключений.
- **Серверы**. Добавьте один или несколько VPN-серверов, к которым подключаются устройства.
  - **Добавить**. Открывает страницу **Добавить строку**, в которой можно указать перечисленные ниже сведения:
    - **Описание**. Укажите описательное имя сервера, например **VPN-сервер Contoso**.
    - **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому подключаются устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
    - **Сервер по умолчанию**. Позволяет использовать данный сервер как сервер по умолчанию, который устройства используют для установки подключения. Обязательно установите только один сервер в качестве сервера по умолчанию.
  - **Импорт**. Найдите файл, содержащий список серверов с указанными через запятую следующими данными: описание, IP-адрес или полное доменное имя, сервер по умолчанию. Щелкните **ОК**, чтобы импортировать эти параметры в список **Серверы**.
  - **Экспорт.** Экспортирует список серверов в файл данных с разделителями-запятыми (CSV).

- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
- **Check Point Capsule VPN**;
- **SonicWall Mobile Connect**;
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Домен или группа входа** (только для SonicWall Mobile Connect). Укажите имя группы входа или домена, к которым следует подключиться.

- **Роль** (только Pulse Secure). Укажите имя роли пользователя, имеющего доступ к этому подключению. Роль пользователя определяет личные настройки и параметры, а также включает или отключает определенные функции доступа.

- **Область** (только Pulse Secure). Укажите имя области проверки подлинности, которую следует использовать. Область аутентификации — это группа ресурсов аутентификации, которая используется типом подключения Pulse Secure.


- **Настраиваемый XML**. Укажите любые пользовательские команды XML, настраивающие VPN-подключение.

**Пример для Pulse Secure:**

```xml
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Пример для CheckPoint Mobile VPN:**

```xml
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Пример для SonicWall Mobile Connect:**

```xml
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Пример для F5 Edge Client:**

```xml
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Дополнительные сведения о создании пользовательских команд XML см. в документации VPN каждого производителя.


## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Автоматическое определение параметров прокси-сервера.** Если VPN-серверу требуется прокси-сервер для подключения, укажите, следует ли устройствам автоматически определять параметры подключения. Дополнительные сведения см. в документации по Windows Server.
- **Скрипт автоматической настройки.** Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера**, содержащий файл конфигурации. Например, введите `http://proxy.contoso.com`.
- **Использовать прокси-сервер**. Включите этот параметр, если требуется ввести параметры прокси-сервера вручную.
  - **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
  - **Номер порта.** Введите номер порта, связанного с прокси-сервером.
- **Обходить прокси-сервер для локальных адресов.** Если VPN-серверу требуется прокси-сервер для подключения, выберите этот параметр, если вы не хотите использовать прокси-сервер для указанных локальных адресов. Дополнительные сведения см. в документации по Windows Server.
