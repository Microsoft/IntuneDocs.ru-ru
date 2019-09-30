---
title: Использование настраиваемых параметров устройств в Microsoft Intune — Azure | Документы Майкрософт
description: Добавьте или создайте профиль, чтобы использовать настраиваемые параметры для устройств Windows Phone, Windows 8.1, Windows 10 и более поздних версий, Android, Android для бизнеса, macOS и iOS с помощью Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 854e8fc7a46f431ce36c4e30682c196e6484b93e
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163113"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Создайте профиль с настраиваемыми параметрами в Intune

## <a name="what-are-custom-profiles"></a>Что такое настраиваемые профили

Microsoft Intune включает множество встроенных параметров для управления различными функциями на устройстве. Также можно создавать настраиваемые профили. Они очень удобны, когда нужно использовать параметры и функции устройств, которые не встроены в Intune. Эти профили включают в себя функции и параметры, которыми вы можете управлять на устройствах в своей организации. Например, можно создать настраиваемый профиль, который задает одну и ту же функцию для каждого устройства iOS.

Дополнительные сведения о профилях конфигурации см. в разделе [Что такое профили устройств в Microsoft Intune?](device-profiles.md). 

Эта статья содержит ссылки для создания настраиваемых профилей для Android, Android Enterprise, iOS, macOS и Windows.

## <a name="available-platforms"></a>Доступные платформы

Пользовательские параметры настраиваются по-разному для каждой платформы. Например, для управления функциями на устройствах Android и Windows можно указать значения универсального кода ресурсов Open Mobile Alliance (OMA-URI). На устройства Apple можно импортировать файл, созданный с помощью [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) или [Apple Profile Manager](https://support.apple.com/profile-manager).

Настраиваемые профили создаются аналогично встроенным профилям и доступны на следующих платформах.

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Дальнейшие шаги

Выберите платформу и приступайте к работе.

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
