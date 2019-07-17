---
title: Настройка параметров защиты конечных точек в Microsoft Intune в Azure | Документы Майкрософт
description: Вы можете создать параметры защиты конечных точек при создании профиля устройства macOS или Windows 10 в Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 1a5cd898545bae51395352d5cf1e7b1ee9bd22dd
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883247"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Добавление параметров защиты конечных точек в Intune

С помощью Intune вы можете использовать профили конфигурации устройств для управления общими функциями безопасности для защиты конечных точек на устройствах, в том числе следующими:
- Брандмауэр 
- BitLocker
- разрешение и блокировка приложений;  
- Защитник Windows и шифрование.

Например, можно создать профиль защиты конечной точки, который разрешает пользователям macOS устанавливать приложения только из Mac App Store. Или включать Windows SmartScreen при выполнении приложений на устройствах Windows 10.

Перед созданием профиля ознакомьтесь со следующими статьями, в которых рассматриваются параметры защиты конечных точек, применяемые Intune для каждой поддерживаемой платформы: 
- [Параметры macOS](endpoint-protection-macos.md)
- [Параметры Windows 10](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Создание профиля устройства с параметрами защиты конечных точек

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
4. Введите **имя** и **описание** для профиля защиты конечных точек.
5. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить настроенные параметры. Сейчас для параметров ограничения устройства можно выбрать одну из следующих платформ:
   - **macOS**
   - **Windows 10 и более поздних версий**.
6. В раскрывающемся списке **Тип профиля** выберите **Endpoint Protection**. 
7. Доступные для настройки параметры различаются в зависимости от выбранной платформы. См. раздел
   - [Параметры macOS](endpoint-protection-macos.md)
   - [Параметры Windows 10](endpoint-protection-windows-10.md)  

8. После настройки нужных параметров выберите **Создать** на странице **Создание профиля**.

   Созданный профиль отобразится на странице со списком профилей. Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройств](device-profile-assign.md).


## <a name="next-steps"></a>Дальнейшие шаги  

Сведения о том, как назначить профиль группам, см. в статье о [назначении профилей устройств](device-profile-assign.md).
