---
title: "Параметры VPN Intune для устройств macOS"
titlesuffix: Azure portal
description: "Узнайте о параметрах Intune, которые можно использовать для настройки VPN-подключений на устройствах macOS.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ec712abe220ca6b020c5d015dc55f0d956cd860
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Параметры VPN для устройств macOS в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>**Основные параметры VPN**

**Имя подключения.** Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений.
- **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому будут подключаться устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
- **Способ проверки подлинности.** Укажите, как устройства будут проходить проверку подлинности на VPN-сервере.
    - **Сертификаты.** В разделе **Сертификат проверки подлинности** выберите профиль сертификата SCEP или PKCS, созданный ранее для проверки подлинности подключения. Дополнительные сведения о профилях сертификатов см. в статье о [настройке сертификатов с помощью Microsoft Intune](certificates-configure.md).
    - **Имя пользователя и пароль**. Конечным пользователям необходимо ввести имя пользователя и пароль для входа на VPN-сервер.
- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
    - **Check Point Capsule VPN**;
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **пользовательская сеть VPN**.
- **Разделить туннелирование** - **Включите** или **отключите** этот параметр, позволяющий устройствам выбрать нужное подключение в зависимости от трафика. Например, пользователь в отеле будет использовать VPN-подключение для доступа к рабочим файлам, а стандартную сеть отеля — для обычного просмотра веб-страниц.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Пользовательские параметры VPN

Если вы выбрали **пользовательскую сеть VPN**, настройте эти дополнительные параметры.

- **Идентификатор VPN.** Это идентификатор для используемого приложения VPN. Его предоставляет поставщик VPN.
- **Enter key and value pairs for the custom VPN attributes** (Введите пары "ключ-значение" для пользовательских атрибутов VPN). Добавьте или импортируйте **ключи** и **значения**, позволяющие настроить VPN-подключение. Эти значения обычно также предоставляет поставщик VPN.


## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Скрипт автоматической настройки**. Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера** (например, **http://proxy.contoso.com**), который содержит файл конфигурации.
- **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
- **Номер порта.** Введите номер порта, связанного с прокси-сервером.
