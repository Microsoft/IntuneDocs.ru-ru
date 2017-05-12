---
title: "Пользовательские параметры Intune для устройств с Windows Phone 8.1"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, какие параметры можно использовать в настраиваемом профиле Windows Phone 8.1."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 9bc814899ff59aaadeda2172f9ac609275f929e2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/05/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Настраиваемые параметры для устройств Windows Phone 8.1 в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Используйте в Microsoft Intune **настраиваемый профиль** Windows Phone 8.1 для назначения параметров OMA-URI, с помощью которых можно управлять функциями на устройствах Windows Phone 8.1. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет назначать параметры, которые нельзя настроить с помощью других политик Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Параметры настраиваемой политики для устройств Windows Phone 8.1

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Добавить строку** укажите для каждого параметра следующие значения:
    - **Имя**. Введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание**. Укажите в описании общие сведения о параметре и актуальную информацию о его расположении.
    - **OMA-URI**. Укажите OMA-URI, для которого необходимо указать параметр.
    - **Тип данных**. Выберите тип данных, в котором следует указать этот параметр OMA-URI. Можно выбрать один из таких типов: **Строка**, **Дата и время**, **Целое число**, **Число с плавающей запятой** или **Логическое значение**.
    - **Значение.** Введите значение, которое нужно сопоставить с указанным OMA-URI.

4. Завершив настройку, нажмите кнопку **ОК**. Затем добавьте другие параметры при необходимости.

