---
title: Защита данных компании с помощью шифрования
description: Это руководство призвано помочь вам защитить данные компании от потери путем применения секретного кода и шифрования данных в мобильных приложениях с помощью политики.
keywords: шифрование, ПИН-код, данные
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/22/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 084da36e9b417e4faee87f33bbd42e0e5f5fa7e2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="quick-start-guide-protect-company-data-with-data-encryption"></a>Краткое руководство по началу работы. Защита корпоративных данных с помощью шифрования

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune может помочь предотвратить потерю данных в мобильных приложениях Office различными способами:
- путем шифрования корпоративных данных с применением высочайшего уровня шифрования устройства, предоставляемого системами iOS и Android;
- на устройствах iOS и Android, которые в связи с требованиями к конфиденциальности или юридическими требованиями нельзя зарегистрировать в решении для управления мобильными устройствами.

С помощью Microsoft Intune можно также предотвращать потерю данных в мобильных приложениях Office и защищать данные Office 365 (O365), не регистрируя мобильные устройства iOS и Android в полнофункциональной системе управления мобильными устройствами. Это верно и в том случае, если вы используете решение для управления мобильными устройствами от стороннего производителя.

## <a name="is-this-quick-start-guide-right-for-me"></a>Подходит ли для меня это краткое руководство по началу работы?
Это краткое руководство по началу работы будет полезным, если выполняются перечисленные ниже требования.
- Вы уже используете или собираетесь использовать лицензии Office 365 и управляете мобильными приложениями Office.
- Вы планируете использовать мобильные приложения Office в iOS или Android.
- Вы используете любое решение для управления мобильными устройствами — от корпорации Майкрософт или другого производителя. Если вы не можете использовать решение для управления мобильными устройствами из-за предусмотренных законом правил, то вы можете воспользоваться этим руководством.

> [!NOTE]
> Windows пока не является поддерживаемой платформой для мобильных приложений Office. Управление мобильными приложениями без регистрации пока не совместимо с локальными развертываниями Exchange и SharePoint. Вы можете защищать только данные, размещенные в веб-версиях.

Это руководство может помочь вам защитить свою организацию от потери данных путем применения секретных кодов и шифрования данных с помощью политик в мобильных приложениях, которые ваши сотрудники используют для доступа к конфиденциальным данным. При этом не требуется полностью выполнять процедуру регистрации в решении для управления устройствами. Microsoft Intune позволяет настраивать политики управления мобильными приложениями (MAM) в мобильных приложениях Office для [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) и [Android](https://products.office.com/mobile/office-mobile-apps-for-android). Такой подход обеспечивает защиту данных Office 365 и не требует регистрации устройств пользователями в решении для управления мобильными устройствами, поэтому конечные пользователи смогут по-прежнему комфортно работать с мобильными приложениями Office.

## <a name="how-do-i-do-it"></a>Как это сделать?
1.  [Узнайте, как можно защитить данные приложения](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.  [Подготовьтесь к настройке политик управления мобильными приложениями](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune).
3.  [Создайте и разверните политики управления мобильными приложениями](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

## <a name="additional-information"></a>Дополнительная информация:
- [Что происходит при управлении приложением iOS с помощью политик MAM](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune](/intune/apps-prepare-mobile-application-management)
- [Просмотр списка партнеров, предоставляющих приложения для Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
