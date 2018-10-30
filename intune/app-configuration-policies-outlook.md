---
title: Параметры Outlook для устройств iOS и Android в Microsoft Intune
description: Создайте политику конфигурации для настройки параметров Microsoft Outlook на устройствах iOS и Android.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ed1a895dd3e4cad6111b40913b43fa9c6a3cec
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903528"
---
# <a name="microsoft-outlook-configuration-settings"></a>Параметры конфигурации Microsoft Outlook 

Используйте политику конфигурации для настройки параметров Microsoft Outlook на устройствах iOS и Android. 

Чтобы создать политику конфигурации приложений для управляемых устройств iOS, см. раздел [Добавление политик конфигурации приложений для управляемых устройств iOS](app-configuration-policies-use-ios.md). Чтобы создать политику конфигурации приложений для управляемых устройств Android, см. раздел [Добавление политик конфигурации приложений для управляемых устройств Android](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Параметры конфигурации

При добавлении политики конфигурации в Intune можно задать определенные параметры для настройки Microsoft Outlook. В панели **Параметры конфигурации** области можно задать конфигурацию учетной записи электронной почты.

### <a name="basic-authentication-email-account-settings"></a>Настройки учетной записи электронной почты для базовой проверки подлинности
В Outlook для iOS и Android администраторам Exchange предоставляется возможность передавать конфигурации учетных записей методом "push" локальным пользователям, использующим базовую проверку подлинности с протоколом ActiveSync. Дополнительные сведения см. в статье [Account setup in Outlook for iOS and Android using Basic authentication](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup) (Настройка учетной записи в Outlook для iOS и Android с использованием обычной проверки подлинности). Чтобы включить настройку учетной записи, настройте следующие параметры:

- **Сервер электронной почты**. Введите имя узла локального сервера Exchange (например, mail.contoso.com).
- **Имя учетной записи электронной почты**. Введите отображаемое имя для учетной записи электронной почты. Это имя пользователи видят на своих устройствах.
- **Атрибут имени пользователя из AAD**. Это имя является атрибутом, который Intune получает из Azure Active Directory (Azure AAD). Intune динамически формирует имя пользователя, которое используется для этого профиля. Доступные варианты:
  - **Имя участника-пользователя**. Получает имя, например `user1` или `user1@contoso.com`
  - **Основной SMTP-адрес**. Получает имя в формате адреса электронной почты, например `user1@contoso.com`
- **Атрибут адреса электронной почты из AAD**. Выберите, как создается адрес электронной почты для пользователя. Выберите **Имя участника-пользователя** (`user1@contoso.com` или `user1`) для использования полного имени участника в качестве адреса электронной почты или **Первичный SMTP-адрес** (`user1@contoso.com`), чтобы использовать первичный SMTP-адрес для входа в Exchange. Рекомендуется выбрать **Основной SMTP-адрес**.
- **Домен учетной записи**. Необязательный домен учетной записи.

## <a name="next-steps"></a>Дальнейшие шаги
[Настройка параметров электронной почты в Intune](email-settings-configure.md)

