---
title: Подключите учетную запись Intune к учетной записи управляемого Google Play.
titleSuffix: Microsoft Intune
description: Узнайте, как подключить учетную запись Intune к учетной записи управляемого Google Play.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 581d88e49391bc874625e9c84318c039706b0c1b
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124832"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Подключение учетной записи Intune к учетной записи управляемого Google Play

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Для поддержки устройств с [рабочим профилем Android для бизнеса ](android-work-profile-enroll.md), [полностью управляемых устройств с Android](android-fully-managed-enroll.md) и [выделенных устройств с Android для бизнеса](android-kiosk-enroll.md) вам нужно подключить клиентскую учетную запись Intune к учетной записи управляемого Google Play.  

Чтобы вам было проще настраивать и использовать управление в Android для бизнеса, при подключении к Google Play в консоль администрирования Intune автоматически добавляются четыре распространенных приложения Android для бизнеса. Речь идет о следующих четырех приложениях Android для бизнеса:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** для сценариев полностью управляемых устройств Android для бизнеса;
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** помогает входить в учетные записи при использовании двухфакторной проверки подлинности;
- **[корпоративный портал Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** используется для политик защиты приложений и в сценариях с рабочим профилем Android для бизнеса;
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) создано специально для выделенных устройств и режима киоска на Android для бизнеса.

> [!NOTE]
> Из-за взаимодействия между доменами Google и Майкрософт для выполнения этого шага может потребоваться изменить параметры браузера.  Убедитесь, что адреса "portal.azure.com" и "play.google.com" находятся в одной и той же зоне безопасности в браузере.

1. Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [задав в качестве центра сертификации управления мобильными устройствами](../fundamentals/mdm-authority-set.md) службу **Microsoft Intune**.
2. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) и выберите **Устройства** > **Android** > **Регистрация Android** > **Управляемый Google Play**.  Если вы используете настраиваемую роль администратора Intune, для доступа нужны разрешения на чтение и изменение организации.
   
   ![Экран регистрации Android для бизнеса](./media/connect-intune-android-enterprise/android-work-bind.png)

3. Выберите **Даю согласие**, чтобы предоставить корпорации Майкрософт разрешение на [отправку сведений о пользователях и устройствах в Google](../protect/data-intune-sends-to-google.md). 
   
4. Выберите **Запустить Google и подключиться сейчас**, чтобы перейти на веб-сайт управляемого Google Play. Веб-сайт откроется в новой вкладке браузера.
  
5. На странице входа в Google выполните вход с учетной записью Google, которая будет связана со всеми задачами управления Android для бизнеса для этого клиента. Это учетная запись Google, которую ИТ-администраторы вашей организации используют для управления приложениями и их публикации в консоли Google Play. Можно использовать уже существующую учетную запись Google или создать новую. Выбранная учетная запись не должна быть связана с доменом G-Suite.
    
    > [!Note]
    > Если вы пользуетесь браузером Microsoft Edge, нажмите **Войти** в правом верхнем углу для входа в учетную запись Google.

6. Укажите **название организации**. Для параметра **Поставщик услуг Enterprise mobility management (EMM)** должно быть указано значение **Microsoft Intune**.

7. Примите соглашение Android и нажмите **Подтвердить**. Ваш запрос будет обработан.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Отключение учетной записи администратора Android для бизнеса

Вы можете отключить регистрацию и управление Android для бизнеса. Для этого необходимо сначала прекратить использование всех зарегистрированных устройств Android для бизнеса, включая устройства рабочего профиля, выделенные устройства и полностью управляемые устройства. Затем, если вы щелкните **Отключить** в консоли администрирования Intune, все зарегистрированные устройства с рабочим профилем, выделенные устройства и полностью управляемые устройства с Android для бизнеса будут удалены из регистрации. При этом также удаляется связь между учетной записью управляемого Google Play и Intune.

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) в качестве администратора Intune.
2. Выберите **Устройства** > **Android** > **Регистрация устройств Android** > **Управляемый Google Play** > **Отключить**.
3. Нажмите **Да**, чтобы отключить и отменить регистрацию всех устройств Android для бизнеса в Intune.

## <a name="next-steps"></a>Дальнейшие шаги

После подключения к учетной записи управляемого Google Play вы можете [настроить устройства с рабочим профилем Android для бизнеса](android-work-profile-enroll.md), [выделенные устройства с Android для бизнеса](android-kiosk-enroll.md) и [полностью управляемые устройства Android для бизнеса](android-fully-managed-enroll.md).
