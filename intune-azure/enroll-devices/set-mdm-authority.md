---
title: "Установка центра управления мобильными устройствами"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9d7a1a934188f0a40553d3c6b8b567ba8f6af034
ms.lasthandoff: 02/18/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Установка центра управления мобильными устройствами 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Параметр центра управления мобильными устройствами определяет способ администрирования устройств. Возможны следующие конфигурации.

- **Изолированная среда Intune** — управление только в облаке, которое настраивается с помощью портала Azure. Включает полный набор возможностей, которые предлагает Intune.

- **Гибридная среда Intune** — интеграция облачного решения Intune с System Center Configuration Manager. Вы настраиваете Intune с помощью консоли Configuration Manager.

- **Управление мобильными устройствами для Office 365** — интеграция Office 365 с облачным решением Intune. Вы настраиваете Intune из центра администрирования Office 365. Конфигурация включает набор возможностей, доступных в автономной среде Intune.

>[!IMPORTANT]
>Настроив центр управления мобильными устройствами, вам нужно обратиться в [центр поддержки Майкрософт](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) для его изменения. Поэтому будьте внимательны при выборе.

**Установка центра управления мобильными устройствами**

1. На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**.

2. В колонке Intune выберите **Регистрация устройств**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы успешно установили Intune в качестве центра управления мобильными устройствами.

