---
title: "Установка центра управления мобильными устройствами"
titleSuffix: Intune on Azure
description: "Выбор центра управления мобильными устройствами в Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97dede1ac393a434342f62d1f8488389dcb28d44
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Установка центра управления мобильными устройствами

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Параметр центра управления мобильными устройствами (MDM) определяет способ администрирования устройств. ИТ-администратор должен задать центр MDM, чтобы пользователи могли регистрировать устройства для управления.

Возможны следующие конфигурации.

- **Изолированная среда Intune** — управление только в облаке, которое настраивается с помощью портала Azure. Включает полный набор возможностей, которые предлагает Intune. [Установка центра управления мобильными устройствами](#set-mdm-authority-to-intune).

- **Гибридная среда Intune** — интеграция облачного решения Intune с System Center Configuration Manager. Вы настраиваете Intune с помощью консоли Configuration Manager. [Настройка подписки Intune с помощью System Center Configuration Manager и Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Управление мобильными устройствами для Office 365** — интеграция Office 365 с облачным решением Intune. Вы настраиваете Intune из центра администрирования Office 365. Конфигурация включает набор возможностей, доступных в автономной среде Intune. Задайте центр MDM в центре администрирования Office 365.

>[!IMPORTANT]    
В Configuration Manager версии 1610 или более поздней и Microsoft Intune версии 1705 вы сможете изменять центр MDM без обращения в службу поддержки Майкрософт и без отмены регистрации и повторной регистрации существующих управляемых устройств. Дополнительные сведения см. в разделе [Что делать, если центр управления мобильными устройствами выбран неправильно](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Выбор Intune в качестве центра MDM

1. На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**.
  ![Снимок экрана: рабочая нагрузка устранения неполадок Intune со ссылкой "Выбор пользователя"](media/set-mdm-auth.png)
2. В колонке Intune выберите **Регистрация устройства**, а затем щелкните **Обзор**.

3. В колонке **Управление устройствами** выберите **Выбрать Intune в качестве центра MDM**. Появится сообщение о том, что вы успешно установили Intune в качестве центра управления мобильными устройствами.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Очистка мобильного устройства после окончания срока действия сертификата MDM

Сертификат MDM обновляется автоматически, когда мобильные устройства взаимодействуют со службой Intune. Если мобильные устройства очищены или не могут связаться со службой Intune на протяжении некоторого времени, сертификат MDM не будет обновлен. Устройство будет удалено с портала Azure через 180 дней после окончания срока действия сертификата MDM.
