---
title: Устранение проблем с регистрацией устройств iOS в Microsoft Intune
titleSuffix: Microsoft Intune
description: Рекомендации по устранению некоторых наиболее распространенных проблем при регистрации устройств iOS в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7c7ec23d0408aa4d4cf81baff2d7cdf749fb65e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509228"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Устранение проблем с регистрацией устройств iOS в Microsoft Intune

Эта статья поможет администраторам Intune понять и устранить проблемы при регистрации устройств iOS в Intune.

## <a name="prerequisites"></a>Предварительные условия

Прежде чем начать устранение неполадок, важно получить некоторые основные сведения. Эти сведения помогут вам лучше понять проблему и сократить время поиска решения.

Собирайте следующие сведения о проблеме:

- Какое именно сообщение об ошибке отображается?
- Где появилось сообщение об ошибке?
- Когда появилась проблема? Уже выполнялась ли регистрация?
- На какой платформе (Android, iOS, Windows) возникла проблема?
- Сколько пользователей затронуты? Все ли пользователи затронули или только некоторые из них?
- Сколько затронутых устройств? Затрагиваются ли все устройства или только некоторые из них?
- Что такое центр MDM? Если System Center Configuration Manager, какая версия Configuration Manager используется?
- Как выполняется регистрация? Это "присвоить свое устройство" (BYOD) или Apple Программа регистрации устройств (DEP) с профилями регистрации?

## <a name="error-messages"></a>Сообщения об ошибках

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Сбой установки профиля. Произошла ошибка сети

**Причина:** На устройстве возникла неопределенная проблема с iOS.

#### <a name="resolution"></a>Решение

1. Чтобы предотвратить потери данных в следующих шагах (при восстановлении iOS удаляются все данные на устройстве), обязательно создайте резервные копии данных.
2. Переведите устройство в режим восстановления, а затем восстановите его. Убедитесь, что вы настроили его как новое устройство. Дополнительные сведения о восстановлении устройств iOS см. в разделе [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Повторно зарегистрируйте устройство.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Сбой установки профиля. Не удается установить подключение к серверу

**Причина:** Клиент Intune настроен на предоставление только корпоративных устройств. 

#### <a name="resolution"></a>Решение
1. Войдите на портал Azure.
2. Щелкните **Больше служб**, а затем найдите и выберите **Intune**.
3. Выберите **Регистрация устройств** > **Ограничения регистрации**.
4. В разделе **ограничения типа устройства**выберите ограничение, которое необходимо задать > **свойства**  > **выберите платформы** > выберите **Разрешить** для **iOS**, а затем нажмите кнопку **ОК**.
5. Щелкните **Настройка платформ**, выберите **Разрешить** для личных устройств iOS, а затем нажмите кнопку **ОК**.
6. Повторно зарегистрируйте устройство.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Эта служба не поддерживается. Нет политики регистрации

**Причина**: сертификат Apple MDM Push Certificate не настроен в Intune, или сертификат недействителен. 

#### <a name="resolution"></a>Решение

- Если MDM Push Certificate не настроен, выполните действия, описанные в статье [Получение сертификата Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Если сертификат MDM Push Certificate является недопустимым, выполните действия, описанные в разделе [продление сертификата Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Корпоративный портал временно недоступен В приложении корпоративный портал возникла проблема. Если проблема повторится, обратитесь к системному администратору.

**Причина:** Корпоративный порталное приложение устарело или повреждено.

#### <a name="resolution"></a>Решение
1. Удалите приложение корпоративного портала с устройства.
2. Скачайте и установите **приложение корпоративного портала Microsoft Intune** из **App Store**.
3. Повторно зарегистрируйте устройство.

### <a name="device-cap-reached"></a>Достигнут предел для устройств

**Причина:** Пользователь пытается зарегистрировать больше устройств, чем ограничение регистрации устройств.

#### <a name="resolution"></a>Решение
1. Откройте [портал администрирования Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)  > **устройства**  > **все устройства**и проверьте число устройств, зарегистрированных пользователем.
    > [!NOTE]
    > Кроме того, необходимо иметь затронутого входа пользователя на [портал пользователя Intune](https://portal.manage.microsoft.com/) и проверить зарегистрированные устройства. Могут существовать устройства, которые отображаются на портале [пользователя Intune](https://portal.manage.microsoft.com/) , но не на [портале администрирования Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). такие устройства также подсчитывает ограничения на регистрацию устройств.
2. Перейдите в раздел **администратор**  > **Управление мобильными устройствами**  > **правила регистрации** > Проверьте предел регистрации устройств. По умолчанию это число не может быть больше 15. 
3. Если число зарегистрированных устройств достигло предела, удалите ненужные устройства или увеличьте предел регистрации устройства. Так как каждое зарегистрированное устройство использует лицензию Intune, рекомендуется всегда удалять ненужные устройства первыми.
4. Повторно зарегистрируйте устройство.

### <a name="workplace-join-failed"></a>Сбой Workplace Join

**Причина:** Корпоративный порталное приложение устарело или повреждено.  

#### <a name="resolution"></a>Решение
1. Удалите приложение корпоративного портала с устройства.
2. Скачайте и установите **приложение корпоративного портала Microsoft Intune** из **App Store**.
3. Повторно зарегистрируйте устройство.

### <a name="user-license-type-invalid"></a>Недопустимый тип лицензии пользователя

**Причина:** У пользователя, пытающегося зарегистрировать устройство, нет действующей лицензии Intune.

#### <a name="resolution"></a>Решение
1. Перейдите в [центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage), а затем выберите **Пользователи**  > **Активные пользователи**.
2. Выберите затронутую учетную запись пользователя > **лицензий продукта**  > **изменить**.
3. Убедитесь, что этому пользователю назначена действительная лицензия Intune.
4. Повторно зарегистрируйте устройство.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Имя пользователя не распознано Эта учетная запись пользователя не имеет права использовать Microsoft Intune. Если вы считаете, что получили это сообщение по ошибке, обратитесь к системному администратору.

**Причина:** У пользователя, пытающегося зарегистрировать устройство, нет действующей лицензии Intune.

1. Перейдите в [центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage), а затем выберите **Пользователи**  > **Активные пользователи**.
2. Выберите затронутую учетную запись пользователя, а затем выберите **лицензии продукта**  > **изменить**.
3. Убедитесь, что этому пользователю назначена действительная лицензия Intune.
4. Повторно зарегистрируйте устройство.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Сбой установки профиля. Новые полезные данные MDM не соответствуют старым полезным данным.

**Причина:** Профиль управления уже установлен на устройстве.

#### <a name="resolution"></a>Решение

1. Откройте **Параметры** на устройстве IOS > **Общие**  > **Управление устройствами**.
2. Выберите существующий профиль управления и нажмите кнопку **Удалить управление**.
3. Повторно зарегистрируйте устройство.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Причина:** Сертификат Cлужба push-уведомлений Apple (APNs) отсутствует, недопустим или просрочен.

#### <a name="resolution"></a>Решение
Убедитесь, что в Intune добавлен действительный сертификат APNs. Дополнительные сведения см. в статье [Регистрация устройств с iOS в Intune](https://docs.microsoft.com/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune). 

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Причина:** Возникла проблема с сертификатом службы push-уведомлений Apple (APNs), настроенным в Intune.

#### <a name="resolution"></a>Решение
Продлите сертификат APNs, а затем повторно зарегистрируйте устройство.

> [!IMPORTANT]
> Убедитесь, что сертификат APNs продлен. Не заменяйте сертификат APNs. При замене сертификата необходимо повторно зарегистрировать все устройства iOS в Intune. 

- Сведения об обновлении сертификата APNs в автономной системе Intune см. в статье [продление срока действия сертификата Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Сведения об обновлении сертификата APNs в гибридной службе Intune с Configuration Manager см. в статье [Настройка гибридного управления устройствами iOS с помощью System Center Configuration Manager и Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac).
- Сведения об обновлении сертификата APNs в Office 365 см. в статье [Создание сертификата APNs для устройств iOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>Недопустимое подключение XPC_TYPE_ERROR

При включении устройства под управлением DEP, которому назначен профиль регистрации, регистрация завершается сбоем и появляется следующее сообщение об ошибке:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Причина:** Между устройством и службой Apple DEP возникает ошибка подключения.

#### <a name="resolution"></a>Решение
Устраните проблему с подключением или используйте другое сетевое подключение для регистрации устройства. Вам также может потребоваться обратиться в Apple, если проблема будет повторяться.


## <a name="other-issues"></a>Другие проблемы

### <a name="dep-enrollment-doesnt-start"></a>Регистрация DEP не запускается
При включении устройства, управляемого DEP, которому назначен профиль регистрации, процесс регистрации Intune не инициируется.

**Причина:** Профиль регистрации создается до передачи токена DEP в Intune.

#### <a name="resolution"></a>Решение

1. Изменение профиля регистрации. Можно внести любые изменения в профиль. Целью является обновление времени изменения профиля.
2. Синхронизация устройств, управляемых DEP. Откройте портал Intune > **администратор**  > **Управление мобильными устройствами**  > **iOS**  > **Программа регистрации устройств**  > **синхронизировать**. Запрос на синхронизацию будет отправлен в Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>Регистрация DEP была задержана при входе пользователя
При включении устройства под управлением DEP, которому назначен профиль регистрации, начальная настройка фиксируется после ввода учетных данных.

**Причина:** Многофакторная проверка подлинности (MFA) включена. В настоящее время MFA не работает во время регистрации на устройствах с DEP.

#### <a name="resolution"></a>Решение
Отключите MFA, а затем повторно зарегистрируйте устройство.

## <a name="next-steps"></a>Дальнейшие шаги

- [Устранение проблем при регистрации устройств в Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Задайте вопрос на форуме Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Обратитесь к блогу группы поддержки Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Ознакомьтесь с блогом Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
