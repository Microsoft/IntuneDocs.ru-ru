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
translationtype: Human Translation
ms.sourcegitcommit: dc08ba96eeea0ce2aad78e4d6ca0d94e709d885d
ms.openlocfilehash: 6cf7c56924091713f55fe8824fb11e522825b98f
ms.lasthandoff: 04/21/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Установка центра управления мобильными устройствами

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Параметр центра управления мобильными устройствами (MDM) определяет способ администрирования устройств. ИТ-администратор должен задать центр MDM, чтобы пользователи могли регистрировать устройства для управления.

Возможны следующие конфигурации.

- **Изолированная среда Intune** — управление только в облаке, которое настраивается с помощью портала Azure. Включает полный набор возможностей, которые предлагает Intune. [Установка центра управления мобильными устройствами](#set-mdm-authority-to-Intune).

- **Гибридная среда Intune** — интеграция облачного решения Intune с System Center Configuration Manager. Вы настраиваете Intune с помощью консоли Configuration Manager. [Настройка подписки Intune с помощью System Center Configuration Manager и Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Управление мобильными устройствами для Office 365** — интеграция Office 365 с облачным решением Intune. Вы настраиваете Intune из центра администрирования Office 365. Конфигурация включает набор возможностей, доступных в автономной среде Intune. Задайте центр MDM в центре администрирования Office 365.

>[!IMPORTANT]
>Настроив центр управления мобильными устройствами, вам нужно обратиться в [центр поддержки Майкрософт](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) для его изменения. Поэтому будьте внимательны при выборе.

## <a name="set-mdm-authority-to-intune"></a>Выбор Intune в качестве центра MDM

1. На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**.
  ![Снимок экрана: рабочая нагрузка устранения неполадок Intune со ссылкой "Выбор пользователя"](media/set-mdm-auth.png)
2. В колонке Intune выберите **Регистрация устройства**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы успешно установили Intune в качестве центра управления мобильными устройствами.

