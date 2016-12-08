---
title: "Использование политик для упрощения управления компьютерами Windows | Microsoft Intune"
description: "Описание политик управления компьютерами Windows и параметров для Центра Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 1c6800ea3fde39603478437de6da7200ecae5afb


---

# <a name="use-policies-to-simplify-windows-pc-management"></a>Использование политик для упрощения управления компьютерами Windows

Компьютерами с Windows, где выполняется программный клиент Intune, можно управлять с помощью политик **Управление компьютером** Intune. Политики **Управление компьютером** Intune используются для настройки параметров в центре Microsoft Intune, управления обновлениями ПК и настройки брандмауэра Windows для ПК.

![Шаблон политик для компьютеров под управлением Windows](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Управление Microsoft Intune Center
Пользователи видят программный клиент Intune как **Microsoft Intune Center**. Microsoft Intune Center позволяет пользователям:

-   получать приложения с корпоративного портала;

-   проверять наличие обновлений;

-   управлять программой Microsoft Intune Endpoint Protection;

-  запрашивать удаленную помощь.

Microsoft Intune Center устанавливается на всех управляемых компьютерах. В политике Intune Center можно настроить следующие параметры, которые будут отображаться для пользователей в Microsoft Intune Center:

|Параметр политики|Подробные сведения|
|------------------|--------------------|
|**Имя**|Имя администратора, который управляет компьютером.<br />Максимальная длина: 40 символов|
|**Номер телефона**|Номер телефона администратора, который управляет компьютером.<br />Максимальная длина: 20 символов.|
|**Адрес электронной почты**|Адрес электронной почты администратора, который управляет компьютером.<br />Максимальная длина: 40 символов|
|**Название веб-сайта**|Название веб-сайта технической поддержки для пользователей.<br />>Максимальная длина: 40 символов|
|**URL-адрес веб-сайта**|URL-адрес веб-сайта технической поддержки.<br />Максимальная длина: 150 символов.|
|**Примечания**|Примечание, отображаемое для пользователей.<br />Максимальная длина: 120 символов.|

Сведения о политиках и параметрах, которые можно настроить для ПК с ОС Windows, см. в следующих ресурсах:

- [Обновление программного обеспечения на компьютерах Windows с помощью Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) — эти политики принуждают управляемые компьютеры искать и скачивать обновления программного обеспечения Майкрософт и других поставщиков. Эти обновления не включают обновления ОС (например, обновление с Windows 7 до Windows 10 или обновления с одной из версий Windows 10 до более поздней).

- [Обеспечение защиты компьютеров с ОС Windows с помощью Endpoint Protection для Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) — эти параметры включают расписания проверки и действия, которые необходимо предпринять при обнаружении вредоносного ПО.

- [Для защиты компьютеров под управлением Windows используйте политики брандмауэра Windows в Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) — эти политики упрощают администрирование параметров брандмауэра Windows на управляемых компьютерах.


### <a name="see-also"></a>См. также

[Общие задачи управления ПК с Windows с программным клиентом Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)



<!--HONumber=Nov16_HO4-->


