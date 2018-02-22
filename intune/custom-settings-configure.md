---
title: "Настройка пользовательских параметров устройств в Intune"
titleSuffix: Azure portal
description: "Узнайте, как с помощью Intune можно настроить пользовательские параметры на управляемых устройствах.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cafcf95cc9025872ce0fbb9605c9d820aa7a19c0
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Настройка пользовательских параметров устройств в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Когда следует использовать пользовательские параметры

Пользовательские параметры устройства могут понадобиться, если среди встроенных параметров в Intune нет тех, которые вы хотите настроить, и они не доступны в других профилях устройства.
Пользовательские параметры настраиваются по-разному для каждой платформы. Например, на устройствах Android и Windows можно указать значения Open Mobile Alliance Uniform Resource Identifier (OMA-URI), чтобы управлять функциями на этих устройствах. На устройства Apple можно импортировать файл, созданный с помощью [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Эта статья содержит базовые сведения о настройке профилей с пользовательскими параметрами, а также ссылки на статьи со сведениями об особенностях устройств, работающих под управлением разных платформ.

## <a name="create-a-device-profile-containing-custom-settings"></a>Создание профиля устройства, содержащего пользовательские параметры

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите пункт **Конфигурация устройства**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создание профиля**.
4. В колонке **Создание профиля** введите **имя** и **описание** для пользовательского профиля.
5. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить настроенные параметры. Сейчас для пользовательских параметров устройства можно выбрать одну из следующих платформ:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 и более поздних версий**.
6. В раскрывающемся списке **Профиль** выберите **Пользовательский**.
7. Доступные для настройки параметры различаются в зависимости от выбранной платформы. Дополнительные сведения о параметрах для каждой платформы см. по ссылкам ниже.
    - [Параметры Android](custom-settings-android.md)
    - [Параметры iOS](custom-settings-ios.md)
    - [Параметры macOS](custom-settings-macos.md)
    - [Параметры Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Параметры Windows 10](custom-settings-windows-10.md)
    - [Параметры Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Параметры Android for Work](custom-settings-android-for-work.md)
8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](device-profile-assign.md).
