---
title: Настройка параметров VPN для устройств с Windows 8.1 в Microsoft Intune — Azure | Документация Майкрософт
description: Добавьте или создайте профиль конфигурации VPN, используя параметры конфигурации виртуальной частной сети (VPN), включая сведения о подключении, и параметры прокси-сервера для включения IP-адреса или полного доменного имени, а также порт TCP в Microsoft Intune на устройствах под Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f9a1399d5474d79ac8fd48a8aa3a844f20eb640
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207049"
---
# <a name="add-vpn-settings-on-windows-81-devices-in-microsoft-intune"></a>Добавление параметров VPN для устройств с ОС Windows 8.1 в Microsoft Intune



Сведения о параметрах Intune, используемых для настройки VPN-подключений на устройствах Windows 8.1.

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>Основные параметры VPN

- **Применить все параметры только к Windows 8.1**: Настройте этот параметр на классическом портале Intune. Этот параметр нельзя изменить в центре администрирования Microsoft Endpoint Manager. Если задано значение **Настроено**, все параметры применяются только к устройствам с Windows 8.1. Если задано значение **Не настроено**, эти параметры применяются также к устройствам с Windows 10.
- **Имя подключения**. Введите имя подключения. Пользователи видят это имя при поиске устройства в списке доступных VPN-подключений.
- **Серверы**: Добавьте VPN-серверы, к которым подключаются устройства.
  - **Добавить**. Открывает страницу **Добавить строку**, в которой можно указать перечисленные ниже сведения.
    - **Описание**. Укажите описательное имя сервера, например **VPN-сервер Contoso**.
    - **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому будут подключаться устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
    - **Сервер по умолчанию**. Позволяет использовать данный сервер как сервер по умолчанию, который устройства используют для подключения. Обязательно установите только один сервер в качестве сервера по умолчанию.
  - **Импорт**. Укажите файл с разделителями-запятыми, который содержит список серверов в следующем формате: описание, IP-адрес или полное доменное имя, сервер по умолчанию. Щелкните **ОК**, чтобы импортировать эти серверы в список **Серверы**.
  - **Экспортировать**. Экспортирует список серверов в файл данных с разделителями-запятыми (CSV).

- **Тип подключения**. Выберите тип VPN-подключения из этого списка поставщиков:
  - **Check Point Capsule VPN**;
  - **SonicWall Mobile Connect**;
  - **F5 Edge Client**
  - **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only): Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Группа входа или домен (только для SonicWall Mobile Connect)** . Укажите имя группы входа или домен, к которому следует подключиться.

- **Роль** (только Pulse Secure). Укажите имя роли пользователя, имеющего доступ к этому подключению. Роль пользователя определяет личные настройки и параметры, а также включает или отключает определенные функции доступа.

- **Область (только Pulse Secure)** . Укажите имя области проверки подлинности, которую следует использовать. Область аутентификации — это группа ресурсов аутентификации, которая используется типом подключения Pulse Secure.

- **Настраиваемый XML**. Укажите пользовательские команды XML, настраивающие VPN-подключение.

  **Пример для Pulse Secure**.

  ```xml
  <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
  ```

  **Пример для CheckPoint Mobile VPN**.

  ```xml
  <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
  ```

  **Пример для SonicWall Mobile Connect**.

  ```xml
  <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
  ```

  **Пример для F5 Edge Client**.

  ```xml
  <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
  ```

  Дополнительные сведения о написании пользовательских команд XML см. в документации по VPN каждого производителя.

## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Автоматически определять параметры прокси-сервера**. Если VPN-серверу требуется прокси-сервер для подключения, укажите, следует ли устройствам автоматически определять параметры подключения.
- **Сценарий автоматической настройки**. Для настройки прокси-сервера будет использоваться файл. Введите **URL-адрес прокси-сервера**, содержащий файл конфигурации. Например, введите `http://proxy.contoso.com`.
- **Использовать прокси-сервер**. Включите этот параметр, если требуется ввести параметры прокси-сервера вручную.
  - **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
  - **Номер порта**. Введите номер порта, связанного с прокси-сервером.
- **Не использовать прокси-сервер для локальных адресов**. Если VPN-серверу требуется прокси-сервер для подключения, выберите этот параметр, если вы не хотите использовать прокси-сервер для указанных локальных адресов.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но он пока ничего не делает. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Настройте параметры VPN на устройствах [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md)и [Windows 10](vpn-settings-windows-10.md) .
