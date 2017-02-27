---
title: "Указание центра управления мобильными устройствами | Предварительная версия Intune Azure | Документы Майкрософт"
description: "Предварительная версия Intune Azure: выбор центра управления мобильными устройствами в Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 72a162175e278faa236add5698d65233fa851c7b

---

# <a name="set-the-mobile-device-management-authority"></a>Установка центра управления мобильными устройствами 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Параметр центра управления мобильными устройствами определяет способ администрирования устройств. Возможны следующие конфигурации.

- **Изолированная среда Intune** — управление только в облаке, которое настраивается с помощью портала Azure. Включает полный набор возможностей, которые предлагает Intune.

- **Гибридная среда Intune** — интеграция облачного решения Intune с System Center Configuration Manager. Вы настраиваете Intune с помощью консоли Configuration Manager.

- **Управление мобильными устройствами для Office 365** — интеграция Office 365 с облачным решением Intune. Вы настраиваете Intune в центре администрирования Office 365. Конфигурация включает набор возможностей, доступных в автономной среде Intune.

>[!IMPORTANT]
>Если после настройки центра управления мобильными устройствами вам потребуется его изменить, нужно будет обратиться в [службу поддержки Майкрософт](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune). Поэтому будьте внимательны при выборе.

**Установка центра управления мобильными устройствами**

1. На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**.

2. В колонке Intune выберите пункт **Регистрация устройств**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите пункт **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы установили Intune в качестве центра MDM.



<!--HONumber=Feb17_HO3-->


