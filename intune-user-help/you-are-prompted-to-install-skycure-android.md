---
title: "Необходимо установить Symantec Endpoint Protection Mobile на устройстве Android | Microsoft Docs"
description: "Дополнительные сведения об установке SEP Mobile на устройстве Android."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 627cd171-6e1b-439e-809a-2e6f007c4b3d
searchScope: User help
ROBOTS: 
ms.custom: intune-enduser
ms.openlocfilehash: f94a7cdb4feeea19527efec6486d09efcaca9b67
ms.sourcegitcommit: 1135765fd3ac2149663341d8107f656aba236493
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2017
---
# <a name="you-need-to-install-symantec-endpoint-protection-mobile-on-your-android-device"></a>Необходимо установить Symantec Endpoint Protection Mobile на устройстве Android

Прежде чем вы сможете получить доступ к рабочим файлам, службе поддержки вашей компании потребуется установить приложение Symantec Endpoint Protection (SEP) Mobile для мобильных устройств, которое помогает защитить устройство путем поиска потенциальных угроз безопасности.

Если возникают проблемы с установкой, выполните действия по устранению неполадок, описанные в конце этого раздела.

**Необходимо выполнить следующие действия:**

1. Перетащите вниз из верхней части экрана панель уведомлений и откройте ее, а затем коснитесь пункта **Required application – Install Skycure from Play Store** (Необходимые приложения — установить Skycure из Магазина Google Play). Его также можно найти в приложении корпоративного портала в разделе __Сведения о соответствии__.

  <!--![The compliance details page on an Android device. The device is not in compliance, with a message at the bottom of the Company Portal page that says the device doesn't meet the mobile risk policy, and that Skycure must be opened to resolve the issue.](./media/skycure-resolves-compliance-android.png)-->

2. Будет выполнен переход на страницу SEP Mobile в Магазине Google Play. Установите SEP Mobile, а затем коснитесь пункта **ПРИНЯТЬ**, чтобы разрешить SEP Mobile получать доступ к устройству.

3. Откройте SEP Mobile, а затем коснитесь элемента **ПРОВЕРКА**.

4. Коснитесь элемента **Sign in with Azure Active Directory** (Вход с использованием Azure Active Directory) и укажите учетную запись, которая используется для доступа к рабочей или учебной электронной почте и файлам.

5. Выберите учетную запись, используемую для доступа к рабочей или учебной электронной почте и файлам, и коснитесь кнопки **ДОБАВИТЬ УЧЕТНУЮ ЗАПИСЬ**.

6. Коснитесь кнопки **Принять**, чтобы предоставить SEP Mobile разрешение на вход и чтение профиля.

7. Ознакомьтесь с материалами о защите устройств с помощью SEP Mobile, а затем коснитесь кнопки **ОК**. За несколько секунд SEP Mobile настроится, а затем начнется проверка на наличие угроз безопасности на устройстве.

8. SEP Mobile сразу начнет проверять ваше устройство на наличие угроз безопасности.

  <!--![Skycure is analyzing your device for security threats.](./media/skycure-scan-in-progress-android.png)-->

  Если SEP Mobile обнаружит на устройстве угрозы безопасности, будут предложены инструкции по устранению проблемы.

  <!--![Skycure found a security threat.](./media/skycure-found-a-threat-android.png)-->

  Если угрозы не найдены, все три типа угроз будут выделены зеленым цветом.

    Экран **сведений об устройстве** на корпоративном портале показывает, что теперь ваше устройство соответствует требованиям безопасности вашей организации.

    ![Устройство теперь соответствует политикам](./media/mtd-device-now-compliant-android.png)

**Если установка не выполняется**

Иногда может происходить сбой установки из-за технических проблем, решить которые вы не можете. В этом случае попробуйте установить SEP Mobile [вручную из Магазина Google Play](https://play.google.com/store/apps/details?id=com.skycure.skycure).

По-прежнему нужна помощь? Обратитесь в службу поддержки вашей компании. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).
