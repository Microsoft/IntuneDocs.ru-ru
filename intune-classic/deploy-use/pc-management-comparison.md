---
title: Сравнение вариантов управления компьютерами Windows
description: Регистрация корпоративных устройств iOS с помощью программы регистрации устройств Apple (DEP) или Apple Configurator.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c760f9c76e54c0b5f9eb037414870ab1c8943803
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Сравнение возможностей для управления ПК Windows как компьютерами или мобильными устройствами

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Организации могут использовать Microsoft Intune для управления ПК Windows как мобильными устройствами с помощью функции MDM или как компьютерами с использованием программного клиента Intune.  Корпорация Майкрософт рекомендует по возможности использовать решение MDM. На следующей схеме приводится сравнение этих двух вариантов управления, что поможет вам лучше понять различия между ними.

|**Возможность или сценарий** |**Управление устройством Windows как компьютером**<br>Intune software client (Программный клиент Intune) | **Управление устройством Windows как мобильным устройством**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Операционные системы** |Windows 10, Windows 8 и более поздние версии, Windows 7, Windows Vista | Windows 10 и более поздние версии |
|**Поддержка портала Intune** |[Консоль Silverlight](https://manage.microsoft.com)|[Портал Azure](https://portal.azure.com) |
|**Условный доступ**|Недоступно|Доступно <br>[Что такое условный доступ?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Массовая регистрация**|Недоступно|Доступно <br>[Массовая регистрация для устройств Windows](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Профили устройств**|Недоступно|Доступно <br>[Что такое профили устройств в Microsoft Intune?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Регистрация без агентов**|Недоступно |Доступно<br>[Регистрация устройств с Windows](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Управление обновлением программного обеспечения**| Обновления Windows и обновления приложений Майкрософт<br>[Обновление программного обеспечения на компьютерах с Windows](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Использование Магазина Майкрософт для бизнеса для получения обновлений приложений Windows 10 и Майкрософт<br> [Настройка параметров Центра обновления Windows для бизнеса](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Управление лицензиями на программное обеспечение**|Доступно <br>[Управление лицензионными соглашениями для программного обеспечения компьютеров Windows](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Магазин Майкрософт для бизнеса (только приложения с расширением appx)<br>[Управление приложениями, приобретенными в Магазине Майкрософт для бизнеса](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Инвентаризация**|Доступно <br>[Просмотр данных инвентаризации оборудования и программного обеспечения для компьютеров под управлением Windows](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Доступно <br>[Отслеживание сведений о приложении](https://docs.microsoft.com/intune/apps-monitor)<br>[Что такое управление устройствами](https://docs.microsoft.com/intune/device-management)|
|**Политика брандмауэра Windows**|Доступно <br>[Для защиты компьютеров под управлением Windows используйте политики брандмауэра Windows в Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Недоступно|
|**Защита от вредоносных программ**|Endpoint Protection<br>[Обеспечение защиты компьютеров с ОС Windows с помощью Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Защитник Windows<br>[Параметры Защитника Windows](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Удаленная поддержка** |TeamViewer<br>[Запрос и предоставление удаленной помощи для компьютеров под управлением Windows](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Недоступно |
|**Развертывание приложений** | Недоступно для Магазина Майкрософт для бизнеса,<br>только файлы с расширением exe, appx и пакеты msi с несколькими файлами<br>[Добавление приложений для компьютеров Windows, на которых выполняется программный клиент Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Доступно для приложений Магазина Майкрософт и бизнес-приложений<br>[Добавление приложений Магазина Windows](https://docs.microsoft.com/intune/store-apps-windows)<br>[Добавление бизнес-приложений Windows](https://docs.microsoft.com/intune/lob-apps-windows)|
|**Защита приложений**|Недоступно|Доступно <br>[Что такое политики защиты приложений?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Аттестация работоспособности**|Недоступно|Доступно|


### <a name="advantages-of-mdm-windows-pc-management"></a>Преимущества управления компьютерами Windows с помощью функции MDM
Управление компьютерами Windows с использованием современной модели управления мобильными устройствами имеет следующие преимущества:
- **Масштабируемость**. Возможности управления MDM масштабируются за счет облачных ресурсов управления Intune. Программный клиент Intune поддерживает не более 7000 ПК.
- **Простота**. Использование современных функций управления, входящих в состав операционной системы, вместо скачиваемого программного клиента
- **Согласованность**. Ваши ПК с Windows управляются так же, как и любые другие мобильные устройства в организации
<!-- - **Cloud optimization** - -->
