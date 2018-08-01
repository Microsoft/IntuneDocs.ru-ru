---
title: Регистрация киосков Android для бизнеса в Intune
titlesuffix: Microsoft Intune
description: Узнайте, как зарегистрировать киоски Android для бизнеса в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5a223834eed1b0174c56b5e33ad2140203073d0
ms.sourcegitcommit: 5251a630fb2c7a2e6f86abd84ab887f8eabc1481
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39212041"
---
# <a name="set-up-enrollment-of-android-enterprise-kiosk-devices"></a>Настройка регистрации киосков Android для бизнеса

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android поддерживает устройства-киоски за счет собственного набора решений для корпоративных однофункциональных устройств ("Corporate-Owned, Single-Use", COSU). Такие устройства используются для одной цели, например для цифровой подписи, печати билетов, управления запасами и т. д. Администраторы ограничивают работу устройства, разрешая использовать ограниченный набор приложений и веб-ссылок. Пользователи не могут добавлять другие приложения или выполнять другие операции на устройстве.

Intune помогает развертывать приложения и параметры в киосках Android. Дополнительные сведения об Android для бизнеса см. в разделе [Требования Android для бизнеса](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Устройства, которыми вы управляете таким образом, регистрируются в Intune без учетной записи пользователя и не привязаны к конечному пользователю. Они не предназначены для персональных приложений или приложений, где требуются данные конкретного пользователя, например Outlook или Gmail.

## <a name="device-requirements"></a>Требования к устройствам

Устройства должны удовлетворять следующим требованиям, чтобы ими можно было управлять как киосками Android:

- ОС Android версии 5.1 и более поздних версий.
- Устройства должны иметь версию Android с подключением к Google Mobile Services (GMS). Устройства должны иметь доступ к GMS и возможность подключиться к GMS.

## <a name="set-up-android-kiosk-management"></a>Настройка управления киоском Android

Чтобы настроить управление киоском Android, выполните следующие действия:

1. Чтобы подготовиться к управлению мобильными устройствами, нужно [установить **Microsoft Intune** в качестве службы управления мобильными устройствами (MDM)](mdm-authority-set.md) для получения инструкций. Этот параметр указывается только один раз при первой настройке Intune для управления мобильными устройствами.
2. [Подключите учетную запись Intune к учетной записи Android для бизнеса](connect-intune-android-enterprise.md).
3. [Создание профиля регистрации.](#create-an-enrollment-profile)
4. [Создание группы устройств](#create-a-device-group).
5. [Регистрация киосков](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Создание профиля регистрации

Необходимо создать профиль регистрации, чтобы зарегистрировать киоски. При создании профиля вы получаете токен регистрации (случайная строка) и QR-код. В зависимости от версии Android и устройства вы можете использовать токен или QR-код для [регистрации киоска](#enroll-the-kiosk-devices).

1. Перейдите на [портал Intune](https://portal.azure.com) и выберите **Регистрация устройства** > **Регистрация Android** > **Регистрация устройств для киосков и задач**.
2. Выберите **Создать** и заполните обязательные поля.
    - **Имя**. Введите имя, которое будет использоваться при назначении профиля динамической группе устройств.
    - **Срок действия токена**. Дата, когда истекает срок действия токена. По требованию Google этот период составляет не более 30 дней.
3. Выберите **Создать**, чтобы сохранить профиль.

### <a name="create-a-device-group"></a>Создание группы устройств

Вы можете выбирать приложения и политики для назначенных или динамических групп устройств. Вы можете настроить динамические группы устройств AAD на автоматическое добавление устройств, зарегистрированных с определенным профилем регистрации, выполнив следующие действия:

1. Перейдите на [портал Intune](https://portal.azure.com) и выберите **Группы** > **Все группы** > **Создать группу**.
2. В колонке **Группа** заполните обязательные поля следующим образом:
    - **Тип группы**: безопасность
    - **Имя группы**: введите интуитивно понятное имя (например, "Устройства фабрики 1")
    - **Тип членства**: динамическое устройство
3. Выберите **Добавить динамический запрос**.
4. В колонке **Правила динамического членства** заполните поля следующим образом:
    - **Добавить правило динамического членства**: простое правило
    - **Место добавления устройств**: enrollmentProfileName
    - В среднем поле выберите **Соответствие**.
    - В последнем поле введите имя профиля регистрации, который был создан ранее.
5. Выберите **Добавить запрос** > **Создать**.

### <a name="replace-or-remove-tokens"></a>Замена или удаление токенов

Вы можете заменить или удалить токены и QR-коды.

- **Заменить токен**. Вы можете создать новый токен или QR-код, когда срок действия почти истек, с помощью опции "Заменить токен".
- **Отменить токен**. Вы можете незамедлительно прекратить действие токена или QR-кода. С этого момента токен или QR-код будут недействительны. Эту опцию можно использовать, если вы:
    - случайно предоставили токен или QR-код постороннему лицу;
    - завершили все регистрации и вам не нужен токен или QR код.

Замена или отмена токена или QR-кода не повлияет на уже зарегистрированные устройства.

1. Перейдите на [портал Intune](https://portal.azure.com) и выберите **Регистрация устройства** > **Регистрация Android** > **Регистрация устройств для киосков и задач**.
2. Выберите нужный профиль.
3. Выберите **Токен**.
4. Чтобы заменить токен, нажмите **Заменить токен**.
5. Чтобы отменить токен, нажмите **Отменить токен**.

## <a name="enroll-the-kiosk-devices"></a>Регистрация киосков

После создания профиля регистрации и динамической группы устройств вы можете зарегистрировать свои киоски. Метод регистрации устройств Android зависит от операционной системы.

| Метод регистрации | Минимальная поддерживаемая версия ОС Android |
| ----- | ----- |
| NFC | 5.1 |
| Запись токена | 6.0 |
| QR-код | 7.0 |
| Zero Touch | 8.0, некоторые производители |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Регистрация с помощью NFC

Для устройств с Android 5.1 и более поздних версий с поддержкой NFC вы можете подготовить устройства, создав специально отформатированный тег NFC. Вы можете использовать собственное приложение или любой инструмент создания тегов NFC. Дополнительные сведения см. в [документации по API управления в Google Android](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Регистрация с помощью токена

Для устройств с Android 6 и более поздних версий можно использовать токен для регистрации устройства.

1. Включите устройство после восстановления заводских настроек.
2. На экране **приветствия** выберите язык.
3. Подключитесь к **Wi-Fi** и нажмите **ДАЛЕЕ**.
4. Примите условия Google и нажмите **ДАЛЕЕ**.
5. На экране входа в Google введите **afw#setup** вместо учетной записи Gmail, а затем нажмите **ДАЛЕЕ**.
6. Выберите **УСТАНОВИТЬ** для приложения **Политика для устройств Android**.
7. Продолжайте установку этой политики.  Для некоторых устройств придется принять дополнительные условия. 
8. На экране **Зарегистрировать это устройство** разрешите устройству отсканировать QR-код или введите токен вручную.
9. Следуйте указаниям на экране, чтобы завершить регистрацию. 

### <a name="enroll-by-using-a-qr-code"></a>Регистрация с помощью QR-кода

На устройствах Android 7 и более поздних версий вы можете отсканировать QR-код из профиля регистрации для регистрации устройства.

1. Чтобы запустить считывание QR-кода на устройстве Android, несколько раз коснитесь первого экрана, который откроется после сброса.
2. На устройствах с Android 7 или 8 вам будет предложено установить сканер QR-кодов. На устройствах с Android 9 и более поздних версий уже установлен сканер QR-кодов.
3. Сканером QR-кодов отсканируйте QR-код в профиле регистрации и следуйте инструкциям на экране для регистрации.

### <a name="enroll-by-using-google-zero-touch"></a>Регистрация с помощью Google Zero Touch

Чтобы использовать систему Google Zero Touch, устройство должно поддерживать ее и быть связано с поставщиком, который поставляет услугу.  Дополнительные сведения см. на [веб-сайте программы Google Zero Touch](https://www.android.com/enterprise/management/zero-touch/). 


1. Создайте новую конфигурацию в консоли Zero Touch.
2. Выберите **Microsoft Intune** из раскрывающегося списка EMM DPC.
3. В консоли Google Zero Touch скопируйте и вставьте приведенный ниже JSON в поле дополнений DPC. Замените сроку *YourEnrollmentToken* токеном регистрации, полученным при создании профиля регистрации. Не забудьте заключить токен регистрации в двойные кавычки.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. Нажмите кнопку **Применить**.

## <a name="managing-apps-on-android-kiosk-devices"></a>Управление приложениями в киосках Android

В киосках Android можно устанавливать только приложения с типом назначения [Обязательно](apps-deploy.md#to-assign-an-app). Приложения устанавливаются из управляемого Google Play так же, как на устройствах с рабочим профилем Android.

Приложения обновляются автоматически на управляемых устройствах, когда разработчик приложения публикует обновление в Google Play.

Чтобы удалить приложение из киоска Android, выполните одно из следующих действий:
-   Удалите развертывание обязательного приложения.
-   Создайте развертывание удаления для приложения.


## <a name="next-steps"></a>Дальнейшие шаги
- [Развертывание приложений в киосках Android](apps-deploy.md)
- [Добавление политик конфигурации для киосков Android](device-profiles.md)