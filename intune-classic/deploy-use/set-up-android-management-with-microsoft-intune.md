---
title: "Настройка управления Android"
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5826cd29bf07a3f1cf9b91ec75f0e0bb46050d60
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2017
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
  - [Ресурсы по пользовательскому интерфейсу Microsoft Intune](/intune/end-user-educate)
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
