---
title: "Настройка регистрации программы Apple School Manager для устройств iOS"
titleSuffix: Intune on Azure
description: "Сведения о настройке регистрации программы Apple School Manager для корпоративных устройств iOS с помощью Intune\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Включение регистрации устройств iOS с помощью Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Этот раздел поможет ИТ-администраторам зарегистрировать устройства iOS, приобретенные по программе [Apple School Manager](https://school.apple.com/) (ASM). Microsoft Intune поддерживает беспроводной (OTA) профиль развертывания, который позволяет регистрировать ASM для управления в этой службе. В этом случае администратору не нужно работать отдельно с каждым управляемым устройством. Профиль ASM содержит параметры управления, которые применяются в процессе регистрации, в том числе параметры помощника по настройке.

**Процедура регистрации устройств ASM**
1. [Получение токена ASM и назначение устройств](#get-the-asm-token-and-assign-devices)
2. [Создание профиля регистрации](#create-an-apple-enrollment-profile)
3. [Подключение School Data Sync](#connect-school-data-sync) (необязательно)
4. [Синхронизация управляемых устройств ASM](#sync-asm-managed-devices)
5. [Назначение профиля ASM устройствам](#assign-an-asm-profile-to-devices)
6. [Распределение устройств между пользователями](#distribute-devices-to-users)

>[!NOTE]
>Регистрация ASM не может применяться без учетной записи [программы регистрации устройств (DEP)](device-enrollment-program-enroll-ios.md) Apple или [диспетчера регистрации устройств](device-enrollment-manager-enroll.md) Intune.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Получение токена ASM Apple и назначение устройств

Перед регистрацией корпоративных устройств iOS с помощью программы Apple School Manager (ASM) необходимо получить файл токена ASM (.p7m) от Apple. Этот токен позволяет службе Intune синхронизировать сведения об устройствах, участвующих в программе ASM. Он также позволяет службе Intune выполнять отправку данных профилей регистрации в Apple и назначать устройства этим профилям. На портале Apple также можно назначить серийные номера управляемых устройств.

**Предварительные требования**
- [Сертификат Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Наличие регистрации в программе [Apple School Management](http://school.apple.com)

**Шаг 1. Скачайте сертификат открытого ключа Intune, необходимый для создания токена ASM Apple.**<br>
1. На [портале Intune](https://aka.ms/intuneportal) Azure выберите **Регистрация устройства** и затем щелкните **Токен программы регистрации**.
2. В колонке **Токен программы регистрации** щелкните **Скачать открытый ключ**, чтобы скачать и локально сохранить файл ключа шифрования (.pem). PEM-файл используется для запроса сертификата отношений доверия с портала программы Apple School Manager.

**Шаг 2. Скачайте токен ASM и назначьте устройства.**<br>
Выберите **Создать токен через Apple School Manager** и выполните вход с помощью идентификатора Apple ID вашей компании. Этот идентификатор Apple ID можно использовать для обновления токена ASM.

   1.  На [портале Apple School Manager](https://school.apple.com) перейдите в раздел **MDM Servers** (Серверы MDM) и щелкните **Add MDM Server** (Добавить сервер MDM) в верхнем правом углу.
   2.  Введите значение в поле **MDM Server Name** (Имя сервера MDM). Имя сервера используется в качестве справочной информации для идентификации сервера управления мобильными устройствами (MDM). Это не имя или URL-адрес сервера Microsoft Intune.
   3.  Выберите на портале Apple команду **Upload File** (Загрузить файл), найдите нужный PEM-файл и щелкните **Save MDM Server** (Сохранить сервер MDM) в нижнем правом углу.
   4.  Выберите **Get Token** (Получить токен) и скачайте файл токена сервера (.p7m) на компьютер.
   5. Выберите **Device Assignments** (Назначения устройств), а затем **Choose Device** (Выбрать устройство) и вручную введите значение в поля **Serial Numbers** (Серийный номер) или **Order Number** (Номер заказа), либо нажмите **Upload CSV File** (Загрузить CSV-файл).
   6.   Выберите действие **Assign to Server** (Присвоить серверу) и затем выберите созданный сервер в поле **MDM Server** (Сервер MDM).
   7. Укажите, каким образом необходимо **выбрать устройства**, предоставьте сведения об устройстве и укажите **серийный номер** и **номер заказа** для каждого устройства в соответствующих полях или выберите **Upload CSV File** (Отправить CSV-файл).
   8. Выберите команду **Назначить серверу**, &lt;имя_сервера&gt;, указанное для Microsoft Intune, и нажмите кнопку **ОК**.

**Шаг 3. Введите идентификатор Apple ID, с помощью которого был создан токен ASM.**<br>Этот идентификатор применяется для обновления токена ASM Apple и хранится для последующего использования.

**Шаг 4. Найдите и загрузите токен.**<br>
Перейдите к файлу сертификата (.p7m) и щелкните **Открыть**, а затем выберите **Передать**. Intune выполнит автоматическую синхронизацию устройств ASM с Apple.

## <a name="create-an-apple-enrollment-profile"></a>Создание профиля регистрации Apple
Профиль регистрации устройства определяет параметры, применяемые к группе устройств в процессе регистрации.

1. На портале Intune выберите **Регистрация устройства**, а затем щелкните **Регистрация Apple**.
2. В разделе **Программа регистрации** щелкните **Профили программы регистрации**.
3. В колонке **Профили программы регистрации** щелкните **Создать**.
4. В колонке **Создание профиля регистрации** введите значения в поля **Имя** и **Описание** для профиля, который отображается на портале Intune.
5. В поле **Сходство пользователей** выберите, будут ли устройства с этим профилем регистрироваться со сходством пользователей или без него.

 - **Регистрация со сходством пользователей.** Устройство должно быть связано с пользователем во время начальной настройки, после чего оно может получить разрешение на доступ к корпоративным данным и электронной почте. Выберите сходство пользователей для управляемых устройств ASM, на которые пользователи входят с помощью своих управляемых идентификаторов Apple ID.

 >[!NOTE]
 >Многофакторная проверка подлинности (MFA) не работает во время проведения регистрации на устройствах ASM со сходством пользователей. После регистрации MFA работает на этих устройствах правильно.

  Чтобы использовать режим общего устройства iPad в рамках программы Apple School Manager, требуется регистрировать пользователей со сходством.

 >[!NOTE]
    >ASM со сходством пользователей требует включения [конечной точки WS-Trust 1.3 в режиме "Имя пользователя/Смешанный"](https://technet.microsoft.com/library/adfs2-help-endpoints) для запроса токена пользователя. [Подробнее о WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Регистрация без сходства пользователей.** Устройство не связано с пользователем. Используйте эту принадлежность для устройств, которые выполняют задачи без осуществления доступа к локальным данным пользователя. Приложения, для которых необходимо сходство пользователей (включая приложение корпоративного портала, используемое для установки бизнес-приложений), не будут работать.

6. Выберите **Параметры управления устройствами**. Эти элементы задаются во время активации и могут быть изменены только путем восстановления заводских настроек. Настройте следующие параметры профиля, после чего нажмите **Сохранить**:

    - **Защищено** — режим управления, который обеспечивает дополнительные возможности управления и отключает блокировку активации по умолчанию. Если оставить поле пустым, возможности управления будут ограничены.

    - **Регистрация заблокирована** (требуется выбрать режим управления "Защищено"). Отключает параметры iOS, которые делают возможным удаление профиля управления. Если не устанавливать флажок, это позволит удалить профиль управления из меню "Параметры".

  - **Общий iPad** (требуется выбор режима **Регистрация со сходством пользователей** и **Защищено**). Позволяет нескольким пользователям входить на зарегистрированные устройства iPad с помощью управляемого идентификатора Apple ID. Управляемые идентификаторы Apple ID создаются на портале Apple School Manager.

  >[!NOTE]
  >Если в профиле включен режим **Общий iPad**, после чего для режима **Сходство пользователей** или **Защищено** задано значение **Выкл.**, режим общего устройства iPad для профиля регистрации отключается.

  - **Максимальное число пользователей в кэше** (требуется выбрать **Общий iPad** = **Да**). Для каждого пользователя на устройстве создается отдельный раздел. Этому параметру рекомендуется присваивать значение, соответствующее числу учащихся, которые с большой вероятностью будут использовать это устройство в течение определенного периода времени. Например, если устройством регулярно пользуется шесть учащихся, присвойте этому параметру значение 6.  

    - **Разрешить связывание.** Указывает, могут ли устройства iOS синхронизироваться с компьютерами. Если выбрать **Разрешить конфигуратор Apple по сертификату**, необходимо выбрать сертификат в разделе **Apple Configurator Certificates** (Сертификаты конфигуратора Apple).

    - **Apple Configurator Certificates** (Сертификаты конфигуратора Apple). Если вы выбрали **Разрешить конфигуратор Apple по сертификату** в разделе **Разрешить связывание**, выберите импортируемый сертификат конфигуратора Apple.

7. Выберите **Параметры помощника по настройке**, настройте следующие параметры профиля, а затем нажмите кнопку **Сохранить**:

    - **Название отдела.** Отображается, когда пользователь выбирает пункт **About Configuration** (О конфигурации) во время активации.

    - **Телефон отдела.** Отображается, когда пользователь нажимает кнопку Need Help (Нужна помощь) во время активации.
    - **Параметры помощника установки**. Параметры, которые не заданы здесь, позднее можно установить в меню **Параметры** iOS.
        - **Секретный код** — запрашивать секретный код во время активации. Следует всегда требовать секретный код, если устройство не защищено другим способом или доступ к нему не управляется иным образом (например, режим терминала, который позволяет запускать на устройстве только одно приложение).
        - **Службы определения местоположения** — если включено, помощник по установке будет запрашивать параметры службы во время активации.
        - **Восстановление** — если включено, помощник по установке будет запрашивать параметры резервного копирования iCloud во время активации.
        - **Apple ID**. Если этот параметр включен, iOS будет запрашивать у пользователей идентификатор Apple ID, когда Intune попытается установить приложение без идентификатора. Идентификатор Apple ID необходим для загрузки приложений Магазина iOS App Store, включая те, которые были установлены с помощью Intune.
        - **Положения и условия** — если включено, помощник по установке предложит пользователям принять положения и условия Apple во время активации.
        - **Touch ID** — если включено, помощник по установке будет запрашивать параметры службы во время активации.
        - **Apple Pay** — если включено, помощник по установке будет запрашивать параметры службы во время активации.
        - **Zoom** — если включено, помощник по установке будет запрашивать параметры службы во время активации.
        - **Siri** — если включено, помощник по установке будет запрашивать параметры службы во время активации.
        - **Диагностические данные.** Если этот параметр включен, помощник по установке будет запрашивать параметры службы во время активации.

8. Чтобы сохранить параметры профиля, выберите **Создать** в колонке **Создать профиль регистрации**.

## <a name="connect-school-data-sync"></a>Подключение School Data Sync
ASM поддерживает синхронизацию данных списка класса с Azure Active Directory (AD) с помощью Microsoft School Data Sync (SDS) (необязательно). Чтобы синхронизировать сведения о школе с помощью SDS, выполните следующие действия.

1. В колонке **Токен программы регистрации** щелкните синий заголовок сведений или выберите **Подключить SDS**.
2. Присвойте параметру **Разрешить Microsoft School Data Sync использовать этот токен** значение **Разрешить**. Этот параметр разрешает Intune подключение к SDS в Office 365.
3. Чтобы разрешить подключение между ASM и Azure AD, выберите **Настроить Microsoft School Data Sync**. Дополнительные сведения о [настройке School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Нажмите кнопку **OK**, чтобы сохранить параметры и продолжить.

## <a name="sync-asm-managed-devices"></a>Синхронизация управляемых устройств ASM
Теперь, когда для Intune назначено разрешение на управление вашими устройствами ASM, можно синхронизировать Intune со службой ASM для просмотра управляемых устройств на портале Intune.

1. На портале Intune выберите **Регистрация устройства**, а затем щелкните **Регистрация Apple**.
2. В разделе **Устройства программы регистрации** выберите **Синхронизировать**. На индикаторе выполнения будет отображаться количество времени, которое должно пройти, прежде чем вы сможете повторно запросить синхронизацию.

    В соответствии с условиями Apple относительно допустимого трафика ASM Intune налагает следующие ограничения:
     -  Полная синхронизация ASM может выполняться не чаще одного раза в семь дней. Во время полной синхронизации Intune обновляет каждый серийный номер, назначенный Apple для Intune, независимо от его предыдущей синхронизации. При попытке выполнения полной синхронизации в течение семи дней с момента предыдущей полной синхронизации Intune обновит только те серийные номера, которые еще не указаны в Intune.
     -  Любой запрос синхронизации выполняется в течение 15 минут. В течение этого времени или до успешного завершения запроса кнопка **Синхронизировать** будет отключена.

>[!NOTE]
>Также вы можете назначить профилям серийные номера ASM в колонке **Устройства программы регистрации**.

## <a name="assign-an-asm-profile-to-devices"></a>Назначение профиля ASM устройствам
Устройства ASM под управлением Intune необходимо назначать профилю ASM до их регистрации.

1. На портале Intune выберите **Регистрация устройства** > **Регистрация Apple**, а затем **Профили программы регистрации**.
2. В списке **Профили программы регистрации** выберите профиль, который нужно назначить устройствам, а затем **Назначения устройств**.
3. Щелкните **Назначить**, а затем выберите устройства ASM, для которых необходимо назначить этот профиль. Можно установить фильтр для просмотра устройств, доступных для ASM:
  - **Неназначенные**
  - **Любые**
  - **&lt;Имя профиля ASM&gt;**
4. Выберите устройства, которые необходимо назначить. С помощью флажка над столбцом можно выбрать до 1000 устройств в списке. Щелкните **Назначить**. Чтобы зарегистрировать более 1000 устройств, повторите указанные действия, пока каждому устройству не будет назначен профиль ASM.

## <a name="distribute-devices-to-users"></a>Распределение устройств между пользователями

Теперь корпоративные устройства можно распределить между пользователями. При включении устройство ASM с iOS будет зарегистрировано для управления с помощью Intune. Если устройство было активировано и используется, невозможно применить профиль до восстановления заводских настроек устройства.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Установка и использование корпоративного портала на устройствах пользователей

Устройства, для которых настроено сопоставление с пользователем (сходство пользователей), могут установить и запустить приложение корпоративного портала для скачивания приложений и управления устройствами. Когда пользователи получают свои устройства, они должны запустить помощник по настройке и установить приложение корпоративного портала.