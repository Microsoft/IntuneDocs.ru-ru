---
title: "Заметки о выпуске Microsoft Intune | Документы Майкрософт"
description: "Заметки о выпуске Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0e027d1c63435084c434c591fed7bb71b5c07f2
ms.openlocfilehash: 8369cc039ac1c4c24b29927a96360cd872f8e9bc
ms.lasthandoff: 03/08/2017


---

# <a name="release-notes-for-microsoft-intune"></a>Заметки о выпуске Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune — это интегрированное, основанное на облаке решение для управления клиентами, которое включает средства, отчеты и лицензии на обновление до последних версий Windows. Оно также обеспечивает защиту и обновление компьютеров. Кроме того, благодаря Intune вы можете управлять мобильными устройствами внутри вашей сети с помощью Exchange ActiveSync или напрямую посредством Intune. В следующих заметках о выпуске содержатся важные сведения об известных проблемах, которые возникают в службе Microsoft Intune.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>Изменение профилей доступа к ресурсам между группами для iOS и Android может завершиться ошибкой
**Проблема.** При изменении профилей доступа к ресурсам для электронной почты или SCEP между группами эти профили могут конфликтовать и вызывать ошибку. Предположим, что имеется профиль электронной почты, указывающий на локальный сервер Exchange и нацеленный на группу А, а затем создается профиль электронной почты, указывающий на Exchange Online и нацеленный на группу Б. При перемещении пользователей из группы А в группу Б устройства сохраняют профиль электронной почты локальной версии Exchange и пробуют установить профиль электронной почты Exchange Online, нацеленный на группу Б.

При этом происходит одно из следующих событий: 
* Если профили электронной почты А и Б являются идентичными, устройство отклоняет профиль электронной почты Б, так как он уже содержит профиль A.
* Если профиль А отличается от профиля Б, как упоминалось в предыдущем примере, на устройстве появляется два профиля электронной почты.

> [!NOTE]
> Чтобы отличить один профиль электронной почты от другого, проверяется имя узла и атрибут, используемый для имени пользователя.

В обоих случаях профиль доступа к ресурсам (профиль электронной почты) не был удален с устройства во избежание непреднамеренного отключения доступа пользователя к электронной почте или удаления сертификата SCEP клиента.

**Обходной путь:** нет.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>При регистрации устройства Windows 8.1, которое должно пройти проверку подлинности на прокси-сервере, процесс регистрации завершается ошибкой без видимой причины сбоя
**Проблема:** при регистрации устройства на базе Windows 8.1 , которое во время этого процесса должно пройти проверку подлинности на прокси-сервере, возникает ошибка, если устройство не выполнило кэширование учетных данных прокси-сервера. Если учетные данные прокси-сервера не кэшированы на устройстве, процесс регистрации будет продолжен только после ввода учетных данных пользователем. Однако запрос на ввод учетных данных прокси-сервера во время процесса регистрации не выводится. Получается, что процессу регистрации не удается пройти проверку подлинности на прокси-сервере. Для пользователя причина этого сбоя никаким образом не отображается.

**Обходной путь.** Для устройств на базе Windows 8.1, которые следует зарегистрировать в сети, требующей использования прошедшего проверку прокси-сервера, настройте и сохраните учетные данные для прокси-сервера до регистрации устройства. Чтобы настроить и сохранить учетные данные на устройстве с Windows 8.1, выполните следующие действия.

1.  На устройстве с Windows 8.1 откройте браузер Internet Explorer.
2.  При запросе на ввод учетных данных прокси-сервера введите нужные данные и установите флажок **Запомнить учетные данные**.
3.  Зарегистрируйте устройство.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>Устройства Windows Phone 8.1 не могут зарегистрироваться в Microsoft Intune, если в AD FS включена проверка подлинности устройства
**Проблема.** При регистрации устройства Windows Phone 8.1 возникает сбой, если необязательный параметр для проверки подлинности устройства включен в рамках глобальной политики поверки подлинности в службах федерации Active Directory (AD FS).

**Обходной путь:** отключите проверку подлинности устройств на сервере служб федерации Active Directory, сняв флажок **Enable device authentication** (Включить проверку подлинности устройств) в области **Edit Global Authentication Policy**(Изменение глобальной политики проверки подлинности). Дополнительные сведения см. в статье [Настройка политик проверки подлинности](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>Инструмент упаковки приложений Microsoft Intune для Android не имеет встроенной возможности удаления
**Проблема:** **инструмент упаковки приложений Майкрософт для Android** не имеет встроенных функциональных возможностей для удаления этого средства.

**Обходной путь:** перейдите к расположению, куда был установлен инструмент, и удалите этот каталог. По умолчанию используется расположение установки **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Дополнительные сведения об инструменте упаковки приложений см. в статье [Подготовка приложений Android для управления мобильными приложениями с помощью инструмента упаковки для приложений Microsoft Intune](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Удаленная помощь недоступна на компьютерах под управлением Windows 8 или Windows 8.1
**Проблема:** в этом выпуске функция удаленной помощи не доступна на компьютерах под управлением Windows 8 или Windows 8.1.

**Обходной путь:** нет.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Уведомления об оповещениях могут не отправляться для получателей, добавленных автоматически
**Проблема.** При автоматическом добавлении получателей в уведомление об оповещениях они могут не всегда получать такие уведомления.

**Обходной путь.** Чтобы гарантировать получение уведомлений получателями, необходимо вручную добавлять получателей уведомления об оповещении в список.

## <a name="language-support-in-the-azure-portal"></a>Языковая поддержка на портале Azure
Портал Azure поддерживает следующие языки: китайский (упрощенное письмо), китайский (традиционное письмо), чешский, нидерландский, английский, немецкий, венгерский, итальянский, японский, португальский (Бразилия), португальский (Португалия), русский, испанский, английский, французский, корейский, польский, шведский, турецкий.

Консоль администрирования Intune и мобильный пользовательский интерфейс в дополнение ко всем языкам портала Azure поддерживают датский, греческий, финский, норвежский и румынский языки.

