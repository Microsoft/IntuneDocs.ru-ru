---
title: "Выбор способа регистрации мобильных устройств | Microsoft Intune"
description: "Выберите способ регистрации мобильных устройств в Intune, ответив на несколько простых вопросов."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 899f50cfec9e7c20d2981c077f93e0fccf37dc2b
ms.openlocfilehash: 0e516e3762dc5712a1b2d0f83016b51b15b7070f


---

# Выбор способа регистрации мобильных устройств

Определить наилучший способ регистрации для устройств, которыми вы управляете, помогут ответы на следующие вопросы.

## **Пользователи приносят собственные устройства или устройства предоставляются организацией?**

  - **Устройства, принадлежащие пользователям** — регистрация устройств BYOD (принеси свое устройство).
  - **Устройства, принадлежащие компании** — регистрация устройств COD.

> [!div class="button"]
[Регистрация устройств BYOD >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Регистрация устройств COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Какие устройства BYOD могут зарегистрировать пользователи?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS и Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile и Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Компьютеры с Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Являются ли устройства компании общими или привязаны к отдельным пользователям?**

> [!div class="button"]
[Общие >](#what-operating-system-are-your-shared-devices-running) [Выделенные >](#how-will-you-manage-dedicated-ios-devices)


## **Какая операционная система выполняется на общих устройствах?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Как вы будете управлять общими устройствами iOS?**

  > [!div class="button"]
  [Регистрация через программу регистрации устройств (DEP) iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Прямая регистрация устройств iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Регистрация с помощью диспетчера регистрации устройств (DEM) >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и зарегистрируется с его использованием.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке. Если вы не хотите сбрасывать устройство, используйте прямую регистрацию.

  - **Диспетчер регистрации устройств** — диспетчер регистрации устройств Intune (DEM) позволяет менеджеру или администратору зарегистрировать множество мобильных устройств с помощью одной учетной записи пользователя. Сходство пользователей (например, выделенные пользователи) на этих устройствах не может присутствовать, их необходимо зарегистрировать путем установки приложения корпоративного портала и входа в него.

## **Как вы будете управлять выделенными устройствами iOS?**

  > [!div class="button"]
  [Теги с IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [Программа регистрации устройств (DEP) iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Помощник по настройке iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Теги с IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Вы можете зарегистрировать устройства организации с выделенными пользователями следующим образом:

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и зарегистрируется с его использованием.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке.

  - **Пометка с номером IMEI** — импортировав международные идентификаторы мобильного оборудования (IMEI) устройств компании, можно пометить эти устройства как принадлежащие компании в Intune. Затем пользователи смогут зарегистрировать свои устройства как личные, установив корпоративный портал для доступа к ресурсам компании, таким как электронная почта, приложения и данные.



<!--HONumber=Sep16_HO2-->


