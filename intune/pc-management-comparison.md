---
title: Сравнение вариантов управления компьютерами Windows
titlesuffix: Microsoft Intune
description: Регистрация корпоративных устройств iOS с помощью Программы регистрации устройств Apple (DEP) или Apple Configurator.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c70dbee01c546f73052b8741ce339c7bfe92fc7
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461147"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Сравнение возможностей для управления ПК Windows как компьютерами или мобильными устройствами

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Организации могут использовать Microsoft Intune для управления ПК Windows как мобильными устройствами с помощью функции MDM или как компьютерами с использованием программного клиента Intune.  Корпорация Майкрософт рекомендует по возможности использовать решение MDM. На следующей схеме приводится сравнение этих двух вариантов управления, что поможет вам лучше понять различия между ними.

|**Возможность или сценарий** |**Управление устройством Windows как компьютером**<br>Intune software client (Программный клиент Intune) | **Управление устройством Windows как мобильным устройством**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Операционные системы** |Windows 10, Windows 8 и более поздние версии, Windows 7, Windows Vista | Windows 10 и более поздние версии |
|**Поддержка портала Intune** |[Консоль Silverlight](https://manage.microsoft.com)|[Портал Azure](https://portal.azure.com) |
|**Условный доступ**|Недоступно|Доступно <br>[Что такое условный доступ?](conditional-access.md)|
|**Массовая регистрация**|Недоступно|Доступно <br>[Массовая регистрация для устройств Windows](windows-bulk-enroll.md)|
|**Профили устройств**|Недоступно|Доступно <br>[Что такое профили устройств в Microsoft Intune?](device-profiles.md)|
|**Регистрация без агентов**|Недоступно |Доступно<br>[Регистрация устройств с Windows](windows-enroll.md)|
|**Управление обновлением программного обеспечения**| Обновления Windows и обновления приложений Майкрософт<br>[Обновление программного обеспечения на компьютерах с Windows](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Использование Магазина Майкрософт для бизнеса для получения обновлений приложений Windows 10 и Майкрософт<br> [Настройка параметров Центра обновления Windows для бизнеса](windows-update-for-business-configure.md) |
|**Управление лицензиями на программное обеспечение**|Доступно <br>[Управление лицензионными соглашениями для программного обеспечения компьютеров Windows](manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Магазин Майкрософт для бизнеса (только приложения с расширением appx)<br>[Управление приложениями, приобретенными в Магазине Майкрософт для бизнеса](windows-store-for-business.md)|
|**Инвентаризация**|Доступно <br>[Просмотр данных инвентаризации оборудования и программного обеспечения для компьютеров под управлением Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Доступно <br>[Отслеживание сведений о приложении](apps-monitor.md)<br>[Что такое управление устройствами](device-management.md)|
|**Политика брандмауэра Windows**|Доступно <br>[Для защиты компьютеров под управлением Windows используйте политики брандмауэра Windows в Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Доступно <br>[Брандмауэр Защитника Windows](endpoint-protection-windows-10.md#windows-defender-firewall)|
|**Защита от вредоносных программ**|Endpoint Protection<br>[Обеспечение защиты компьютеров с ОС Windows с помощью Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Защитник Windows<br>[Включение Защитника Windows](advanced-threat-protection.md)|
|**Удаленная поддержка** |TeamViewer<br>[Запрос и предоставление удаленной помощи для компьютеров под управлением Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Использование TeamViewer для удаленного администрирования устройств Intune](device-profile-android-teamviewer.md) |
|**Развертывание приложений** | Недоступно для Магазина Майкрософт для бизнеса,<br>только файлы с расширением exe, appx и пакеты msi с несколькими файлами<br>[Добавление приложений для компьютеров Windows, на которых выполняется программный клиент Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)|Доступно для приложений Магазина Майкрософт и бизнес-приложений<br>[Добавление приложений Магазина Windows](store-apps-windows.md)<br>[Добавление бизнес-приложений Windows](lob-apps-windows.md)|
|**Защита приложений**|Недоступно|Доступно <br>[Что такое политики защиты приложений?](app-protection-policy.md)|
|**Аттестация работоспособности**|Недоступно|Доступно|


### <a name="advantages-of-mdm-windows-pc-management"></a>Преимущества управления компьютерами Windows с помощью функции MDM
Управление компьютерами Windows с использованием современной модели управления мобильными устройствами имеет следующие преимущества:
- **Масштабируемость**. Возможности управления MDM масштабируются за счет облачных ресурсов управления Intune. Программный клиент Intune поддерживает не более 7000 ПК.
- **Простота**. Использование современных функций управления, входящих в состав операционной системы, вместо скачиваемого программного клиента
- **Согласованность**. Ваши ПК с Windows управляются так же, как и любые другие мобильные устройства в организации
<!-- - **Cloud optimization** - -->
