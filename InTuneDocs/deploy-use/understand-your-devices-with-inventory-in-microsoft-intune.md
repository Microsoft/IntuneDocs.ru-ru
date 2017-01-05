---
title: "Получение сведений об устройствах с помощью инвентаризации | Microsoft Intune"
description: "Сведения об использовании Intune для просмотра информации об оборудовании управляемых устройств."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dbf3ac5c7ab326fd82acb979ea7a4933ac68ff1c
ms.openlocfilehash: 1bfb47cccc6438bae54a57271e585bdc9f9f6611


---

# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Получение сведений об устройствах с помощью инвентаризации в Microsoft Intune
Microsoft Intune позволяет просматривать данные инвентаризацию зарегистрированных устройств и компьютеров под управлением Windows, где запущено клиентское программное обеспечение Intune.
Обычно Intune собирает данные инвентаризации с управляемых устройств раз в 7 дней. Из-за этого внесенные на устройствах изменения, например смена имени или свободное дисковое пространство, могут отображаться в отчетах с задержкой.

## <a name="whats-collected-from-enrolled-devices"></a>Данные, собираемые с зарегистрированных устройств
Чтобы просмотреть данные инвентаризации, собранные мобильными устройствами, запустите [Отчеты инвентаризации мобильных устройств](understand-microsoft-intune-operations-by-using-reports.md). Intune собирает следующие данные инвентаризации с зарегистрированных устройств:

|Свойство|Кто собирает|
|------------|-----------------------|
|**Имя**|Все устройства|
|**Операционная система**|Все устройства|
|**Изготовитель**|Все устройства|
|**Модель**|Все устройства|
|**Канал управления**|Все устройства|
|**Зарегистрировано в AAD**|Все устройства, кроме Mac OS X|
|**Соответствует**|Все устройства|
|**EAS активирована**|Все устройства, кроме Mac OS X|
|**Идентификатор активации EAS**|Все устройства, кроме Mac OS X|
|**Время активации EAS**|Все устройства, кроме Mac OS X|
|**Состояние управления**|Все устройства|
|**Адрес электронной почты**|Все устройства|
|**Идентификатор Exchange ActiveSync**|Все устройства|
|**Устройства, на которых получен корневой доступ или выполнен взлом ОС**|Только устройства iOS и Android|
|**Уникальный идентификатор устройства**|Все устройства, кроме Exchange ActiveSync|
|**Серийный номер**|Настольные устройства iOS, Mac OS X, Android, Windows 8.1 и Windows 10|
|**Общая вместимость хранилища**|Настольные и мобильные устройства iOS, Mac OS X, Windows 8.1 и Windows 10|
|**Свободное место для хранения данных**|Настольные устройства iOS, Mac OS X, Windows 8.1 и Windows 10|
|**Номер телефона**<br>Телефоны, отнесенные к корпоративным, идентифицируются по полному номеру телефона (например, при запуске отчета об инвентаризации мобильных устройств). Номера телефонов BYOD маскируются символами *; отображаются только четыре последние цифры.|Устройства iOS, Android и Windows Phone|
|**IMEI**|Устройства Exchange ActiveSync, iOS, Android и Windows Phone|
|**MEID**<br>Идентификатор мобильного оборудования|Только устройства iOS|
|**Wi-Fi MAC**|Все устройства, кроме Exchange ActiveSync|
|**Абонентская система связи**|Только устройства iOS и Android|
|**Сотовая технология**|Только устройства iOS и Android|
|**Защищено**|Только устройства iOS|
|**Состояние блокировки активации**|Только устройства iOS|
|**Дата регистрации**|Все устройства|
|**Последнее обновление**|Все устройства|
|**Ethernet MAC**|Только устройства Mac OS X|
|**Блокировка активации включена**|Только устройства iOS|
|**Шифрование включено**|Все устройства|

## <a name="whats-collected-from-windows-pcs"></a>Данные, собираемые с компьютеров Windows
> [!IMPORTANT]
> Этот раздел применим только для компьютеров под управлением Windows, где запущено клиентское программное обеспечение Windows Intune.

Чтобы просмотреть данные инвентаризации компьютеров Windows, выполните [Отчеты об инвентаризации компьютеров](understand-microsoft-intune-operations-by-using-reports.md). Intune собирает следующие данные инвентаризации с компьютеров Windows:

-   **Имя**

-   **Тип шасси**

-   **Изготовитель**

-   **Модель**

-   **Операционная система**

-   **Версия TPM**

-   **Общий объем дискового пространства**

-   **Используется места на диске**

-   **Свободное место на диске**

-   **Имя диска ОС**

-   **Место на диске ОС**

-   **Свободное место на диске ОС**

-   **Физическая память**

-   **Имя процессора**

-   **Архитектура процессора**

-   **Скорость ЦП**

-   **IP-адрес**

-   **Серийный номер**

-   **Последний пользователь, вошедший в систему**

-   **Назначенный пользователь**

-   **Последнее обновление**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Nov16_HO2-->

