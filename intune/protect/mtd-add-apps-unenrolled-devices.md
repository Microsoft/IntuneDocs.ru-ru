---
title: Добавление приложений для защиты мобильных устройств от угроз на незарегистрированные устройства
titleSuffix: Microsoft Intune
description: Добавление приложений для защиты мобильных устройств от угроз на незарегистрированные устройства пользователями устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1cf0a3d8b30955be8413b376acd223a924be843
ms.sourcegitcommit: 06dce5c8111592ad774247e86e539dd3128117e5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/30/2019
ms.locfileid: "75545940"
---
# <a name="add-mobile-threat-defense-apps-to-unenrolled-devices"></a>Добавление приложений для защиты мобильных устройств от угроз на незарегистрированные устройства

По умолчанию при использовании политик защиты приложений Intune с защитой от мобильных угроз служба Intune выполняет необходимую работу для установки и входа во все необходимые приложения, чтобы обеспечить подключение к соответствующим службам.

Конечным пользователям требуется Microsoft Authenticator (iOS) для регистрации устройства, а также защита мобильных устройств (Android и iOS) для получения уведомлений при обнаружении угрозы на мобильных устройствах и получения рекомендаций по устранению угроз.

Кроме того, можно использовать Intune для добавления и развертывания Microsoft Authenticator и приложений защиты от угроз для мобильных устройств (MTD).

> [!NOTE] 
> Эта статья относится ко всем партнерам по Mobile Threat Defense, поддерживающим политики защиты приложений. Better Mobile (Android), Zimperium (Android и iOS), Lookout for Work (Android и iOS).
> 
> Для незарегистрированных устройств **не требуется политика конфигурации приложений для iOS**, которая настраивает средство защиты мобильных устройств от угроз для приложений iOS, используемое с Intune. Это ключевое отличие от зарегистрированных устройств Intune. 

## <a name="configure-microsoft-authenticator-for-ios-via-intune-optional"></a>Настройка приложения Microsoft Authenticator для iOS через Intune (необязательно)
При использовании политик защиты приложений Intune с защитой мобильных устройств от угроз служба Intune поможет пользователю установить приложение, войти в систему и зарегистрировать устройство в Microsoft Authenticator (iOS).

Однако если вы хотите сделать приложение доступным для конечных пользователей с помощью корпоративного портала Intune, ознакомьтесь с инструкциями по [добавлению приложений из магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Используйте этот [URL-адрес приложения Microsoft Authenticator в магазине iOS App Store](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) в разделе **Настройка сведений о приложении**. Не забудьте [назначить приложение группам с помощью Intune](../apps/apps-deploy.md) в качестве последнего шага.

> [!NOTE] 
> Для устройств iOS требуется приложение [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), чтобы можно было проверять удостоверения пользователей в Azure AD. Корпоративный портал Intune работает на устройствах Android в качестве посредника, чтобы можно было проверять удостоверения пользователей в Azure AD.

## <a name="making-mobile-threat-defense-apps-available-via-intune-optional"></a>Предоставление доступа к мобильным приложениям для защиты от угроз через Intune (необязательно)
При использовании политик защиты приложений Intune с защитой мобильных устройств от угроз служба Intune поможет пользователю установить приложение для защиты мобильных устройств от угроз, войти в систему и зарегистрировать устройство. 

Тем не менее, если вы хотите сделать приложение доступным для конечных пользователей с помощью корпоративного портала Intune, можно выполнить следующие действия на [портале Azure](https://portal.azure.com/). Убедитесь, что вы знакомы со следующими процессами.

- [Добавление приложения в Intune](../apps/apps-add.md).
- [Назначение приложения в Intune](../apps/apps-deploy.md)

### <a name="making-lookout-for-work-available-to-end-users"></a>Предоставление доступа к Lookout for Work для конечных пользователей
- **Android**  
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес приложения Lookout for Work в магазине Google Play](https://play.google.com/store/apps/details?id=com.lookout.enterprise) в разделе **Настройка сведений о приложении**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Используйте этот [URL-адрес приложения Lookout for Work в магазине iOS App Store](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) в разделе **Настройка сведений о приложении**.

<!-- ### Making Symantec Endpoint Protection Mobile available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). When completing the **Configure app information** section, use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure). For **Minimum operating system**, select **Android 4.0 (Ice Cream Sandwich)**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile - App Store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) when completing the **Configure app information** section.

### Making Check Point SandBlast Mobile available to end users
- **Android**  
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) when completing the **Configure app information** section. 

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile - App Store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) when completing the **Configure app information** section. -->

### <a name="making-zimperium-available-to-end-users"></a>Предоставление доступа к Zimperium для конечных пользователей
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес приложения Zimperium в Магазине Google Play](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) в разделе **Configure app information** (Указание сведений о приложении).
- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Используйте этот [URL-адрес приложения Zimperium в магазине App Store](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) в разделе **Настройка сведений о приложении**.
 
<!-- ### Making Pradeo available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo - Play Store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo - App Store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) when completing the **Configure app information** section. -->

### <a name="making-better-mobile-available-to-end-users"></a>Предоставление доступа к Better Mobile для конечных пользователей 
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес приложения Active Shield в магазине Google Play](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) в разделе **Настройка сведений о приложении**.
<!-- - **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) when completing the **Configure app information** section. -->

<!-- ### Making Sophos available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos - Play Store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) when completing the **Configure app information** section.

### Making Wandera available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.wandera.android) when completing the **Configure app information** section. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile - - App Store URL](https://itunes.apple.com/app/wandera/id605469330) when completing the **Configure app information** section. -->

## <a name="next-steps"></a>Дальнейшие шаги  

- [Включение соединителя Mobile Threat Defense в Intune для незарегистрированных устройств](~/protect/mtd-enable-unenrolled-devices.md)

