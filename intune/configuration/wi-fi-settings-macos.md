---
title: Настройка параметров Wi-Fi для устройств macOS в Microsoft Intune (Azure) | Документация Майкрософт
titleSuffix: ''
description: Создание и добавление профилей конфигурации Wi-Fi для устройств macOS. Вы изучите разные возможности, в том числе процедуры добавления сертификатов, выбора типа EAP и выбора метода аутентификации в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f81f4f04d1321697bce5de48eae50c2bdd8f15b7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733924"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Добавление параметров Wi-Fi для устройств macOS в Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Вы можете создать профиль с определенными параметрами Wi-Fi и развернуть этот профиль для устройств macOS. Microsoft Intune предлагает множество возможностей, в том числе аутентификация в сети, добавление сертификата первичных ключей или сертификата SCEP и многое другое.

Эти параметры Wi-Fi разделены на две категории: основные параметры и параметры корпоративного уровня.

Все они описаны в этой статье.

## <a name="before-you-begin"></a>Подготовка к работе

[Создание профиля устройства](device-profile-create.md).

> [!NOTE]
> Эти параметры доступны для всех типов регистрации. Дополнительные сведения о типах регистрации см. в разделе [macOS регистрация](../enrollment/macos-enroll.md).

## <a name="basic-profiles"></a>Базовые профили:

- **Тип Wi-Fi.** Выберите **Базовый**.
- **Имя сети.** Введите имя подключения Wi-Fi. Это значение будет отображаться в списке доступных подключений на устройствах пользователей при поиске.
- **SSID.** Обозначает **идентификатор беспроводной сети**. Это настоящее имя беспроводной сети, к которой будут подключаться устройства. Тем не менее при выборе подключения пользователи видят только имя сети, настроенное вами.
- **Подключаться автоматически.** Выберите **Включить**, чтобы устройство автоматически подключалось к этой сети, когда находится в зоне ее действия. Выберите **Отключить**, чтобы запретить автоматическое подключение устройств.
- **Скрытая сеть**. Выберите **Включить**, чтобы скрыть эту сеть в списке доступных сетей на устройстве. Идентификатор SSID не будет передаваться. Выберите **Отключить**, чтобы сеть отображалась в списке доступных сетей на устройстве.
- **Тип безопасности.** Выберите протокол безопасности, который будет использоваться для аутентификации в сети Wi-Fi. Доступны следующие параметры:

  - **Открыто (без проверки подлинности)** . Используйте этот параметр, если сеть не защищена.
  - **WPA/WPA2 - Personal** (WPA/WPA2 — личная информация). Введите пароль в поле **Общий ключ**. Когда создается или настраивается корпоративная сеть, для нее настраивается пароль или ключ сети. Введите этот пароль или ключ сети в качестве значения для общего ключа.
  - **WEP**

- **Параметры прокси-сервера.** Здесь доступны следующие варианты:
  - Чтобы не использовать параметры прокси-сервера, выберите **Нет**.
  - **Вручную.** Введите **адрес прокси-сервера** в формате IP-адреса и укажите соответствующий **номер порта**.
  - **Автоматически.** Для настройки прокси-сервера будет использоваться файл. Введите **URL-адрес прокси-сервера** (например, `http://proxy.contoso.com`), по которому размещен файл конфигурации.

## <a name="enterprise-profiles"></a>Корпоративные профили:

- **Тип Wi-Fi.** Выберите **Корпоративный**.
- **SSID.** Обозначает **идентификатор беспроводной сети**. Это настоящее имя беспроводной сети, к которой будут подключаться устройства. Тем не менее при выборе подключения пользователи видят только имя сети, настроенное вами.
- **Подключаться автоматически.** Выберите **Включить**, чтобы устройство автоматически подключалось к этой сети, когда находится в зоне ее действия. Выберите **Отключить**, чтобы запретить автоматическое подключение устройств.
- **Скрытая сеть**. Выберите **Включить**, чтобы скрыть эту сеть в списке доступных сетей на устройстве. Идентификатор SSID не будет передаваться. Выберите **Отключить**, чтобы сеть отображалась в списке доступных сетей на устройстве.

- **Тип EAP.** Выберите тип протокола расширенной проверки подлинности (EAP), используемый для проверки подлинности безопасных беспроводных подключений. Доступны следующие параметры:

  - **EAP-FAST.** Введите **параметры Protected Access Credential (PAC)** . В этом варианте используются учетные данные защищенного доступа для создания туннеля с аутентификацией между клиентом и сервером аутентификации. Доступны следующие параметры:
    - **Не использовать (PAC).**
    - **Использовать (PAC).** Если есть PAC-файл, следует его использовать.
    - **Использовать и подготовить PAC.** Создание PAC-файла и добавление его на устройства.
    - **Использовать и подготовить PAC анонимно.** Создание PAC-файла и добавление его на устройства без аутентификации на сервере.

  - **EAP-SIM**;

  - **EAP-TLS**. Также введите следующие данные:

    - **Доверие сервера** - **Имена серверов сертификатов.** **Добавление** одного или нескольких общих имен, которые используются в сертификатах, выданных доверенным центром сертификации (ЦС). Указав эти сведения, вы сможете избежать появления окна динамической проверки, которое отображается на устройствах пользователей при подключении к сети Wi-Fi.
    - **Корневой сертификат для проверки сервера.** Выберите существующий профиль доверенного корневого сертификата. Этот сертификат предоставляется серверу, когда клиент подключается к сети, а также используется для аутентификации подключения.

    - **Проверка подлинности клиента** - **Сертификат клиента для проверки подлинности клиента (сертификат удостоверения).** Выберите профиль сертификата клиента SCEP или PKCS, который развернут на устройстве. Этот сертификат выполняет роль идентификатора, который устройство предоставляет серверу для аутентификации подключения.

  - **EAP-TTLS**. Также введите следующие данные:

    - **Доверие сервера** - **Имена серверов сертификатов.** **Добавление** одного или нескольких общих имен, которые используются в сертификатах, выданных доверенным центром сертификации (ЦС). Указав эти сведения, вы сможете избежать появления окна динамической проверки, которое отображается на устройствах пользователей при подключении к сети Wi-Fi.
    - **Корневой сертификат для проверки сервера.** Выберите существующий профиль доверенного корневого сертификата. Этот сертификат предоставляется серверу, когда клиент подключается к сети, а также используется для аутентификации подключения.

    - **Проверка подлинности клиента**. Выберите **Метод проверки подлинности**. Доступны следующие параметры:

      - **Имя пользователя и пароль**. Пользователю предлагается ввести имя пользователя и пароль для аутентификации подключения. Кроме того, укажите:
        - **Метод отличается от EAP (внутреннее удостоверение)** . Выберите, как будет выполняться аутентификация подключения. Здесь нужно выбрать тот же протокол, который настроен в используемой сети Wi-Fi.

          Поддерживаются следующие варианты: **Незашифрованный пароль (РАР)** , **Протокол проверки пароля (CHAP)** , **Microsoft CHAP (MS-CHAP)** или **Microsoft CHAP версии 2 (MS-CHAP v2)**

      - **Сертификаты.** Выберите профиль сертификата клиента SCEP или PKCS, который развернут на устройстве. Этот сертификат выполняет роль идентификатора, который устройство предоставляет серверу для аутентификации подключения.

      - **Конфиденциальность удостоверений (внешнее удостоверение)** . Введите текст, отправляемый в ответ на запрос удостоверения EAP. Этот текст может иметь любое значение, например `anonymous`. Во время проверки подлинности сначала будет отправлено это анонимное удостоверение, после чего в защищенный туннель будет отправлена фактическая идентификация.

  - **LEAP**;

  - **PEAP**. Кроме того, укажите следующие данные:

    - **Доверие сервера** - **Имена серверов сертификатов.** **Добавление** одного или нескольких общих имен, которые используются в сертификатах, выданных доверенным центром сертификации (ЦС). Указав эти сведения, вы сможете избежать появления окна динамической проверки, которое отображается на устройствах пользователей при подключении к сети Wi-Fi.
    - **Корневой сертификат для проверки сервера.** Выберите существующий профиль доверенного корневого сертификата. Этот сертификат предоставляется серверу, когда клиент подключается к сети, а также используется для аутентификации подключения.

    - **Проверка подлинности клиента**. Выберите **Метод проверки подлинности**. Доступны следующие параметры:

      - **Имя пользователя и пароль**. Пользователю предлагается ввести имя пользователя и пароль для аутентификации подключения. 

      - **Сертификаты.** Выберите профиль сертификата клиента SCEP или PKCS, который развернут на устройстве. Этот сертификат выполняет роль идентификатора, который устройство предоставляет серверу для аутентификации подключения.

      - **Конфиденциальность удостоверений (внешнее удостоверение)** . Введите текст, отправляемый в ответ на запрос удостоверения EAP. Этот текст может иметь любое значение, например `anonymous`. Во время проверки подлинности сначала будет отправлено это анонимное удостоверение, после чего в защищенный туннель будет отправлена фактическая идентификация.

- **Параметры прокси-сервера.** Здесь доступны следующие варианты:
  - Чтобы не использовать параметры прокси-сервера, выберите **Нет**.
  - **Вручную.** Введите **адрес прокси-сервера** в формате IP-адреса и укажите соответствующий **номер порта**.
  - **Автоматически.** Для настройки прокси-сервера будет использоваться файл. Введите **URL-адрес прокси-сервера** (например, `http://proxy.contoso.com`), по которому размещен файл конфигурации.

## <a name="next-steps"></a>Дальнейшие шаги

Мы создали профиль, но он пока ничего не делает. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Настройка параметров Wi-Fi на устройствах [Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [iOS](wi-fi-settings-ios.md)и [Windows 10](wi-fi-settings-windows.md) .