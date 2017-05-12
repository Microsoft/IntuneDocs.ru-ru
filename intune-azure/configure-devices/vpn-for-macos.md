---
title: "Параметры VPN Intune для устройств macOS | Документация Майкрософт"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: узнайте о параметрах Intune, которые можно использовать для настройки VPN-подключений на устройствах macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 76fdf944a21a7dfcd300ef71d12954e4f61831f5
ms.contentlocale: ru-ru
ms.lasthandoff: 05/05/2017


---

# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Параметры VPN для устройств macOS в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

В зависимости от выбранных параметров не все приведенные в следующем списке значения будут доступны для настройки.

## <a name="base-vpn-settings"></a>**Основные параметры VPN**

**Имя подключения**. Введите имя подключения. Конечные пользователи увидят это имя при поиске устройства в списке доступных VPN-подключений.
- **IP-адрес или полное доменное имя**. Укажите IP-адрес или полное доменное имя VPN-сервера, к которому будут подключаться устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.
- **Способ проверки подлинности.** Укажите, как устройства будут проходить проверку подлинности на VPN-сервере.
    - **Сертификаты.** В разделе **Сертификат проверки подлинности** выберите профиль сертификата SCEP или PKCS, созданный ранее для проверки подлинности подключения. Дополнительные сведения о профилях сертификатов см. в статье о [настройке сертификатов с помощью Microsoft Intune](how-to-configure-certificates.md).
    - **Имя пользователя и пароль**. Конечным пользователям необходимо ввести имя пользователя и пароль для входа на VPN-сервер.
- **Тип подключения**. Выберите тип VPN-подключения в следующем списке поставщиков:
    - **Check Point Capsule VPN**;
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **пользовательская сеть VPN**.
- **Разделить туннелирование** - **Включите** или **отключите** этот параметр, позволяющий устройствам выбрать нужное подключение в зависимости от трафика. Например, пользователь в отеле будет использовать VPN-подключение для доступа к рабочим файлам, а стандартную сеть отеля — для обычного просмотра веб-страниц.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../manage-apps/deploy-apps.md). --->

## <a name="custom-vpn-settings"></a>Пользовательские параметры VPN

Если вы выбрали **пользовательскую сеть VPN**, настройте эти дополнительные параметры.

- **Идентификатор VPN.** Это идентификатор для используемого приложения VPN. Его предоставляет поставщик VPN.
- **Enter key and value pairs for the custom VPN attributes** (Введите пары "ключ-значение" для пользовательских атрибутов VPN). Добавьте или импортируйте **ключи** и **значения**, позволяющие настроить VPN-подключение. Эти значения обычно также предоставляет поставщик VPN.


## <a name="proxy-settings"></a>Параметры прокси-сервера

- **Скрипт автоматической настройки**. Используйте файл для настройки прокси-сервера. Введите **URL-адрес прокси-сервера** (например, **http://proxy.contoso.com**), который содержит файл конфигурации.
- **Адрес**. Введите адрес прокси-сервера (в формате IP-адреса).
- **Номер порта.** Введите номер порта, связанного с прокси-сервером.

