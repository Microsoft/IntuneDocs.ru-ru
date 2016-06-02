---
# required metadata

title: Настройка профилей сертификатов | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Настройка профилей сертификатов Intune
После настройки инфраструктуры и сертификатов, как описано в разделе [Настройка инфраструктуры сертификатов](configure-certificate-infrastructure.md), вы можете настроить профили сертификатов.

**Задача 1**. Экспорт доверенного корневого сертификата ЦС

**Задача 2**. Создание профилей доверенных сертификатов ЦС

**Задача 3**. Два варианта:

### Создание профилей сертификатов SCEP
Создание профилей сертификатов .PFX Задача 1. Экспорт доверенного корневого сертификата

Экспортируйте доверенный корневой сертификат ЦС в виде **CER** -файла из выдающего ЦС или с любого устройства, доверяющего выдающему ЦС.

### Экспортировать закрытый ключ не нужно.
Сертификат будет импортирован при настройке профиля доверенного сертификата. Задача 2. Создание профилей доверенных сертификатов

##### Перед созданием профиля сертификата SCEP или .PFX необходимо создать **профиль доверенного сертификата**.

1.  Профиль доверенного сертификата и профиль SCEP или .PFS требуются для каждой платформы мобильных устройств.

2.  Создание профиля доверенного сертификата

    **Откройте [консоль администрирования Intune](https://manage.microsoft.com) и щелкните **Политика** &gt; **Добавить политику**.**

    **Настройте один из следующих типов политики:**

    **Android &gt; Профиль доверенного сертификата (Android 4 и более поздние версии)**

    **iOS &gt; Профиль доверенного сертификата (iOS 7.1 и более поздние версии)**

    **Mac OS X &gt; Профиль доверенного сертификата (Mac OS X 10.9 и более поздние версии)**

    Windows &gt; Профиль доверенного сертификата (Windows 8.1 или более поздней версии)

3.  Windows &gt; Профиль доверенного сертификата (Windows Phone 8.1 или более поздней версии) Дополнительные сведения см. в разделе [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Предоставьте запрошенные сведения, чтобы настроить параметры профиля доверенного сертификата для Android, iOS, Mac OS X, Windows 8.1 или Windows Phone 8.1.


4.  В параметре **Файл сертификата** импортируйте доверенный корневой сертификат ЦС (**CER**-файл), экспортированный из выдающего ЦС.

Параметр **Конечное хранилище** применяется только к устройствам с ОС Windows 8.1 и более поздней версии и только в том случае, если у устройства несколько хранилищ сертификатов.

### По завершении нажмите кнопку **Сохранить политику**.
Новая политика отобразится в рабочей области **Политика** , после чего ее можно будет развернуть. Задача 3. Создание профилей сертификатов SCEP или .PFX После создания профиля доверенного сертификата ЦС создайте профили сертификатов SCEP или .PFX для каждой платформы, которую хотите использовать.

##### При создании профиля сертификата SCEP необходимо указать профиль доверенного сертификата для этой же платформы.

1.  Это свяжет два профиля сертификатов, однако каждый профиль необходимо по-прежнему развертывать отдельно.

2.  Создание профиля сертификата SCEP

    **Откройте [консоль администрирования Intune](https://manage.microsoft.com) и щелкните **Политика** &gt; **Добавить политику**.**

    **Настройте один из следующих типов политики:**

    **Android &gt; Профиль сертификата SCEP (Android 4 или более поздней версии)**

    **iOS &gt; Профиль сертификата SCEP (iOS 7.1 и более поздние версии)**

    **Mac OS X &gt; Профиль сертификата SCEP (Mac OS X 10.9 и более поздние версии)**

    Windows &gt; Профиль сертификата SCEP (Windows 8.1 или более поздней версии)

3.  Windows &gt; Профиль сертификата SCEP (Windows Phone 8.1 или более поздней версии)

4.  Дополнительные сведения см. в разделе [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Чтобы настроить параметры профиля сертификата SCEP, следуйте инструкциям на странице настройки профиля.

##### По завершении нажмите кнопку **Сохранить политику**.

1.  Новая политика отобразится в рабочей области **Политика** , после чего ее можно будет развернуть.

2.  Создание профиля сертификата .PFX



-   **Откройте [консоль администрирования Intune](https://manage.microsoft.com) и щелкните **Политика** &gt; **Добавить политику**.**

    -   **Настройте один из следующих типов политики:**

    -   **Android &gt; Профиль сертификата .PFX (Android 4 или более поздней версии)**

    -    **Windows &gt; PKCS #12 (.PFX) Профиль сертификата (Windows 10 и более поздние версии)**    

    Windows &gt; PKCS #12 (.PFX) Профиль сертификата (Windows Phone 10 и более поздние версии)

3.  iOS > Профиль сертификата PKCS 12 (.PFX) (iOS 7.1 и более поздние версии)

4.  Дополнительные сведения см. в разделе [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Предоставьте данные, запрашиваемые в форме политики.

## По завершении нажмите кнопку **Сохранить политику**.
Новая политика отобразится в рабочей области **Политика** , после чего ее можно будет развернуть.

Развертывание профилей сертификатов

-   При развертывании профилей сертификатов файл сертификата из профиля доверенного сертификата ЦС устанавливается на устройствах, а профиль сертификата SCEP или .PFX используется устройством для создания запроса на сертификат устройством.

    > [!TIP]
    > Профили сертификата устанавливаются только на применимых устройствах на основе платформы, используемой при создании профиля. Вы можете развернуть профили сертификатов в коллекциях пользователей или устройств.

-   Чтобы разрешить публикацию сертификатов на устройствах сразу после регистрации, разверните профиль сертификата в группе пользователей (а не в группе устройств).

При развертывании в группе устройств для получения политики может потребоваться полная регистрация устройства.

1.  Хотя каждый профиль развертывается отдельно, необходимо развернуть как доверенный корневой профиль, так и профиль SCEP или .PFX, иначе произойдет сбой политики сертификата SCEP или .PFX.

2.  Профили сертификатов развертываются так же, как и другие политики для Intune.

    -   В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.

    -   В диалоговом окне **Управление развертыванием** выполните следующие действия.

**Чтобы развернуть политику**, выберите одну или несколько групп для ее развертывания, а затем нажмите **Добавить** &gt; **ОК**.
###  **Чтобы закрыть диалоговое окно, не развертывая политику**, нажмите кнопку **Отмена**.

При выборе развернутой политики можно просмотреть дополнительные сведения о развертывании в нижней части списка политик.

-  [Дальнейшие действия](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Теперь можно использовать сертификаты для защиты профилей электронной почты, Wi-Fi и VPN:](wi-fi-connections-in-microsoft-intune.md)
-  [Настройка доступа к корпоративной электронной почте с помощью профилей электронной почты](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->

