---
title: "Пользовательские параметры Intune для устройств с Windows Holographic for Business"
titlesuffix: Azure portal
description: "Сведения о параметрах, которые можно использовать в пользовательском профиле Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Пользовательские параметры устройств с Windows Holographic for Business в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Пользовательский** профиль Microsoft Intune для Windows Holographic for Business позволяет развертывать параметры универсального кода ресурса Open Mobile Alliance (OMA-URI) для управления функциями устройств. Windows Holographic for Business открывает доступ ко множеству параметров поставщиков служб конфигурации (CSP). Обзор CSP см. в разделе [Введение в поставщики служб конфигурации (CSP) для ИТ-специалистов](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Также см. [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Если вам нужен какой-то конкретный параметр, не забывайте, что [профиль ограничения устройств с Windows Holographic for Business](device-restrictions-windows-holographic.md) содержит множество встроенных параметров и не требует указывать ваши собственные значения.

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Настраиваемые параметры OMA URI** выберите **Добавить**, чтобы добавить новое значение. Можно также щелкнуть **Экспорт**, чтобы создать список всех настроенных значений в файле с разделителями-запятыми (CSV).
4. Для каждого добавляемого параметра OMA-URI введите указанные ниже сведения. Сведения о параметрах, которые можно использовать, см. в списке ниже.
    - **Имя параметра** — введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание параметра** — введите необязательное описание параметра.
    - **Тип данных** — выберите одно из значений:
        - **Строка**
        - **Строка (XML)**
        - **Дата и время**
        - **Целое число**
        - **Число с плавающей запятой**
        - **Логическое значение**
    - **OMA-URI (с учетом регистра)** — задайте OMA-URI, для которого необходимо указать параметр.
    - **Значение** — укажите значение, которое требуется сопоставить с заданным OMA-URI.
5. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.
Созданный профиль отобразится в колонке со списком профилей.

## <a name="supported-custom-settings"></a>Поддерживаемые пользовательские параметры

Windows Holographic for Business поддерживает следующие пользовательские параметры:


|Имя параметра|OMA-URI|Тип данных  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Целое число (0 — не допускается, 1 — допускается)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Целое число (0 — не допускается, 1 — допускается)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Как найти настраиваемые политики

Полный список поставщиков служб конфигурации (CSP), поддерживаемых Windows Holographic, приведен в разделе [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Некоторые параметры не совместимы с некоторыми версиями Windows Holographic. Таблица в разделе Windows содержит сведения о том, какие версии поддерживаются для каждого поставщика служб конфигурации (CSP).

Кроме того, Intune поддерживает не все параметры, перечисленные в этом разделе. Чтобы узнать, поддерживает ли Intune необходимый параметр, откройте соответствующий раздел для этого параметра. На странице каждого параметра отображаются сведения о поддерживаемых операциях. Для работы с Intune параметр должен поддерживать операции **добавления** или **замены**.


