---
title: Параметры электронной почты для Android Enterprise в Microsoft Intune в Azure | Документация Майкрософт
description: Создайте профили конфигурации электронной почты, использующие серверы Exchange, и извлеките атрибуты из Azure Active Directory. Включите SSL или SMIME, выполните проверку подлинности пользователей с сертификатами или именем пользователя и паролем, а также синхронизируйте электронную почту и расписания в рабочих профилях устройств Android с помощью Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62fad2a881332470a6c3e95b7cdcab0403ba1839
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734665"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Параметры устройства Android Enterprise для настройки электронной почты, проверки подлинности и синхронизации в Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

В этой статье перечислены и описаны параметры, которыми можно управлять на устройствах Android Enterprise. Как часть вашего решения управления мобильными устройствами (MDM) используйте эти параметры, чтобы настроить почтовый сервер, SSL, чтобы зашифровывать сообщения электронной почты, и многое другое.

Администратор Intune может создавать и назначать параметры электронной почты устройствам Android Enterprise в рабочем профиле.

Дополнительные сведения о профилях электронной почты см. в статье [Добавление параметров электронной почты на устройства с помощью Intune](email-settings-configure.md).

## <a name="before-you-begin"></a>Подготовка к работе

Создайте [профиль конфигурации устройства](email-settings-configure.md#create-a-device-profile) (выберите рабочий профиль) или создайте [политику конфигурации приложений](../apps/app-configuration-policies-use-android.md).

## <a name="android-enterprise"></a>Android для бизнеса

- **Приложение электронной почты**. Выберите **Gmail** или **Nine Work**
- **Почтовый сервер**. Имя узла вашего сервера Exchange. Например, введите `outlook.office365.com`.
- **Атрибут имени пользователя из AAD**. Это имя является атрибутом, который Intune получает из Azure Active Directory (Azure AAD). Intune динамически формирует имя пользователя, которое используется для этого профиля. Доступны следующие параметры:

  - **Имя участника-пользователя**. Получает имя, например `user1` или `user1@contoso.com`
  - **Имя пользователя**. Получает только имя, например `user1`

- **Атрибут адреса электронной почты из AAD**. Это имя является атрибутом адреса, который Intune получает из Azure AD. Intune динамически создает имя пользователя, которое используется для этого профиля. Доступны следующие параметры:
  - **Имя участника-пользователя**. В качестве адреса электронной почты используется полное имя субъекта (`user1@contoso.com` или `user1`).
  - **Основной SMTP-адрес**. Для входа в Exchange используется основной SMTP-адрес (например, `user1@contoso.com`).

- **Способ проверки подлинности**. В качестве метода проверки подлинности, используемого профилем электронной почты, выберите **Имя пользователя и пароль** или **Сертификаты**.
  - Выбрав способ **Сертификаты**, укажите созданный ранее профиль клиентского сертификата SCEP или PKCS, который будет использоваться для проверки подлинности подключения к Exchange.
- **SSL**. Выберите **Включить**, чтобы использовать протокол SSL при отправке и получении электронной почты, а также для взаимодействия с сервером Exchange.
- **Объем синхронизируемой электронной почты**. Выберите время, за которое требуется синхронизировать электронную почту. Или выберите **Не ограничено**, чтобы синхронизировать все доступные сообщения электронной почты.
- **Типы содержимого для синхронизации** (только для Nine Work). Выберите, какие данные вы хотите синхронизировать на устройствах. Доступны следующие параметры:
  - **Контакты**. Выберите **Включить**, чтобы разрешить пользователям синхронизировать контакты на своих устройствах.
  - **Календарь**. Выберите **Включить**, чтобы разрешить пользователям синхронизировать календарь на своих устройствах.
  - **Задачи**. Выберите **Включить**, чтобы разрешить пользователям синхронизировать задачи на своих устройствах.

## <a name="next-steps"></a>Дальнейшие шаги

[Назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Вы также можете создать профили электронной почты, дополнительные сведения см. в статьях [Параметры устройств Android и Android Enterprise для настройки электронной почты, проверки подлинности и синхронизации в Intune](email-settings-android.md), [Параметры профиля электронной почты для устройств iOS в Intune](email-settings-ios.md), [Параметры профиля электронной почты для устройств с ОС Windows 10 в Intune](email-settings-windows-10.md) и [Параметры профиля электронной почты в Microsoft Intune для устройств Windows Phone 8.1](email-settings-windows-phone-8-1.md).