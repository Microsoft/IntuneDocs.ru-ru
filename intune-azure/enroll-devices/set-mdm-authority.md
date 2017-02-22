---
title: "Выбор центра управления мобильными устройствами | Предварительная версия Intune Azure | Документация Майкрософт"
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
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 3c0de501c172484f036aa2d812f0c40fcfa1d93f

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

1. На портале Azure выберите **Больше служб**, в текстовом поле введите **Intune**, а затем выберите **Другое** > **Intune**.

2. В колонке Intune выберите **Регистрация устройств**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы успешно установили Intune в качестве центра управления мобильными устройствами.



<!--HONumber=Feb17_HO1-->


