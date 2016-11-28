---
title: "Выбор способа регистрации мобильных устройств | Microsoft Intune"
description: "Выберите способ регистрации мобильных устройств в Intune, ответив на несколько простых вопросов."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: f15c9748b1c55ec46ddd0056445bf434fa323c59


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Выбор способа регистрации мобильных устройств

Определить наилучший способ регистрации для устройств, которыми вы управляете, помогут ответы на приведенные ниже вопросы.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Пользователи приносят собственные устройства или устройства предоставляются организацией?**

  - **Устройства, принадлежащие пользователям** — регистрация устройств BYOD (принеси свое устройство).
  - **Устройства, принадлежащие компании** — регистрация устройств COD.

> [!div class="button"]
[Регистрация устройств BYOD >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Регистрация устройств COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Какие устройства BYOD могут зарегистрировать пользователи?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS и Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile и Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Компьютеры с Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Являются ли устройства организации общими или привязаны к отдельным пользователям?**

> [!div class="button"]
[Общие >](#what-operating-system-are-your-shared-devices-running) [Выделенные >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Какая операционная система выполняется на общих устройствах?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Как вы будете управлять общими устройствами iOS?**

  > [!div class="button"]
  [Регистрация через программу регистрации устройств (DEP) iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Прямая регистрация устройств iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Регистрация с помощью диспетчера регистрации устройств (DEM) >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно загрузит профиль DEP и зарегистрируется с его помощью.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте вариант регистрации с помощью помощника по настройке. Если вы не хотите сбрасывать устройство, используйте вариант прямой регистрации.

  - **Диспетчер регистрации устройств (Intune)** — диспетчер регистрации устройств Intune (DEM) позволяет менеджеру или администратору зарегистрировать множество мобильных устройств с помощью одной учетной записи пользователя. Выделенные пользователи (сходство пользователей) на этих устройствах не могут присутствовать; их необходимо зарегистрировать путем установки приложения корпоративного портала и входа в него.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Как вы будете управлять выделенными устройствами iOS?**

  > [!div class="button"]
   [Программа регистрации устройств (DEP) iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Помощник по настройке iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Теги с IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Вы можете зарегистрировать устройства организации с выделенными пользователями следующим образом:

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно загрузит профиль DEP и зарегистрируется в Intune.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте вариант регистрации с помощью помощника по настройке.

  - **Пометка с номером IMEI** — импортировав международные идентификаторы мобильного оборудования (IMEI) устройств компании, можно пометить эти устройства как принадлежащие компании в Intune. Затем пользователи смогут зарегистрировать свои устройства как личные, установив корпоративный портал для доступа к ресурсам компании, таким как электронная почта, приложения и данные.



<!--HONumber=Nov16_HO3-->


