---
title: Настраиваемые параметры Microsoft Intune для устройств под управлением Windows Phone 8.1
titleSuffix: ''
description: Параметры, которые можно использовать в настраиваемом профиле Windows Phone 8.1.
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
ms.openlocfilehash: b21464016dff3396b25861af568fa90d8b7a260f
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Настраиваемые параметры Microsoft Intune для устройств под управлением Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Используйте в Microsoft Intune **настраиваемый профиль** Windows Phone 8.1 для назначения параметров OMA-URI, с помощью которых можно управлять функциями на устройствах Windows Phone 8.1. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет назначать параметры, которые нельзя настроить с помощью других политик Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Параметры настраиваемой политики для устройств Windows Phone 8.1

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. На панели **Настраиваемые параметры OMA-URI** выберите **Добавить**, чтобы добавить один или несколько параметров OMA-URI.
3. На панели **Добавить строку** укажите для каждого параметра следующие значения:
    - **Имя.** Введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание**. Укажите в описании общие сведения о параметре и актуальную информацию о его расположении.
    - **OMA-URI.** Укажите OMA-URI, для которого необходимо указать параметр.
    - **Тип данных.** Выберите тип данных, в котором следует указать этот параметр OMA-URI. Выберите **Строка**, **Строка (XML)**, **Дата и время**, **Целое число**, **Число с плавающей запятой**, **Логическое значение** или **Base64**.
    - **Значение.** Введите значение или файл, который нужно сопоставить с указанным OMA-URI.

4. Завершив настройку, нажмите кнопку **ОК**. Затем добавьте другие параметры при необходимости.
