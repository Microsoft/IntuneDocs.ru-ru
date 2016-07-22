---
title: "Регистрация корпоративных устройств iOS в Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 48359b44bec9ac3e1c9510debc01d2cf8abf6d2b


---

# Регистрация корпоративных устройств iOS в Microsoft Intune
Служба Microsoft Intune поддерживает регистрацию корпоративных устройств iOS с помощью программы регистрации устройств Apple (DEP) или средства [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) на компьютере Mac.

Регистрировать корпоративные устройства iOS можно тремя способами:

-   **Регистрация помощника по настройке** — выполняет сброс устройства и подготавливает его для установки нового пользователя устройства. При использовании этого метода администратору необходимо подключить устройство iOS к USB-порту на компьютере Mac со средством Apple Configurator для настройки регистрации. Затем устройства предоставляются пользователям, которые запускают помощник по настройке, настраивают устройства, используя свои рабочие или учебные учетные данные, и завершают процесс регистрации. [Регистрация устройств iOS с использованием Apple Configurator и помощника по настройке](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Прямая регистрация** — создает файл, совместимый с Apple Configurator, для использования во время подготовки устройства. Для зарегистрированного устройства не выполняется сброс, но оно не имеет принадлежности пользователя. При использовании этого метода администратору необходимо подключить устройство iOS к USB-порту на компьютере Mac со средством Apple Configurator для регистрации устройства. [Прямая регистрация устройств iOS с помощью Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Программа регистрации устройств (DEP)** — профиль регистрации можно развертывать на устройствах, приобретенных по программе регистрации устройств Apple, в автоматическом режиме. Когда пользователь запускает помощник по настройке на устройстве, оно регистрируется в Intune.  Регистрация устройств, выполненная с помощью программы DEP, не может быть отменена пользователями. [Регистрация устройств iOS с помощью программы регистрации устройств](ios-device-enrollment-program-in-microsoft-intune.md)




### См. также
[Подготовка к регистрации устройств в Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


