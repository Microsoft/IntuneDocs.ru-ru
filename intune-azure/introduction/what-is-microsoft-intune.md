---
title: "Краткое описание Intune в предварительной версии портала Azure"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Основные сведения об Intune в предварительной версии портала Azure и об управлении устройствами с помощью Intune."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 92e07a49205ffaf287fc3aa2da6a6376b75fda4f
ms.lasthandoff: 04/24/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Краткое описание Microsoft Intune в предварительной версии портала Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune перемещается на портал Azure, а это означает изменение прежних рабочих процессов и функциональных возможностей.
На новом портале Azure, где можно управлять корпоративными мобильными устройствами, компьютерами и приложениями, доступна предварительная версия новых и обновленных функциональных возможностей.
Все функциональные возможности Intune в конечном итоге будут перемещены в Azure, но многие задачи Intune можно выполнять на портале Azure уже сегодня. Так как эта возможность доступна в предварительной версии, на портале некоторые функциональные возможности еще отсутствуют. Дополнительные сведения см. в разделе [Новые возможности](#what's-new).

> [!IMPORTANT]
> **Еще не видите новый портал?**<br>
> Мы уже начали развертывать предварительную версию для выбранных клиентов. Существующие клиенты будут перемещены на портал с новыми возможностями в начале 2017 года. Перед перемещением клиента вы получите уведомление в Office Message Center.


Документацию по новому продукту вы найдете в библиотеке по Intune. Она будет непрерывно обновляться в течение периода действия предварительной версии. Если у вас есть дополнительные предложения, оставьте свои отзывы в разделе комментариев. Мы с радостью рассмотрим их.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Вот некоторые новые возможности:

- встроенная консоль для всех компонентов Enterprise Mobility + Security (EMS);
- консоль на основе HTML, созданная согласно веб-стандартам;
- поддержка Microsoft Graph API для автоматизации многих действий;
- группы Azure Active Directory (AD) для обеспечения совместимости во всех приложениях Azure;
- поддержка современных веб-браузеров.

Документацию, касающуюся классической консоли Intune, см. в [библиотеке документации Intune](https://docs.microsoft.com/en-us/intune/).

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
Этот раздел содержит следующие подразделы: [Новые возможности](/intune-azure/introduction/whats-new), [Известные проблемы](/intune-azure/introduction/known-issues-in-the-intune-preview), [Получение поддержки](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) и [Приступая к работе с бесплатной пробной версией](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) для Intune.
### <a name="plan-and-design"></a>План и проект
Сведения, которые должны помочь [спланировать и спроектировать](/intune-azure/plan-and-design/get-started) окружение Intune.
### <a name="device-enrollment"></a>Регистрация устройств
[Сведения о регистрации устройств в Intune](/intune-azure/enroll-devices/what-is).
### <a name="device-compliance"></a>Соответствие устройства
[Сведения об определении уровня соответствия устройств для получения уведомлений об устройствах, не соответствующих требованиям](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="device-configuration"></a>Конфигурация устройства
[Сведения о профилях, используемых для настройки параметров и функций на управляемых устройствах](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="devices"></a>Устройства
[Сведения об управлении устройствами с помощью инвентаризации и отчетов](/intune-azure/manage-devices/what-is).
### <a name="mobile-apps"></a>Мобильные приложения
[Сведения о публикации, настройке и защите приложений, а также об управлении ими](/intune-azure/manage-apps/what-is-app-management).
### <a name="conditional-access"></a>Условный доступ
[Ограничение доступа к службам Exchange в зависимости от заданных условий](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="on-premises-access"></a>Локальный доступ
[Управление мобильными устройствами Exchange ActiveSync с использованием Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Дополнительные сведения о пользователях, устройств, которыми вы управляете, и сортировка ресурсов по группам](/intune-azure/manage-users/what-is).
### <a name="groups"></a>Groups (Группы)
[Начало работы с группами](/intune-azure/manage-users/get-started-with-groups)
### <a name="intune-roles"></a>Роли Intune
[Управление пользователями, выполняющими различные действия Intune, и теми, к кому применимы эти действия](/intune-azure/access-control/role-based-access-control). Вы можете использовать встроенные роли для некоторых распространенных сценариев Intune или же создавать собственные роли.
### <a name="software-updates"></a>Обновления программного обеспечения
[Настройка параметров Центра обновления Windows для бизнеса с помощью Microsoft Intune](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).



## <a name="whats-new"></a>Что нового?

[Сведения о новых возможностях в предварительной версии](/intune-azure/introduction/whats-new).

