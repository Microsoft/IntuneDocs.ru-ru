---
title: Портал службы технической поддержки по устранению неполадок
titleSuffix: Microsoft Intune
description: Персонал службы технической поддержки использует портал диагностики для устранения технических проблем пользователей.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/11/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0094cdd12b2594cb60260d768daec8c5bed04c9c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510250"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Использование портала диагностики для оказания помощи пользователям в вашей компании

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Портал диагностики позволяет операторам службы технической поддержки и администраторам Intune просматривать информацию о пользователях для обработки запросов в службу поддержки. Организации, содержащие в штате **операторов службы технической поддержки**, могут назначить такого оператора группе пользователей. Участники роли операторов службы технической поддержки могут использовать панель **Устранение неполадок**.

На панели **Устранение неполадок** также отображаются проблемы с регистрацией пользователей. Располагая сведениями о проблеме и выполняя предлагаемые действия по ее решению, администраторы и сотрудники службы поддержки могут устранять возникающие неполадки. Некоторые проблемы регистрации не фиксируются, и для некоторых ошибок могут отсутствовать предложения по исправлению.

Инструкции по добавлению роли оператора службы технической поддержки см. в статье [Управление доступом на основе ролей (RBAC) с помощью Intune](/intune/role-based-access-control).

Когда пользователь обращается в службу поддержки с техническим вопросом по Intune, оператор вводит имя этого пользователя. Intune показывает полезные данные, способные помочь в устранении многих проблем уровня 1, таких как:

- Состояние пользователя
- Назначения
- Проблемы с соответствием
- устройство не отвечает;
- устройство не получает параметры VPN или Wi-Fi;
- сбой при установке приложения.

## <a name="to-review-troubleshooting-details"></a>Просмотр сведений об устранении неполадок

На панели "Устранение неполадок" щелкните ссылку **Выбор пользователя**, чтобы просмотреть сведения о пользователе. Сведения о пользователях помогут вам понять текущее состояние пользователей и их устройств.  

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. На панели **Intune** выберите **Устранение неполадок**.
4. Щелкните **Выбрать**, чтобы выбрать пользователя для устранения неполадок.
5. Выберите пользователя, введя его имя или адрес электронной почты. Щелкните **Выбрать**. Сведения об устранении неполадок для пользователя приводятся на панели "Устранение неполадок". Эти сведения поясняются в представленной ниже таблице.

> [!Note]  
> Чтобы получить доступ к панели **Устранение неполадок**, перейдите в браузере по адресу: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Области панели мониторинга для устранения неполадок

На панели **Устранение неполадок** можно просматривать сведения о пользователе.

![Панель мониторинга устранения неполадок с пронумерованными областями, описанными в следующей таблице](./media/help-desk-operators/troubleshooting-dash.png)

| Область | Название | Описание |
| ---  | ---  | ---         |
| 1.   | Состояние учетной записи  | Показывает состояние текущего клиента Intune: **Активен** или **Неактивен**.       |
| 2.   | Выбор пользователя  | Имя выбранного в данный момент пользователя. Чтобы выбрать другого пользователя, щелкните **Сменить пользователя**.       |
| 3.   | Состояние пользователя  | Содержит лицензию Intune пользователя, число устройств, сведения о соответствии каждого устройства требованиям, число приложений и сведения о соответствии приложений требованиям.       |
| 4.   | Информация о пользователе  | В этом списке можно выбрать сведения, которые должны отображаться на панели. <br>Доступные варианты: <ul><li>Клиентские приложения<li>Политики соответствия требованиям<li> Политики конфигурации<li>Политики защиты приложений <li>Ограничения на регистрацию</ul>      |
| 5.   | Членство в группе  | Отображает текущие группы, в которые входит выбранный пользователь.       |

<!-- this section needs to be updated

## Client apps reference

The apps that are running devices
- managed by Intune and Azure Active Directory (AD) 
- owned by users managed by Intune and Azure Active Directory (AD).

### Properties

The properties of client apps.

| Property      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name          | The name of the application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| OS            | The operating system installed on the device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | You can choose an assignment type for each app.  <br> **Available** - Users install the app from the Company Portal app or website.  <br> **Not Applicable** - The app is not installed or shown in the Company Portal. <br> **Uninstall** - The app is uninstalled from devices in the selected groups.  <br> **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. |
| Last Modified | The name of the type of device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| App install | Denotes whether an app install failure or success has occurred on the individual device. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection status

An app protection policy is available to mobile apps that integrate with Enterprise Mobility Solution (EMS) technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## App protection policies reference

An app protection policy is available to mobile apps that integrate with EMS technologies.These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

### Properties

The table summarizes app protection policies status for devices managed by Intune.

| Property    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | The name of the application.                                                                                                        |
| Deployed    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Platform    | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Enrollment  | The name of the type of device.                                                                                                     |
| Last Update | The timestamp the policy was modified.                                                                                              |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device Name        | The name of the type of device.                                                                                                     |
| Managed By         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last Check in      | The name of the type of device.                                                                                                     |

## Compliance policies reference

Makes sure that the devices used to access company apps and data, comply with certain rules like using a PIN to access the device, and encryption of data stored on the device.

### Properties

The properties of the compliance policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## Configuration policies reference

An app configuration policy is available to mobile apps with vendor-specific configuration. 

### Properties

The properties of the configuration policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |


### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

-->

## <a name="enrollment-failure-reference"></a>Справочник по ошибкам регистрации

В таблице "Ошибки регистрации" приводятся попытки регистрации, которые завершились неудачно. Устройство, указанное в приведенной ниже таблице, могло впоследствии зарегистрироваться успешно при выполнении очередной попытки. Некоторые неудачные попытки могут отсутствовать в списке. Сведения об устранении доступны не для всех ошибок.

| Столбец таблицы | Описание |
|-------------|----------|
| Начало регистрации | Время, когда пользователь впервые начал регистрацию. |
| ОС | Операционная система устройства. |
| Версия ОС | Версия операционной системы устройства. |
| Сбой | Причина сбоя. |

### <a name="failure-details"></a>Сведения об ошибке

При выборе строки с ошибкой предоставляются дополнительные сведения.

| Раздел | Описание |
|-------------|----------|
| Сведения об ошибке | Более подробное описание ошибки. |
| Возможные способы исправления | Предлагаемые действия для устранения ошибки. Для некоторых ошибок могут отсутствовать. |
| Ресурсы (необязательно) | Ссылки на дополнительные материалы или разделы портала, на которых можно выполнить действия по исправлению ошибки. |

### <a name="enrollment-errors"></a>Ошибки регистрации

| Ошибка | Подробные сведения |
|-------------|----------|
| Истечение времени ожидания или сбой iOS | Истекло время ожидания между устройством и Intune из-за того, что пользователь выполняет регистрацию слишком долго. |
| Пользователь не найден или не имеет лицензии | У пользователя нет лицензии, либо он был удален из службы. |
| Устройство уже зарегистрировано | Кто-то попытался зарегистрировать с помощью Корпоративного портала устройство, которое уже зарегистрировано другим пользователем. |
| Не подключено к Intune | Предпринята попытка регистрации, когда центр управления мобильными устройствами (MDM) Intune не настроен. |
| Ошибка авторизации для регистрации | Предпринята попытка регистрации с помощью старой версии корпоративного портала. |
| Устройство не поддерживается | Устройство не соответствует минимальным требованиям для регистрации в Intune. |
| Ограничения на регистрацию не соблюдены | Регистрация была заблокирована из-за настроенного администратором ограничения на регистрацию. |
| Версия устройства слишком низкая | Администратор настроил ограничение регистрации, требующее более поздней версии устройства. |
| Версия устройства слишком высокая | Администратор настроил ограничение регистрации, требующее более старой версии устройства. |
| Устройство не может быть зарегистрировано как личное | Администратор настроил ограничения на регистрацию для блокирования регистрации личных и сбойных устройств, не заданных как корпоративные. |
| Платформа устройства заблокирована | Администратор настроил ограничение регистрации, блокирующее платформу устройства. |
| Истек срок действия массового токена | Истек срок действия массового токена в пакете подготовки. |
| Устройство или сведения AutoPilot не найдены | Устройство Autopilot не найдено при попытке регистрации. |
| Профиль AutoPilot не найден или не назначен | На устройстве нет активного профиля Autopilot. |
| Непредвиденный метод регистрации AutoPilot | Устройство пытается зарегистрироваться с помощью недопустимого метода. |
| Устройство AutoPilot удалено | Устройство, которое пытается зарегистрироваться, удалено из Autopilot для этой учетной записи. |
| Достигнут предел для устройств | Регистрация была заблокирована из-за настроенного администратором ограничения для устройств. |
| Подключение Apple | Регистрация всех устройств iOS в данное время была заблокирована из-за отсутствия сертификата Apple MDM Push Certificate в Intune или истечения срока его действия. |
| Устройство не прошло предварительную регистрацию | Устройство не было предварительно зарегистрировано как корпоративное, а регистрация личных устройств заблокирована администратором. |
| Функция не поддерживается | Вероятно, пользователь попытался зарегистрировать устройство с помощью метода, который не совместим с вашей конфигурацией Intune. |

## <a name="collect-available-data-from-mobile-device"></a>Сбор доступных данных с мобильного устройства

Используйте следующие ресурсы для сбора данных с устройств при устранении неполадок устройства пользователя:
- [Отправка ошибок регистрации iOS ИТ-администратору](/intune-user-help/send-errors-to-your-it-admin-ios)
- [Оказание помощи службе поддержки компании в устранении проблем с устройством с помощью подробного ведения журналов](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
- [Отправка журналов Android в службу поддержки вашей организации по USB-кабелю](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
- [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
- [Отправка ошибок регистрации Android ИТ-администратору](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Дальнейшие шаги

Вы можете получить дополнительные сведения об управлении доступом на основе ролей (RBAC), позволяющем определить роли для управления устройствами организации, мобильными приложениями и защитой данных. См. статью [Управление доступом на основе ролей (RBAC) с помощью Intune](/intune/role-based-access-control).

Вы можете узнать об известных проблемах в Microsoft Intune. См. статью [Известные проблемы в Microsoft Intune](/intune/known-issues).

Вы можете получить сведения о создании запросов в службу поддержки и получении справки при необходимости. [Получение поддержки](/intune/get-support).
