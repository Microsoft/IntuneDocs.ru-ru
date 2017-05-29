---
title: "Настройка политик защиты приложений во время миграции Intune | Документация Майкрософт"
description: "В этой статье предоставлена процедура настройки политик защиты приложений во время миграции Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ec990ecdedff0e1b7f4fd6fd9d45fd2edc1571bd
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Этап 1. Настройка политик защиты приложений (необязательно)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Политики защиты приложений позволяют шифровать приложения, определять ПИН-код при обращении к приложению, блокировать устройства со снятой защитой или с административным доступом и выполнять множество других операций для защиты. Если телефон пользователя утерян или украден, вы можете выборочно удаленно очистить корпоративные данные с сохранением личных данных, применив политики защиты мобильных приложений.

Политики защиты приложений применяют защиту на уровне приложения и не требуют регистрации устройства. Их можно использовать как на зарегистрированных в Intune устройствах, так и на не зарегистрированных, а также на устройствах, зарегистрированных в стороннем поставщике MDM.

## <a name="app-protection-policies-with-lob-apps"></a>Политики защиты приложения с бизнес-приложениями

Политики защиты мобильных приложений также можно применить к бизнес-приложениям /intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) или к средствам упаковки приложений Microsoft Intune на платформах [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) и [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Как политики защиты приложений помогают во время миграции?

Миграция требует удаления устройств из старого поставщика MDM и их регистрации в Intune. Следует учитывать это при планировании и рекомендовать пользователям отказаться от старых поставщиков MDM и сразу же зарегистрироваться в Intune. Однако во время миграции может обнаружиться, что некоторые пользователи отложили завершение регистрации и что их устройствами не управляют поставщики MDM.

В это время риск кражи устройств и потери корпоративных данных в организации может возрасти, если доступ к корпоративным ресурсам по-прежнему разрешен, или же может снизиться производительность работы пользователей, если доступ к корпоративным ресурсам блокируется.

Intune может предложить защиту корпоративных данных во время миграции, поэтому ваши корпоративные данные будут защищены даже без управления на уровне устройств.

При отключении условного доступа в старом поставщике MDM и переходе к Intune эффективность работы пользователей не пострадает.

## <a name="task-list-for-app-protection-policies"></a>Список задач для политик защиты приложений

-   Задача 1. Узнайте, [как приступить к настройке политик защиты мобильных приложений](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune).

-   Задача 2. Узнайте, [как создать и развернуть политики защиты мобильных приложений](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

## <a name="next-steps"></a>Дальнейшие действия 

[Этап 1. Особые примечания о миграции](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

