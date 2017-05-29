---
title: "Установка центра управления мобильными устройствами"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: выбор центра управления мобильными устройствами в Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c36ddef7e53d6f4f15c82c97dc6d18863e6859f1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Установка центра управления мобильными устройствами

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Параметр центра управления мобильными устройствами (MDM) определяет способ администрирования устройств. ИТ-администратор должен задать центр MDM, чтобы пользователи могли регистрировать устройства для управления.

Возможны следующие конфигурации.

- **Изолированная среда Intune** — управление только в облаке, которое настраивается с помощью портала Azure. Включает полный набор возможностей, которые предлагает Intune. [Установка центра управления мобильными устройствами](#mdm-authority-set-to-intune).

- **Гибридная среда Intune** — интеграция облачного решения Intune с System Center Configuration Manager. Вы настраиваете Intune с помощью консоли Configuration Manager. [Настройка подписки Intune с помощью System Center Configuration Manager и Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Управление мобильными устройствами для Office 365** — интеграция Office 365 с облачным решением Intune. Вы настраиваете Intune из центра администрирования Office 365. Конфигурация включает набор возможностей, доступных в автономной среде Intune. Задайте центр MDM в центре администрирования Office 365.

>[!IMPORTANT]
>Настроив центр управления мобильными устройствами, вам нужно обратиться в [центр поддержки Майкрософт](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) для его изменения. Поэтому будьте внимательны при выборе.

## <a name="set-mdm-authority-to-intune"></a>Выбор Intune в качестве центра MDM

1. На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**.
  ![Снимок экрана: рабочая нагрузка устранения неполадок Intune со ссылкой "Выбор пользователя"](media/set-mdm-auth.png)
2. В колонке Intune выберите **Регистрация устройства**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы успешно установили Intune в качестве центра управления мобильными устройствами.

