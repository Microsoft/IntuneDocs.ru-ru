---
title: "Параметры VPN Intune для устройств Windows 8.1 | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте о параметрах Intune, которые можно использовать для настройки VPN-подключений на устройствах Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 21ed25c1c0afd2c3fa45c15d4aa40d9c8d57b35a
ms.lasthandoff: 02/16/2017


---

# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a>Параметры VPN для устройств с ОС Windows 8.1 в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>Основные параметры VPN


- **Apply all settings to Windows 8.1 only** (Применение всех параметров только к устройствам с Windows 8.1). Этот параметр можно настроить на классическом портале Intune. На портале Azure этот параметр изменить невозможно. Если задано значение **Настроено**, все параметры будут применяться только к устройствам Windows 8.1. Если выбрать значение **Не настроено**, эти параметры будут также применены к устройствам Windows 10.
- **Имя подключения.** Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений.
- **Серверы.** Добавьте один или несколько VPN-серверов, к которым будут подключаться устройства.
    - **Добавить**. Открывает колонку **Добавить строку**, в которой можно указать перечисленные ниже сведения:
        - **Описание**. Укажите описательное имя сервера, например **VPN-сервер Contoso**.
        - **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому будут подключаться устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
        - **Сервер по умолчанию**. Позволяет использовать данный сервер как сервер по умолчанию, который устройства будут использовать для установки подключения. Обязательно установите только один сервер в качестве сервера по умолчанию.
    - **Импорт.** Найдите файл, содержащий список серверов с разделителями-запятыми, в описании формата, IP-адресе или полном доменном имени и на сервере по умолчанию. Щелкните **ОК**, чтобы импортировать эти параметры в список **Серверы**.
    - **Экспорт.** Экспортирует список серверов в файл данных с разделителями-запятыми (CSV).

- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
- **Check Point Capsule VPN**;
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Домен или группа входа** (только для Dell SonicWALL Mobile Connect). Укажите имя группы входа или домена, к которым следует подключиться.

- **Роль** (только Pulse Secure). Укажите имя роли пользователя, имеющего доступ к этому подключению. Роль пользователя определяет личные настройки и параметры, а также включает или отключает определенные функции доступа.

- **Область** (только Pulse Secure). Укажите имя области проверки подлинности, которую следует использовать. Область аутентификации — это группа ресурсов аутентификации, которая используется типом подключения Pulse Secure.


- **Настраиваемый XML**. Укажите любые пользовательские команды XML, настраивающие VPN-подключение.

**Пример для Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Пример для CheckPoint Mobile VPN:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

**Пример для Dell SonicWALL Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Пример для F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Дополнительные сведения о создании пользовательских команд XML см. в документации VPN каждого производителя.


## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Автоматическое определение параметров прокси-сервера.** Если VPN-серверу требуется прокси-сервер для подключения, укажите, следует ли устройствам автоматически определять параметры подключения. Дополнительные сведения см. в документации по Windows Server.
- **Скрипт автоматической настройки.** Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера** (например, **http://proxy.contoso.com**), который содержит файл конфигурации.
- **Использовать прокси-сервер**. Включите этот параметр, если требуется ввести параметры прокси-сервера вручную.
    - **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
    - **Номер порта.** Введите номер порта, связанного с прокси-сервером.
- **Обходить прокси-сервер для локальных адресов.** Если VPN-серверу требуется прокси-сервер для подключения, выберите этот параметр, если вы не хотите использовать прокси-сервер для указанных локальных адресов. Дополнительные сведения см. в документации по Windows Server.

