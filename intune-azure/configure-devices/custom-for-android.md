---
title: "Настраиваемые параметры Intune для устройств Android | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure. Узнайте, какие параметры можно использовать в настраиваемом профиле Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3a80a69a27b540b66fb96e098c0b0f66a0854297


---

# <a name="custom-settings-for-android-devices-in-intune-azure-preview"></a>Настраиваемые параметры Intune для устройств Android в предварительной версии Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Используйте **настраиваемый** профиль Microsoft Intune для развертывания параметров OMA-URI, которые можно использовать для управления функциями на устройствах Android. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет развертывать параметры Android, которые нельзя настроить с помощью политик Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Настраиваемые параметры профиля для устройств Android

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Изменить строку** укажите следующие значения для каждого параметра.
    - **Имя.** Введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание.** Укажите в описании общие сведения о параметре и актуальную информацию о его расположении.
    - **Тип данных.** Выберите тип данных, в котором следует указать этот параметр OMA-URI. Выберите **Строка**, **Строка (XML)**, **Дата и время**, **Целое число**, **Число с плавающей запятой** или **Логическое значение**.
    - **OMA-URI.** Укажите OMA-URI, для которого необходимо указать параметр.
    - **Значение.** Введите значение, которое нужно сопоставить с указанным OMA-URI.
4. Завершив настройку, нажмите кнопку **ОК**. Затем добавьте другие параметры при необходимости.



<!--HONumber=Feb17_HO1-->


