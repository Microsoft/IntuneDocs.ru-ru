---
title: "Выбор способа регистрации мобильных устройств"
description: "Выберите способ регистрации мобильных устройств в Intune, ответив на несколько простых вопросов."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 489936efebe4a69b834c96a4f878a905b8e4ec6f
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Выбор способа регистрации мобильных устройств

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Определить наилучший способ регистрации устройств, которыми вы управляете, помогут ответы на ряд вопросов.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Как вы будете управлять общими устройствами iOS?**

> [!div class="button"]
[Регистрация iOS с помощью программы регистрации устройств >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
[Прямая регистрация iOS >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
[Регистрация DEM >](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и зарегистрируется с его использованием.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке. Если вы не хотите сбрасывать устройство, используйте прямую регистрацию.

  - **Диспетчер регистрации устройств** — диспетчер регистрации устройств Intune (DEM) позволяет менеджеру или администратору зарегистрировать множество мобильных устройств с помощью одной учетной записи пользователя. Сходство пользователей (например, выделенные пользователи) на этих устройствах не может присутствовать, их необходимо зарегистрировать путем установки приложения корпоративного портала и входа в него.

> [!div class="button"]
[< Назад](choose-how-to-enroll-devices3.md)
