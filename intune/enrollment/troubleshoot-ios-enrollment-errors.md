---
title: Устранение проблем, возникающих при регистрации устройства с iOS или iPadOS в Microsoft Intune
titleSuffix: Microsoft Intune
description: Рекомендации по устранению распространенных проблем с регистрацией устройств с iOS или iPadOS в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: a29fab4be6e2046b2c6757505001a7ba3455b8d6
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514325"
---
# <a name="troubleshoot-iosipados-device-enrollment-problems-in-microsoft-intune"></a>Устранение проблем, возникающих при регистрации устройства с iOS или iPadOS в Microsoft Intune

С помощью сведений, приведенных в этой статье, администраторы Intune смогут понять и устранить проблемы, возникающие при регистрации устройств с iOS или iPadOS в Intune.

## <a name="prerequisites"></a>Предварительные условия

Перед устранением проблем необходимо собрать некоторые основные сведения. Благодаря им вы сможете лучше понять проблему и сократите время, затрачиваемое на поиск ее решения.

Соберите следующие сведения о проблеме:

- Какое именно сообщение об ошибке отображается?
- Где появилось сообщение об ошибке?
- Когда появилась проблема? Выполнена ли уже регистрация?
- На какой платформе (Android, iOS или iPadOS, Windows) возникла проблема?
- Сколько пользователей затронуто? Все ли пользователи затронуты или лишь некоторые из них?
- Сколько затронуто устройств? Все ли устройства затронуты или лишь некоторые из них?
- Что такое центр MDM?
- Как выполняется регистрация? В профилях регистрации используется программа "Принеси свое устройство" (BYOD) или Программа регистрации устройств (DEP) Apple?

## <a name="error-messages"></a>Сообщения об ошибках

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Сбой установки профиля. Произошла ошибка сети

**Причина.** На устройстве возникла неизвестная проблема с iOS или iPadOS.

#### <a name="resolution"></a>Решение

1. Чтобы предотвратить потерю данных при выполнении дальнейших шагов (во время восстановления iOS/iPadOS все данные на устройстве удаляются), обязательно создайте резервные копии данных.
2. Переведите устройство в режим восстановления, а затем выполните восстановление. Настройте его как новое устройство. Дополнительные сведения о восстановлении устройств с iOS/iPadOS см. на этой странице: [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Повторно зарегистрируйте устройство.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Сбой установки профиля. Не удается установить подключение к серверу

**Причина.** Клиент Intune разрешает использование лишь корпоративных устройств. 

#### <a name="resolution"></a>Решение
1. Войдите на портал Azure.
2. Щелкните **Больше служб**, а затем найдите и выберите **Intune**.
3. Выберите **Регистрация устройств** > **Ограничения регистрации**.
4. В разделе **Ограничения по типу устройства** выберите ограничение, которое необходимо задать. Для этого выберите **Свойства** > **Выбрать платформы**, а затем **Разрешить** для **iOS** и нажмите кнопку **ОК**.
5. Выберите **Настройка платформ**, установите флажок **Разрешить** для личных устройств с iOS или iPadOS и нажмите кнопку **ОК**.
6. Повторно зарегистрируйте устройство.

**Причина.** В службе доменных имен (DNS) отсутствуют необходимые записи CNAME.

#### <a name="resolution"></a>Решение
Создайте запись ресурсов CNAME DNS для домена вашей организации. Например, если ваша компания использует домен contoso.com, создайте в DNS запись CNAME, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com.

Несмотря на то, что создавать записи CNAME в DNS не обязательно, записи CNAME позволяют упростить регистрацию для пользователей. Если запись CNAME для регистрации не обнаружена, пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

Если у вас есть несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

|ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
|------|------|------|------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com|1 ч|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 ч|

Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

> [!NOTE]
> Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

**Причина.** Регистрируемое устройство ранее зарегистрировано в другой учетной записи пользователя, и предыдущий пользователь удален из Intune несоответствующим образом.

#### <a name="resolution"></a>Решение
1. Отмените все текущие профильные установки.
2. Откройте ссылку [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) в Safari.
3. Повторно зарегистрируйте устройство.

> [!NOTE]
> Если регистрация по-прежнему завершается сбоем, удалите файлы cookie в Safari (не блокируйте их), а затем повторно зарегистрируйте устройство.

**Причина.** Устройство уже зарегистрировано у другого поставщика MDM.

#### <a name="resolution"></a>Решение
1. Откройте на устройстве с iOS или iPadOS раздел **Settings** (Параметры) и перейдите к разделу **General > Device Management** (Общие > Управление устройством).
2. Удалите все имеющиеся профили управления.
3. Повторно зарегистрируйте устройство.

**Причина.** У пользователя, пытающегося зарегистрировать устройство, нет лицензии Microsoft Intune.

#### <a name="resolution"></a>Решение
1. Перейдите в [Центр администрирования Office 365](https://portal.office.com/adminportal/home#/homepage), а затем выберите элементы **Пользователи > Активные пользователи**.
2. Выберите учетную запись пользователя, которой требуется назначить лицензию пользователя Intune, и щелкните **Лицензии на продукты > Изменить**.
3. Переведите переключатель для лицензии, которую необходимо назначить этому пользователю, в положение **Вкл.** , а затем нажмите кнопку **Сохранить**.
4. Повторно зарегистрируйте устройство.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Эта служба не поддерживается. Нет политики регистрации

**Причина.** Сертификат Apple MDM Push Certificate не настроен в Intune или же он недействителен. 

#### <a name="resolution"></a>Решение

- Если сертификат MDM Push Certificate не настроен, выполните действия, указанные в [этом разделе](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Если сертификат MDM Push Certificate недействителен, выполните действия, указанные в [этом разделе](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Корпоративный портал временно недоступен В приложении "Корпоративный портал" возникла проблема. Если проблема повторится, обратитесь к системному администратору.

**Причина.** Приложение "Корпоративный портал" устарело или повреждено.

#### <a name="resolution"></a>Решение
1. Удалите приложение корпоративного портала с устройства.
2. Скачайте и установите **приложение корпоративного портала Microsoft Intune** из **App Store**.
3. Повторно зарегистрируйте устройство.
 > [!NOTE]
    > Эта ошибка также может возникать, если пользователь пытается зарегистрировать больше устройств, чем разрешено. Если описанные действия не помогли устранить ошибку, выполните рекомендации по разрешению проблемы **Достигнут предел для устройств**.

### <a name="device-cap-reached"></a>Достигнут предел для устройств

**Причина.** Пользователь пытается зарегистрировать больше устройств, чем предусмотрено пределом для регистрации устройств.

#### <a name="resolution"></a>Решение
1. В [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) выберите элементы **Устройства** > **Все устройства** и проверьте количество зарегистрированных пользователем устройств.
    > [!NOTE]
    > Кроме того, затронутый пользователь должен войти на [портал пользователя Intune](https://portal.manage.microsoft.com/) и проверить зарегистрированные устройства там. Некоторые устройства, не отображающиеся на [портале администрирования Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview), могут отображаться на [портале пользователя Intune](https://portal.manage.microsoft.com/). Такие устройства также учитываются при определении достижения предела для регистрации устройств.
2. В [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) выберите элементы **Устройства** > **Ограничения регистрации** и проверьте предел для регистрации устройств. По умолчанию это число не может быть больше 15. 
3. Если число зарегистрированных устройств достигло предела, удалите ненужные устройства или увеличьте предел для регистрации устройств. Каждое зарегистрированное устройство использует лицензию Intune, поэтому рекомендуется всегда удалять ненужные устройства в первую очередь.
4. Повторно зарегистрируйте устройство.

### <a name="workplace-join-failed"></a>Сбой подключения к рабочему месту

**Причина.** Приложение "Корпоративный портал" устарело или повреждено.  

#### <a name="resolution"></a>Решение
1. Удалите приложение корпоративного портала с устройства.
2. Скачайте и установите **приложение корпоративного портала Microsoft Intune** из **App Store**.
3. Повторно зарегистрируйте устройство.

### <a name="user-license-type-invalid"></a>Недействующий тип лицензии пользователя

**Причина.** У пользователя, пытающегося зарегистрировать устройство, нет действующей лицензии Intune.

#### <a name="resolution"></a>Решение
1. Перейдите в [Центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage), а затем выберите элементы **Пользователи** > **Активные пользователи**.
2. Последовательно выберите затронутую учетную запись пользователя, **Product licenses**(Лицензии на продукты)  > **Изменить**.
3. Убедитесь, что этому пользователю назначена действующая лицензия Intune.
4. Повторно зарегистрируйте устройство.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Имя пользователя не распознано Этой учетной записи пользователя не разрешено использовать Microsoft Intune. Если вы считаете, что получили данное сообщение по ошибке, обратитесь к системному администратору.

**Причина.** У пользователя, пытающегося зарегистрировать устройство, нет действующей лицензии Intune.

1. Перейдите в [Центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage), а затем выберите элементы **Пользователи** > **Активные пользователи**.
2. Последовательно выберите затронутую учетную запись пользователя, **Product licenses**(Лицензии на продукты)  > **Изменить**.
3. Убедитесь, что этому пользователю назначена действующая лицензия Intune.
4. Повторно зарегистрируйте устройство.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Сбой установки профиля. Новые полезные данные MDM не соответствуют старым.

**Причина.** Профиль управления уже установлен на устройстве.

#### <a name="resolution"></a>Решение

1. Откройте на устройстве с iOS или iPadOS раздел **Settings (Параметры)** **General (Общие)**  > **Device Management (Управление устройствами)** .
2. Коснитесь имеющегося профиля управления и нажмите кнопку **Remove Management** (Удалить управление).
3. Повторно зарегистрируйте устройство.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Причина.** Сертификат Службы push-уведомлений Apple (APNs) отсутствует, недействителен или просрочен.

#### <a name="resolution"></a>Решение
Убедитесь, что в Intune добавлен действующий сертификат APNs. Дополнительные сведения см. в статье [Enroll iOS/iPadOS devices in Intune](ios-enroll.md) (Регистрация устройствiOS/iPadOS в Intune).

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Причина.** С сертификатом APNs, настроенным в Intune, возникла проблема.

#### <a name="resolution"></a>Решение
Продлите сертификат APNs, а затем повторно зарегистрируйте устройство.

> [!IMPORTANT]
> Убедитесь, что сертификат APNs продлен. Не заменяйте сертификат APNs. При замене сертификата необходимо повторно регистрировать в Intune все устройства с iOS/iPadOS. 

- Сведения о продлении сертификата APNs в автономной службе Intune см. в разделе [Продление сертификата Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Сведения о продлении сертификата APNs в Office 365 см. в статье [Создание сертификата APNs для устройств с iOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>Недопустимое подключение XPC_TYPE_ERROR

При включении устройства под управлением DEP, которому назначен профиль регистрации, регистрация завершается сбоем и отображается следующее сообщение об ошибке:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Причина.** Возникла проблема с подключением между устройством и службой Apple DEP.

#### <a name="resolution"></a>Решение
Устраните проблему с подключением или используйте для регистрации устройства другое сетевое подключение. Если проблема повторится, возможно, потребуется обратиться в службу поддержки Apple.


## <a name="other-issues"></a>Другие проблемы

### <a name="dep-enrollment-doesnt-start"></a>Регистрация DEP не запускается
При включении устройства под управлением DEP, которому назначен профиль регистрации, процесс регистрации в Intune не инициируется.

**Причина.** Профиль регистрации создается до передачи токена DEP в Intune.

#### <a name="resolution"></a>Решение

1. Измените профиль регистрации. Вы можете внести в профиль любые изменения. Это действие необходимо для обновления времени изменения профиля.
2. Синхронизация устройств под управлением DEP. В [Центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) выберите **Устройства** > **iOS** > **Регистрация iOS** > **Токены программы регистрации**, а затем выберите токен в списке и **Синхронизировать**. Запрос на синхронизацию будет отправлен в Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>Регистрация DEP зависла на этапе входа пользователя в систему
При включении устройства под управлением DEP, которому назначен профиль регистрации, первоначальная настройка не продолжается после ввода учетных данных.

**Причина.** Включена многофакторная проверка подлинности (MFA). Сейчас MFA не выполняется во время регистрации на устройствах DEP.

#### <a name="resolution"></a>Решение
Отключите MFA, а затем повторно зарегистрируйте устройство.


## <a name="next-steps"></a>Дальнейшие шаги

- [Устранение проблем при регистрации устройств в Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Задайте вопрос на форуме Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [См. блог группы поддержки Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [См. блог разработчиков Microsoft Enterprise Mobility + Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
