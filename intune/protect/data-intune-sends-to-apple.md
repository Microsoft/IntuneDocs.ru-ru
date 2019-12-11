---
title: Данные, отправляемые Intune в Apple
titleSuffix: Microsoft Intune
description: Список данных, которые Intune отправляет Apple.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b204a956-18ec-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2f1be7a2457cca7da62883370c9e273168c6a29
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502431"
---
# <a name="data-intune-sends-to-apple"></a>Данные, отправляемые Intune в Apple

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Если на устройстве включена любая из следующих служб Apple, Microsoft Intune устанавливает соединение с Apple и делится с Apple сведениями о пользователе и устройстве: 

- [Программа регистрации устройств Apple (DEP)](../enrollment/device-enrollment-program-enroll-ios.md)
- [Сертификат Apple MDM Push Certificate (APNS)](../enrollment/apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](../apps/vpp-apps-ios.md)

Чтобы установить соединение с Microsoft Intune, необходимо создать учетную запись Apple для каждой службы Apple.

Ниже перечислены данные, которые Microsoft Intune отправляет с устройства включенным службам Apple. 

| службы | Данные, отправляемые Apple | Назначение |
|---|---| ---|
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен, PushMagic | Если сервер принимает устройство, устройство предоставляет серверу свой токен для push-уведомлений. Сервер должен использовать этот токен для отправки устройству push-уведомлений. Это сообщение о возврате также содержит строку PushMagic. Сервер должен запомнить эту строку и включить ее в push-уведомления, отправляемые на устройство. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен сервера | Токен для push-уведомлений на устройстве, используемый для проверки подлинности в службе Apple. |
| ASM/DEP | имя_сервера | Понятное имя сервера MDM. |
| ASM/DEP | server_uuid | Идентификатор сервера, созданный системой. |
| ASM/DEP | admin_id | Идентификатор Apple пользователя, создавшего текущие использующиеся токены. |
| ASM/DEP | org_name | Название организации. |
| ASM/DEP | org_email | Адрес электронной почты организации. |
| ASM/DEP | org_phone | Номер телефона организации. |
| ASM/DEP | org_address | Адрес организации. |
| ASM/DEP | org_id | Идентификатор клиента DEP. Этот ключ доступен только в версии протокола 3 и более поздних версиях. |
| ASM/DEP | serial_number | Серийный номер устройства (строка). |
| ASM/DEP | для базы данных модели | Имя модели (строка). |
| ASM/DEP | description | Описание устройства (строка). |
| ASM/DEP | asset_tag | Ярлык устройства (строка). |
| ASM/DEP | profile_status | Состояние установки профиля. Возможные значения: **пусто**, **назначено**, **отправлено** или **удалено**. |
| ASM/DEP | profile_uuid | Уникальный идентификатор назначенного профиля. |
| ASM/DEP | device_assigned_by | Адрес электронной почты пользователя, который назначил устройство. |
| ASM/DEP | ОС | Операционная система устройства: iOS, OSX или tvOS. Этот ключ допустим в протоколе сервера X версии 2 и более поздних версиях. |
| ASM/DEP | device_family | Семейство продуктов устройства Apple: iPad, iPhone, iPod, Mac или AppleTV. Этот ключ допустим в протоколе сервера X версии 2 и более поздних версиях. |
| ASM/DEP | profile_name | Строка. Понятное имя профиля. |
| ASM/DEP | support_phone_number | Необязательный параметр. Строка. Номер телефона службы поддержки для организации. |
| ASM/DEP | support_email_address | Необязательный параметр. Строка. Адрес электронной почты службы поддержки для организации. Этот ключ допустим в протоколе сервера X версии 2 и более поздних версиях. |
| ASM/DEP | department | Необязательный параметр. Строка. Определяемые пользователем имя отдела или расположения. |
| ASM/DEP | устройств | Массив строк, содержащий серийный номер устройства. (Может быть пустым.) |
| VPP | Глобальный уникальный идентификатор пользователя Intune | Идентификатор GUID, созданный Intune. |
| VPP | Идентификатор Apple ID для имени участника-пользователя | Идентификатор Apple ID, указанный администратором при настройке подключения токена VPP с Apple. |
| VPP | Серийный номер | Серийный номер управляемого устройства. |

Чтобы прекратить использование служб Apple через Microsoft Intune и удалить данные, необходимо отключить токен Apple в Microsoft Intune и удалить учетную запись Apple. Сведения об управлении учетными записями см. в учетной записи Apple.


