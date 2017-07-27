---
title: "Краткое описание Intune на портале Azure"
titleSuffix: Intune on Azure
description: "Основные сведения об Intune на портале Azure и об управлении устройствами с помощью Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 07/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: a51b3c59d922b0c150073017222dca0c90c5b7a0
ms.sourcegitcommit: 36ae73f59ff5e9fdfe4f930ad0aa4b7795fe11f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Краткое описание Microsoft Intune на портале Azure


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune теперь действует на портале Azure, а это означает изменение прежних рабочих процессов и функциональных возможностей.
На новом портале Azure, где можно управлять корпоративными мобильными устройствами, компьютерами и приложениями, доступны новые и обновленные функциональные возможности.

* По ссылке [Мои функции Intune исчезли в Azure. Почему?](ui-changes.md) вы можете узнать, какие рабочие процессы и элементы пользовательского интерфейса изменились с переходом в Azure.
* В разделе [Классические группы Intune на портале Azure](groups-get-started.md) поясняется, что изменится в управлении группами с переходом на группы безопасности Azure Active Directory.




В этой библиотеке можно найти постоянно обновляемые сведения о новом портале. Если у вас есть дополнительные предложения, оставьте свои отзывы в разделе комментариев. Мы с радостью рассмотрим их.

Вот некоторые новые возможности:

- встроенная консоль для всех компонентов Enterprise Mobility + Security (EMS);
- консоль на основе HTML, созданная согласно веб-стандартам;
- поддержка Microsoft Graph API для автоматизации многих действий;
- группы Azure Active Directory (AD) для обеспечения совместимости во всех приложениях Azure;
- поддержка современных веб-браузеров.

> [!IMPORTANT]
> **Еще не видите новый портал?**<br>
> Существующие клиенты будут перенесены в новый интерфейс. Перед началом миграции клиента в центре сообщений Office появится соответствующее уведомление.
>
> Учетные записи Intune, созданные до января 2017 г., потребуется перенести (единожды), перед тем как рабочие процессы регистрации Apple станут доступны в Azure. Расписание миграции на данный момент еще не объявлено. Если у вашей существующей учетной записи отсутствует доступ к порталу Azure, рекомендуется создать пробную учетную запись.
>
> Просмотрите список потенциальных блокировщиков https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/.


## <a name="before-you-start"></a>Перед началом работы

Для использования Intune на портале Azure необходимо иметь учетную запись администратора и клиента Intune. Если у вас еще нет учетной записи, [зарегистрируйте ее](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Поддерживаемые веб-браузеры для портала Azure

Портал Azure поддерживается большинством современных компьютеров, компьютерами Mac и планшетными ПК. Мобильные телефоны не поддерживаются.
В настоящее время поддерживаются следующие браузеры:

- Microsoft Edge (последняя версия);
- Microsoft Internet Explorer 11;
- Safari (последняя версия, только для Mac);
- Chrome (последняя версия);
- Firefox (последняя версия).

Актуальные сведения о поддерживаемых браузерах см. на [портале Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Компоненты библиотеки

Документация отображает структуру портала Intune, чтобы упростить поиск нужной информации.

![Рабочие нагрузки портала Azure](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Введение и начало работы
В этом разделе содержатся [общие сведения](introduction-intune.md) по началу работы с Intune.
### <a name="plan-and-design"></a>План и проект
Сведения, которые должны помочь [спланировать и спроектировать](/intune-classic/plan-design/introduction) окружение Intune.
### <a name="device-enrollment"></a>Регистрация устройств
[Сведения о регистрации устройств в Intune](device-enrollment.md).
### <a name="device-compliance"></a>Соответствие устройства
[Сведения об определении уровня соответствия устройств для получения уведомлений об устройствах, не соответствующих требованиям](device-compliance.md).
### <a name="device-configuration"></a>Конфигурация устройства
[Сведения о профилях, используемых для настройки параметров и функций на управляемых устройствах](device-profiles.md).
### <a name="devices"></a>Устройства
[Сведения об управлении устройствами с помощью инвентаризации и отчетов](device-management.md).
### <a name="mobile-apps"></a>Мобильные приложения
[Сведения о публикации, настройке и защите приложений, а также об управлении ими](app-management.md).
### <a name="conditional-access"></a>Условный доступ
[Ограничение доступа к службам Exchange в зависимости от заданных условий](conditional-access.md).
### <a name="on-premises-access"></a>Локальный доступ
[Управление мобильными устройствами Exchange ActiveSync с использованием Microsoft Intune](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Дополнительные сведения о пользователях, устройств, которыми вы управляете, и сортировка ресурсов по группам](users-add.md).
### <a name="groups"></a>Groups (Группы)
[Начало работы с группами](groups-get-started.md)
### <a name="intune-roles"></a>Роли Intune
[Управление пользователями, выполняющими различные действия Intune, и теми, к кому применимы эти действия](role-based-access-control.md). Вы можете использовать встроенные роли для некоторых распространенных сценариев Intune или же создавать собственные роли.
### <a name="software-updates"></a>Обновления программного обеспечения
[Настройка параметров Центра обновления Windows для бизнеса с помощью Microsoft Intune](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Что нового?

[Новые возможности в Intune](whats-new.md).
