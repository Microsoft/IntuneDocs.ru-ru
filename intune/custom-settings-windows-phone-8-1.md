---
title: "Пользовательские параметры Intune для устройств с Windows Phone 8.1"
titleSuffix: Azure portal
description: "Параметры, которые можно использовать в настраиваемом профиле Windows Phone 8.1.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 566037e507e6344187acb6528b2db86a82e28937
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Настраиваемые параметры для устройств Windows Phone 8.1 в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Используйте в Microsoft Intune **настраиваемый профиль** Windows Phone 8.1 для назначения параметров OMA-URI, с помощью которых можно управлять функциями на устройствах Windows Phone 8.1. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет назначать параметры, которые нельзя настроить с помощью других политик Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Параметры настраиваемой политики для устройств Windows Phone 8.1

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Добавить строку** укажите для каждого параметра следующие значения:
    - **Имя**. Введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание**. Укажите в описании общие сведения о параметре и актуальную информацию о его расположении.
    - **OMA-URI**. Укажите OMA-URI, для которого необходимо указать параметр.
    - **Тип данных**. Выберите тип данных, в котором следует указать этот параметр OMA-URI. Можно выбрать один из таких типов: **Строка**, **Дата и время**, **Целое число**, **Число с плавающей запятой** или **Логическое значение**.
    - **Значение.** Введите значение, которое нужно сопоставить с указанным OMA-URI.

4. Завершив настройку, нажмите кнопку **ОК**. Затем добавьте другие параметры при необходимости.
