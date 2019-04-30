---
title: Данные, которые JAMF Pro отправляет в Intune
titleSuffix: Microsoft Intune
description: Список данных, которые Jamf Pro отправляет в Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 452d6fafccc2d53d2f6940197ef4a1aa19febfc2
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61509540"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Данные, которые Jamf Pro отправляет в Intune

При использовании [Jamf Pro](https://www.jamf.com) для управления компьютерами Mac конечных пользователей с помощью Intune Jamf Pro собирает данные инвентаризации управляемых устройств macOS. а затем отправляет в Intune следующие сведения:

* Идентификатор Azure AD устройства.
* Состояние инвентаризации JAMF (состояние инвентаризации компьютера, зарегистрированное Jamf Pro за последние 24 часа).
* Версия ОС
* Идентификатор Azure AD пользователя.
* Состояние шифрования (хранилище файлов 2).
* Состояние привратника.
* Пароль (минимальное число наборов символов).
* Окончание срока действия пароля (дней)
* Тип пароля ("Простой", "Алфавитно-цифровой" или "Нет данных").
* Блокировка автоматического входа.
* Требуемая длина секретного кода.
* Пароль (число предыдущих паролей для предотвращения повторного использования).
* Защита целостности системы.
* Время последнего возврата.
* Тип архитектуры.
* Доступные слоты ОЗУ.
* Емкость батареи.
* Загрузочное ПЗУ.
* Частота шины.
* Размер кэша
* Имя устройства
* Присоединение к домену
* Идентификатор Jamf.
* MAC-адрес;
* Производитель
* Модель
* Идентификатор модели.
* Скорость сетевого адаптера.
* Число ядер.
* Число процессоров
* ОС
* Платформа
* Частота процессора
* Тип процессора
* Дополнительный MAC-адрес.
* Серийный номер
* Версия SMC.
* Общий объем ОЗУ
* UDID.
* Электронная почта пользователя.


Вы можете удалить устройство под управлением Jamf из консоли Intune, выбрав **Удалить** в представлении **Все устройства**. Чтобы выполнить массовое удаление устройств, выберите несколько устройств и нажмите **Удалить**.

Сведения об [удалении устройства под управлением Jamf см. в документации Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Чтобы получить дополнительную помощь, можно также отправить запрос в [службу поддержки Jamf](https://www.jamf.com/support/). 

