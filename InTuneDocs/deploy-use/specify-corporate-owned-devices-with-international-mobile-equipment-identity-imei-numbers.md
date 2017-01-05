---
title: "Указание номеров IMEI | Microsoft Intune"
description: "Microsoft Intune позволяет администраторам импортировать номера IMEI, чтобы идентифицировать корпоративные мобильные устройства на платформах мобильных устройств."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 656c93771776fd317f2b8d91bc59125fba1eb0b9
ms.openlocfilehash: 8b19cb740ed34b479fa8c4f5e2c1d13f13cda1f4


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Указание корпоративных устройств по номерам IMEI
Microsoft Intune позволяет администраторам импортировать международные идентификаторы мобильного оборудования (IMEI) для платформ мобильных устройств, на которых есть номера IMEI, для идентификации корпоративных мобильных устройств. После регистрации в Intune устройства с импортированными номерами IMEI можно просмотреть, выбрав **Группы** > **Обзор** > **Все устройства**. В разделе **Группа устройств** устройства с импортированными номерами IMEI указаны в столбце **Тип собственности** со значением **Корпоративные**.

1. В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) выберите **Группы** &gt; **Все устройства** &gt; **Все предварительно зарегистрированные корпоративные устройства** &gt; **По номеру IMEI (все платформы)** и затем выберите **Добавить устройства...** Добавить устройства можно двумя способами.

    -   **Отправка CSV-файла с серийными номерами** — создайте список значений с разделителями-запятыми (CSV-файл) с двумя столбцами без заголовка с ограничением в 5000 устройств или 5 МБ на CSV-файл.

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;Сведения об устройстве 1&gt;|
        |&lt;IMEI #2&gt;|&lt;Сведения об устройстве 2&gt;|
        В текстовом редакторе CSV-файл отображается следующим образом:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Добавление сведений об устройстве вручную** — введите номер IMEI и сведения об устройстве максимум для 15 устройств.

   Поле *Сведения* предназначено для администраторов. Можно указать сведения, чтобы идентифицировать устройство в списке корпоративных устройств, упорядоченных по коду оборудования. Эта информация не отправляется на устройство, а отображается в консоли Intune.

2.   Нажмите кнопку **Далее**.
3.  В области **Просмотреть устройства** можно проверить импортированные номера IMEI устройств. Кроме того, вы можете определить, следует ли перезаписывать **сведения** для повторно импортируемых номеров IMEI. Можно снять флажок **Заменить**, чтобы сохранить текущие сведения. Нажмите кнопку **Готово** для импорта номеров IMEI.
4.  Импортированные описания и номера IMEI вносятся в список **По номеру IMEI (все платформы)**.

При регистрации устройства с номером IMEI в Intune, что обычно происходит, когда пользователь устанавливает приложение корпоративного портала и проходит процедуру регистрации, оно помечается как корпоративное и отображается как зарегистрированное в группе **Устройства IMEI**.



<!--HONumber=Nov16_HO3-->

