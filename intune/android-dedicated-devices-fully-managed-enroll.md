---
title: Регистрация выделенных или полностью управляемых устройств с Android в Intune
titlesuffix: Microsoft Intune
description: Сведения о регистрации выделенных или полностью управляемых корпоративных устройств с Android в Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 0eb12470c20efd8d455f8bb165455ae4266da956
ms.sourcegitcommit: 2a1720184cec577684a64af85d0d731693d11d81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2019
ms.locfileid: "55146899"
---
# <a name="enroll-your-android-dedicated-devices-or-fully-managed-devices-preview"></a>Регистрация выделенных или полностью управляемых устройств с Android (предварительная версия)

После настройки [выделенных устройств с Android](android-kiosk-enroll.md) или [полностью управляемых устройств](android-fully-managed-enroll.md) в Intune вы можете зарегистрировать устройства. Метод регистрации устройств Android зависит от операционной системы.

| Метод регистрации | Минимальная версия ОС Android для выделенного и полностью управляемого устройства |
| ----- | ----- |
| NFC | 5.1 |
| Запись токена | 6.0 |
| QR-код | 7.0 |
| Zero Touch  | 8.0\* |

\*, участвующие в программе производители.

### <a name="enroll-by-using-near-field-communication-nfc"></a>Регистрация с помощью NFC

Для устройств с поддержкой NFC вы можете подготовить устройства, создав специально отформатированный тег NFC. Вы можете использовать собственное приложение или любой инструмент создания тегов NFC. Дополнительные сведения см. в разделе [Регистрация устройств с Android на базе C для бизнеса с помощью Microsoft Intune](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) и [документации Google по API управления Android](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Регистрация с помощью токена

Для устройств с Android 6 и более поздних версий можно использовать токен для регистрации устройства. Android 6.1 и более поздних версий также может сканировать QR-код при использовании метода регистрации **afw#setup**.

1. Включите очищенное устройство.
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

> [!Note]
> Масштаб в браузере может помешать устройствам сканировать QR-код. Увеличьте масштаб в браузере, чтобы решить проблему.

1. Чтобы запустить считывание QR-кода на устройстве Android, несколько раз коснитесь первого экрана, который откроется после очистки.
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


## <a name="next-steps"></a>Дальнейшие шаги
- [Развертывание приложений Android](apps-deploy.md)
- [Добавление политик конфигурации Android](device-profiles.md)

