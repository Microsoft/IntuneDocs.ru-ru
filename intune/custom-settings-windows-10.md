---
title: "Пользовательские параметры для устройств с Windows 10 в Intune"
titleSuffix: Intune on Azure
description: "Параметры, которые можно использовать в настраиваемом профиле Windows 10.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bda9e939e2d4aba4c4d005ea55ba65bec9c6e217
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Настраиваемые параметры устройств с ОС Windows 10 в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Используйте **настраиваемый** профиль Microsoft Intune для Windows 10 и Windows 10 Mobile, чтобы развернуть параметры OMA-URI (универсальный код ресурса Open Mobile Alliance), с помощью которых можно управлять функциями устройств. В ОС Windows 10 становятся доступными многие параметры CSP, например [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Поставщик службы конфигурации (CSP) политик).
Если вам нужен какой-то конкретный параметр, не забывайте, что [профиль ограничения устройств с Windows 10](device-restrictions-windows-10.md) содержит множество параметров, которые встроены в Intune и не требуют указания пользовательских значений.

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

## <a name="example"></a>Пример
На снимке экрана ниже параметр **Connectivity/AllowVPNOverCellular** был включен. Это позволяет устройству с Windows 10 открыть VPN-подключение по сети мобильной связи.

> ![Пример настраиваемой политики, содержащий параметры VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Как найти настраиваемые политики

Полный список всех поставщиков служб конфигурации (CSP), поддерживаемых ОС Windows 10, можно найти в [справочнике поставщиков служб конфигурации](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) в библиотеке документации Windows.

Не все параметры совместимы со всеми версиями ОС Windows 10. Таблица в разделе Windows содержит сведения о том, какие версии поддерживаются для каждого поставщика служб конфигурации (CSP).

Кроме того, Intune поддерживает не все параметры, перечисленные в этом разделе. Чтобы узнать, поддерживает ли Intune необходимый параметр, откройте соответствующий раздел для этого параметра. На странице каждого параметра отображаются сведения о поддерживаемых операциях. Для работы с Intune параметр должен поддерживать операции **добавления** или **замены**.


