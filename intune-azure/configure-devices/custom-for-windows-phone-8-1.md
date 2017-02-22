---
title: "Настраиваемые параметры Intune для устройств Windows Phone 8.1 | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте, какие параметры можно использовать в настраиваемом профиле Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3656db2d9828dcc16c479ba072de691848fdd23b


---

# <a name="custom-settings-for-windows-phone-81-devices-in-intune-azure-preview"></a>Настраиваемые параметры для устройств Windows Phone 8.1 в предварительной версии Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Используйте в Microsoft Intune **настраиваемый профиль** Windows Phone 8.1 для развертывания параметров OMA-URI, с помощью которых можно управлять функциями на устройствах Windows Phone 8.1. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет развертывать параметры, которые нельзя настроить с помощью других политик Intune.

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



<!--HONumber=Feb17_HO1-->


