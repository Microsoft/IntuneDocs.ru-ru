---
title: Параметры VPN для устройств macOS в Microsoft Intune
titlesuffix: ''
description: Узнайте о параметрах Intune, которые можно использовать для настройки VPN-подключений на устройствах macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4330d8e8095df49b14ab60c4b08aae44d134452
ms.sourcegitcommit: cac71802b2782700f0d52ea114089d73620cd1ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50679225"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-macos"></a>Настройка параметров VPN для устройств macOS в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Сведения о параметрах Intune, используемых для настройки VPN-подключений на устройствах macOS.

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>Основные параметры VPN

**Имя подключения.** Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений.
- **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому подключаются устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
- **Способ проверки подлинности.** Укажите, как устройства будут проходить проверку подлинности на VPN-сервере.
    - **Сертификаты.** В разделе **Сертификат проверки подлинности** выберите профиль сертификата SCEP или PKCS, созданный ранее для проверки подлинности подключения. Дополнительные сведения о профилях сертификатов см. в статье о [настройке сертификатов с помощью Microsoft Intune](certificates-configure.md).
    - **Имя пользователя и пароль**. Конечным пользователям необходимо ввести имя пользователя и пароль для входа на VPN-сервер.
- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
    - **Check Point Capsule VPN**;
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**;
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Пользовательская сеть VPN**.
- **Разделить туннелирование** - . Выберите **Включить** или **Отключить** этот параметр, позволяющий устройствам выбрать нужное подключение в зависимости от трафика. Например, пользователь в отеле использует VPN-подключение для доступа к рабочим файлам, а стандартную сеть отеля — для обычного просмотра веб-страниц.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Пользовательские параметры VPN

Если вы выбрали **пользовательскую сеть VPN**, настройте эти дополнительные параметры.

- **Идентификатор VPN.** Это идентификатор для используемого приложения VPN. Его предоставляет поставщик VPN.
- **Enter key and value pairs for the custom VPN attributes** (Введите пары "ключ-значение" для пользовательских атрибутов VPN). Добавьте или импортируйте **ключи** и **значения**, позволяющие настроить VPN-подключение. Эти значения обычно также предоставляет поставщик VPN.


## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Скрипт автоматической настройки.** Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера** (например, `** http://proxy.contoso.com**`), на котором находится файл конфигурации.
- **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
- **Номер порта.** Введите номер порта, связанного с прокси-сервером.
