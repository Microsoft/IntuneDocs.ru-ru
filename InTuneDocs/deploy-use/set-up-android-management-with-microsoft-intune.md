---
title: "Настройка управления устройствами Android | Документы Майкрософт"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для устройств Android и KNOX Standard."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 4042a22ecfbab7970ea4b3dab8ee6a82b0da5f78
ms.lasthandoff: 04/24/2017


---

# <a name="set-up-android-device-management"></a>Настройка управления устройством Android

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Как администратор Intune вы можете включить управление устройствами Android (в т. ч. устройства Samsung Knox Standard) из корпоративного портала. После этого пользователи могут зарегистрировать свои устройства с помощью доступного в Google Play приложения корпоративного портала.

По умолчанию устройства с Android могут зарегистрироваться для участия в Intune. Чтобы запретить регистрацию устройств с Android, войдите на [портал администрирования Microsoft Intune](https://manage.microsoft.com), используя учетные данные администратора. Откройте раздел **Администратор** > **Управление мобильными устройствами** > **Правила регистрации** и снимите флажок **Разрешить устройства с Android**.

1.  **Настройка Intune**<br>
    Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами](prerequisites-for-enrollment.md#step-2-set-mdm-authority) службу **Microsoft Intune** и настроив MDM.

2.  **Регистрация устройств Android включена**<br>
    Для регистрации мобильных устройств Android никакие дополнительные настройки в консоли Intune не требуются.

3.  **Сообщите пользователям, как регистрировать свои устройства, чтобы получить доступ к ресурсам компании.**

    Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). При регистрации пользователи будут уведомлены о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.

    Дополнительные сведения о других задачах для пользователей см. в статьях:
  - [Ресурсы по пользовательскому интерфейсу Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Руководство пользователя для устройств с Android](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Так как в Китае отсутствует Магазин Google Play, корпоративный портал для устройств Android можно скачать в китайских магазинах приложений. Приложение корпоративного портала для Android можно будет скачать в следующих магазинах:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

В этом приложении взаимодействие со службой Microsoft Intune осуществляется с помощью Сервисов Google Play. В настоящее время Сервисы Google Play еще недоступны в Китае, поэтому на выполнение одной из следующих задач понадобится до 8 часов. 

|Консоль администрирования Intune| Приложение корпоративного портала Intune для Android |Веб-сайт корпоративного портала Intune|   
|---|---|---|
|Полная очистка| Удаление удаленного устройства| Удаление устройства (локального и удаленного)|
|Selective wipe (Выборочная очистка)| Сброс устройства| Сброс устройства|
|Развертывание нового или обновленного приложения| Установка доступных бизнес-приложений| Сброс секретного кода устройства|
|удаленная блокировка;|||
|Passcode reset (Сброс секретного кода)|||

### <a name="see-also"></a>См. также
[Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md)

