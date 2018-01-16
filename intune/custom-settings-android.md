---
title: "Пользовательские параметры для устройств Android в Intune"
titleSuffix: Azure portal
description: "Узнайте, какие параметры можно использовать в настраиваемом профиле Android.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b1ccb3b0b7b2ce024ff6a09d7f9d8366896fb67
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Настраиваемые параметры для устройств Android в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Используйте **настраиваемый** профиль Microsoft Intune для назначения параметров OMA-URI, которые можно использовать для управления функциями на устройствах Android. Это стандартные параметры, которые многие производители мобильных устройств используют для управления функциями устройств.

Эта возможность позволяет назначать приведенные далее параметры Android, которые невозможно настроить с помощью политик Intune.

- [Использование пользовательского профиля устройств Microsoft Intune для создания профиля Wi-Fi с общим ключом](/intune/wi-fi-profile-shared-key)
- [Использование пользовательского профиля Microsoft Intune с целью создания профиля VPN для каждого приложения на устройствах Android](/intune/android-pulse-secure-per-app-vpn)
- [Использование настраиваемых политик для разрешения и блокировки приложений для устройств Samsung Knox Standard в Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Сейчас с помощью этого типа профиля можно настроить только приведенные выше параметры. На устройствах Android не выводится полный список параметров OMA-URI, которые можно настроить. Чтобы просмотреть дополнительные добавленные параметры, запросите их на [сайте Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Настраиваемые параметры профиля для устройств Android

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создание профиля** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Изменить строку** укажите следующие значения для каждого параметра.
    - **Имя.** Введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание.** Укажите в описании общие сведения о параметре и актуальную информацию о его расположении.
    - **Тип данных.** Выберите тип данных, в котором следует указать этот параметр OMA-URI. Выберите **Строка**, **Строка (XML)**, **Дата и время**, **Целое число**, **Число с плавающей запятой** или **Логическое значение**.
    - **OMA-URI.** Укажите OMA-URI, для которого необходимо указать параметр.
    - **Значение.** Введите значение, которое нужно сопоставить с указанным OMA-URI.
4. Завершив настройку, нажмите кнопку **ОК**. Затем добавьте другие параметры при необходимости.

## <a name="next-steps"></a>Дальнейшие шаги

После установки параметров созданный профиль отобразится в колонке со списком профилей. Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).




