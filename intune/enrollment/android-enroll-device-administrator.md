---
title: Регистрация в Microsoft Intune с использованием функции администратора устройства Android
titleSuffix: ''
description: Регистрация устройств Android в Intune с помощью функции администратора устройства.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08193aa329a1bee4e66638de5c0d7518d15db2a4
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547915"
---
# <a name="android-device-administrator-enrollment"></a>Регистрация с использованием функции администратора устройства Android

Функция администратора устройства Android (иногда называют "устаревшим" режимом управления Android — выпуск Android 2.2) — это способ управлять устройствами Android. Сейчас улучшенная функция управления доступна в [Android для бизнеса](https://www.android.com/enterprise/management/) (выпуск Android 5.0). Чтобы способствовать переходу на современные, расширенные и более безопасные средства управления устройствами, компания Google ограничивает поддержку функции администратора устройства в новых выпусках Android.

Поэтому, чтобы избежать проблем, связанных с этим ограничением, мы рекомендуем зарегистрировать новые устройства с помощью соответствующего процесса, описанного ниже.

По тем же причинам рекомендуется выполнить переход для устройств с функции управления устройством администратором, если они будут обновлены до Android 10. 

Дополнительные сведения о поддержке функции администратора устройства Android в Intune см. в разделе [Уведомления](../fundamentals/whats-new.md#decreasing-support-for-android-device-administrator).

Если вы хотите, чтобы пользователи зарегистрировали свои устройства Android с помощью функции управления администратором устройства, перейдите к следующему разделу.  


> [!Note]  
> Android версии 10 и выше не будут поддерживаться в гибридном управлении мобильными устройствами (гибридное MDM; Intune управляется с помощью консоли System Center Configuration Manager), так как поддержка этого решение прекращается 1 сентября 2019 г. Если вы все еще используете гибридное MDM, необходимо как можно скорее перейти на Intune. Обратитесь в службу поддержки, если вам нужна помощь в переходе. Дополнительные сведения см. в записи блога [Переход с гибридного управления мобильными устройствами на Intune в Azure](https://aka.ms/hybrid_notification).

Подробнее о функциях Android для бизнеса от Google:
- [Руководство Google по переходу от функции администратора устройства на функцию Android для бизнеса](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Документация Google по прекращению поддержки API администратора устройства](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>Настройка регистрации с использованием функции администратора устройства

1. Чтобы подготовиться к управлению мобильными устройствами, нужно установить **Microsoft Intune** в качестве службы управления мобильными устройствами (MDM). Инструкции см. в статье [Установка центра управления мобильными устройствами](../fundamentals/mdm-authority-set.md). Этот параметр указывается только один раз при первой настройке Intune для управления мобильными устройствами.
2. Перейдите в раздел **Intune** > **Регистрация устройств** > **Регистрация устройств Android** > **Personal and corporate-owned devices with device administration privileges** (Личные и корпоративные устройства с правами администратора устройства) > **Использовать администратор устройств для управления устройствами**.
3. [Расскажите пользователям, как регистрировать устройства](/intune-user-help/enroll-your-device-in-intune-android).  

Когда пользователь зарегистрируется, вы начнете управлять его устройством в Intune, включая [назначение политик соответствия требованиям](../protect/compliance-policy-create-android.md), [управление приложениями](../apps/app-management.md) и многое другое.

Дополнительные сведения о других задачах для пользователей см. в статьях:
- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](../fundamentals/end-user-educate.md)
- [Использование устройства Android с Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>Блокировка регистрации с использованием функции администратора устройства
Дополнительные сведения о блокировании регистрации устройств Android с функцией администратора устройства или только личных устройств Android см. в разделе [Установка ограничений по типу устройства](enrollment-restrictions-set.md).



## <a name="next-steps"></a>Дальнейшие шаги
- [Назначение политик соответствия](../protect/compliance-policy-create-android.md)
- [Управление приложениями](../apps/app-management.md)
