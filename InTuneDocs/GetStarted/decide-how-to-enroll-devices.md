---
title: "Выбор способа регистрации мобильных устройств | Microsoft Intune"
description: "Выберите способ регистрации мобильных устройств в Intune, ответив на несколько простых вопросов."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: b5cc645ea50e6c4bb521e04371037c3978c9426a


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Выбор способа регистрации мобильных устройств

Регистрация мобильных устройств — это процесс передачи смартфонов, планшетных и настольных компьютеров под управление Microsoft Intune. Как администратору вам следует определить наилучший способ регистрации на основе следующих критериев:

 -  Владение (личное устройство или устройство организации)
 -  Использование (общее или личное устройство)
 -  Платформа (iOS, Android, Windows Phone, компьютер с Windows, компьютер с Mac)

Определить наилучший способ регистрации для устройств, которыми вы управляете, помогут ответы на следующие вопросы.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Пользователи приносят собственные устройства или устройства предоставляются организацией?**

  - **Устройства, принадлежащие пользователям**. Регистрация BYOD-устройств (принеси свое устройство) позволяет пользователю установить приложение корпоративного портала Intune на своем устройстве и зарегистрировать его для доступа к ресурсам компании, таким как электронная почта, приложения компании, данные компании и поддержка.  

  - **Устройства, принадлежащие компании**. Устройства, принадлежащие компании, можно регистрировать разными способами в зависимости от потребностей организации и типов управляемых устройств.

> [!div class="button"]
[Регистрация BYOD >](#what-byod-devices-can-your-users-enroll) [Регистрация COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Какие устройства BYOD могут зарегистрировать пользователи?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS и Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile и Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Компьютеры с Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Являются ли устройства организации общими или привязаны к отдельным пользователям?**

- **Общие устройства, принадлежащие компании**. Такие устройства не привязываются к отдельному пользователю и обычно не предназначены для доступа к электронной почте. К ним относятся устройства, работающие в полноэкранном режиме, и устройства, ориентированные на задачи, которые пользователи берут из пула при необходимости, а затем возвращают. Рекомендуемые методы регистрации зависят от платформы устройств.

- **Отдельные пользователи**. Устройства, принадлежащие компании, которые передаются отдельным пользователям и должны отслеживаться как активы компании, позволяя пользователям при этом работать с электронной почтой и данными, как на личных устройствах. Рекомендуемые методы регистрации зависят от платформы устройств.

> [!div class="button"]
[Общие >](#what-operating-system-are-your-shared-devices-running) [Выделенные >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Какая операционная система выполняется на общих устройствах?**

> [!div class="button"]
[Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Как вы будете управлять общими устройствами iOS?**

- **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и выполнит регистрацию с использованием этого профиля.

- **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке. Если вы не хотите сбрасывать устройство, используйте прямую регистрацию.

- **Диспетчер регистрации устройств** — диспетчер регистрации устройств Intune (DEM) позволяет менеджеру или администратору зарегистрировать множество мобильных устройств с помощью одной учетной записи пользователя. Сходство пользователей (например, выделенные пользователи) на этих устройствах не может присутствовать, их необходимо зарегистрировать путем установки приложения корпоративного портала и входа в него.

  > [!div class="button"]
  [Регистрация с помощью программы регистрации устройств (DEP) iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Прямая регистрация устройств iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Регистрация с помощью диспетчера регистрации устройств (DEM) >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Как вы будете управлять выделенными устройствами iOS?**

Вы можете зарегистрировать устройства организации с выделенными пользователями следующим образом:

- **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и зарегистрируется с его использованием.

- **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке.

- **Пометка с номером IMEI** — импортировав международные идентификаторы мобильного оборудования (IMEI) устройств компании, можно пометить эти устройства как принадлежащие компании в Intune. Затем пользователи смогут зарегистрировать свои устройства как личные, установив корпоративный портал для доступа к ресурсам компании, таким как электронная почта, приложения и данные.

  > [!div class="button"]
  [Теги с IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [Программа регистрации устройств (DEP) iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Помощник по настройке iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Теги с IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Nov16_HO4-->


