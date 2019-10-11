---
title: Данные, которые Apple отправляет в Intune
titleSuffix: Microsoft Intune
description: Список данных, которые Apple отправляет в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b316e305afa5aaae2c65c3aa062ff0343a845ffe
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722557"
---
# <a name="data-apple-sends-to-intune"></a>Данные, которые Apple отправляет в Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Если на устройстве включена любая из следующих служб Apple, Microsoft Intune устанавливает соединение с Apple и делится с Apple сведениями о пользователе и устройстве:

- [Программа регистрации устройств Apple (DEP)](../enrollment/device-enrollment-program-enroll-ios.md)
- [Сертификат Apple MDM Push Certificate (APNs)](../enrollment/apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](../apps/vpp-apps-ios.md)

Чтобы установить соединение с Microsoft Intune, необходимо создать учетную запись Apple для каждой службы Apple.

> [!NOTE]
> В соответствии с политикой Майкрософт и Apple, мы не продаем данные, собираемые нашей службой, третьим лицам ни по какой причине.

В следующей таблице перечислены данные, которые устройство Apple отправляет в Intune. [Intune также отправляет данные в Apple](data-intune-sends-to-apple.md). 

| службы | Сообщение | Данные, отправляемые в Intune | Назначение |
|:---:|:---:|:---:| ---|
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | MessageType | Тип сообщений: проверка подлинности. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | Раздел | Раздел, который будет прослушивать устройство. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | MesUDID | UDID устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | OSVersion | Версия ОС устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | BuildVersion | Версия сборки устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | ProductName | Имя продукта устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | SerialNumber | Серийный номер устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | IMEI | IMEI-номер устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Проверка подлинности | MEID | Идентификатор мобильного оборудования устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | Раздел | Раздел, который будет прослушивать устройство. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | UDID. | UDID устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | Токен | Токен push-уведомлений устройства. Сервер должен использовать этот обновленный токен при отправке push-уведомлений на устройство. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | PushMagic | Магическая строка, которая должна быть включена в сообщение push-уведомления.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | UnlockToken | Большой двоичный объект данных, который можно использовать для разблокировки устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Обновление токена | AwaitingConfiguration | Если имеет значение true, устройство будет ожидать команды MDM DeviceConfigured, прежде чем переходить к помощнику по настройке.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Извлечение | MessageType | Тип сообщения: извлечение. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Извлечение | Раздел | Раздел, который будет прослушивать устройство. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Извлечение | UDID. | UDID устройства. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Протокол MDM | Состояние | Состояние.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Протокол MDM | UDID. |UDID устройства.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Протокол MDM | CommandUUID | UUID команды, для которой предназначен этот ответ. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Протокол MDM | ErrorChain | Массив словарей, представляющий цепочку возникших ошибок.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Серийный номер | Серийный номер устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | для базы данных модели | Название модели устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Описание | Описание устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Цвет | Цвет устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Тег ресурса | Тег ресурса устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Состояние профиля | Состояние установки профиля. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | UUID профиля | UUID назначенного профиля. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Время присвоения профиля | Метка времени в формате ISO 8601, указывающая, когда профиль был назначен устройству. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Время отправки профиля | Метка времени в формате ISO 8601, указывающая, когда профиль был отправлен устройству.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Дата назначения устройства | Метка времени в формате ISO 8601, указывающая, когда устройство было зарегистрировано в программе регистрации устройств. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Кем назначено устройство | Адрес электронной почты пользователя, который назначил устройство. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | ОС | Операционная система устройства. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Токен из программы регистрации | Семейство устройств | Семейство продуктов Apple устройства. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Идентификатор пользователя Apple | Идентификатор пользователя, созданный Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Описание приложения | Описание приложения VVP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Значок приложения | URL-адрес значка, размещенного в Apple для приложения VVP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | ИД приложения | Идентификатор приложения Apple, также известный как adamsId. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Название приложения | Имя приложения VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | assignedCount | Количество назначенных лицензий для приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | availableCount | Количество не назначенных лицензий для приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | bundleId | bundleId приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | авторские права | Информация об авторских правах для приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | CountryCode | Код страны программы VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | deviceAssignable | Apple возвращает значение true, если администратор может назначить лицензию устройства для приложения. Если нет, возвращается значение false. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | facilitatorMemberId | Идентификатор участника посредника учетной записи VPP.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Жанры | Жанры приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Глобальный уникальный идентификатор пользователя Intune | Идентификатор GUID, созданный Intune. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | isIrrevocable | Apple возвращает значение true, если лицензию нельзя отменить. Если ее можно отменить, возвращается значение false. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Идентификатор лицензии | Идентификатор, созданный Apple для идентификации определенной лицензии. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Расположение | Расположение, которое хранится в данных конфигурации VPP Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | Идентификатор Apple ID для имени участника-пользователя | Сообщение с идентификатором AppleID для пользователя, администратора и участника-посредника. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | OrganizationId | Идентификатор организации, назначенный Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | pricingParam | Тип расчета цены Apple для приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | productType | Тип продукта приложения VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | retiredCount | Количество устаревших лицензий приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | totalCount | Общее число лицензий, приобретенных для приложения. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | url | URL-адрес магазина iTunes приложения.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Токен VPP Apple | User Status (Состояние пользователя) | Состояние пользователя в программах VPP Apple. |


Чтобы прекратить использование служб Apple через Microsoft Intune и удалить данные, необходимо отключить токен Apple в Microsoft Intune и удалить учетную запись Apple. Сведения об управлении учетными записями см. в учетной записи Apple.


