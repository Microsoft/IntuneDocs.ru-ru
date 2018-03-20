---
title: "Использование настраиваемых параметров устройств в Microsoft Intune — Azure | Документы Майкрософт"
description: "Добавьте или создайте профиль, чтобы использовать настраиваемые параметры для устройств Windows, iOS и Android с помощью Microsoft Intune"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: adecb332c91f17cf92362295b6b0c81445f5acaf
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Создайте профиль с настраиваемыми параметрами в Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

В Intune может не быть всех нужных параметров. Или вы захотите использовать параметр, доступный в других профилях устройств. Чтобы добавить эти параметры, создайте профиль устройства и укажите в нем настраиваемые параметры.

В этой статье перечислены основные шаги для создания профиля с настраиваемыми параметрами. Она также содержит ссылки на более подробную информацию о создании настраиваемых параметров на разных платформах.

## <a name="custom-settings-on-different-platforms"></a>Настраиваемые параметры для разных платформ
Пользовательские параметры настраиваются по-разному для каждой платформы. Например, для управления функциями на устройствах Android и Windows можно указать значения универсального кода ресурсов Open Mobile Alliance (OMA-URI). На устройства Apple можно импортировать файл, созданный с помощью [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-the-profile"></a>Создание профиля

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Конфигурация устройства** и нажмите **Профили**, а затем **Создать профиль**.
4. Укажите **имя** и **описание** настраиваемого профиля.
5. В раскрывающемся списке **Платформа** выберите платформу устройства для применения настраиваемых параметров. Выберите любую из следующих платформ:

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 и более поздние версии**
    - **Windows 10 и более поздних версий**.

6. В раскрывающемся списке **Профиль** выберите **Пользовательский**.
7. Доступные для настройки параметры различаются в зависимости от выбранной платформы. В следующих статьях приводятся дополнительные сведения о настраиваемых параметрах для каждой платформы:

    - [Параметры Android](custom-settings-android.md)
    - [Параметры iOS](custom-settings-ios.md)
    - [Параметры macOS](custom-settings-macos.md)
    - [Параметры Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Параметры Windows 10](custom-settings-windows-10.md)
    - [Параметры Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Параметры Android for Work](custom-settings-android-for-work.md)

8. По окончании нажмите **Создать**.

Созданный профиль отобразится в списке профилей. Сведения о том, как назначить этот профиль группам, см. в статье [Назначение профилей устройств](device-profile-assign.md).
