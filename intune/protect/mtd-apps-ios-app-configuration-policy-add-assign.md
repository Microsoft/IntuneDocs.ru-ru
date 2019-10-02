---
title: Добавление и назначение приложений MTD в Microsoft Intune
titleSuffix: Microsoft Intune
description: Добавление приложений Mobile Threat Defense (MTD), Microsoft Authenticator и политики конфигурации для iOS в Microsoft Intune на портале Azure.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08a4b6b4bbb9922395bca7b331fee259cb49fbd8
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722089"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Добавление и назначение приложений Mobile Threat Defense (MTD) в Intune  

> [!NOTE] 
> Эта статья относится ко всем партнерам по Mobile Threat Defense.

Вы можете использовать Intune для добавления и развертывания приложений Mobile Threat Defense (MTD), чтобы конечные пользователи могли получать уведомления при определении угроз в их мобильных устройствах и рекомендации по их устранению.

## <a name="before-you-begin"></a>Подготовка к работе    
Описанные ниже действия следует выполнять на [портале Azure](https://portal.azure.com/). Убедитесь, что вы знакомы со следующими процессами.

- [Добавление приложения в Intune](../apps/apps-add.md).
- [Добавление политики конфигурации приложения для iOS в Intune](../apps/app-configuration-policies-use-ios.md).
- [Назначение приложения в Intune](../apps/apps-deploy.md)

> [!TIP]
> Корпоративный портал Intune работает на устройствах Android в качестве посредника, чтобы можно было проверять удостоверения пользователей в Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Настройка приложения Microsoft Authenticator для iOS  
Для устройств iOS требуется приложение [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), чтобы можно было проверять удостоверения пользователей в Azure AD. Кроме того, требуется политика конфигурации приложений iOS, указывающая, какое приложение iOS MTD следует использовать с Intune.

Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Используйте этот [URL-адрес приложения Microsoft Authenticator в магазине](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) на **шаге 12** в разделе **Настройка сведений о приложении**.

## <a name="configure-mtd-applications"></a>Настройка приложений MTD  
Выберите раздел, соответствующий вашему поставщику MTD:

- [Lookout for Work](#configure-lookout-for-work-apps)
- [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
- [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
- [Zimperium](#configure-zimperium-apps)
- [Pradeo](#configure-pradeo-apps)
- [Better Mobile](#configure-better-mobile-apps)
- [Sophos Mobile](#configure-sophos-apps)
- [Wandera](#configure-wandera-apps)

### <a name="configure-lookout-for-work-apps"></a>Настройка приложений Lookout for Work  
- **Android**  
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте [URL-адрес приложения Lookout for Work в магазине Google](https://play.google.com/store/apps/details?id=com.lookout.enterprise) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения iOS Lookout for Work в магазине](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) на **шаге 11** для параметра **URL-адрес Appstore**.

- **Приложение Lookout for Work вне магазина Apple Store**  
  - Вам нужно повторно подписать приложение Lookout for Work для iOS. Lookout распространяет приложение Lookout for Work iOS за пределами магазина iOS App Store. Перед распространением приложения нужно повторно подписать приложение с использованием сертификата корпоративного разработчика iOS.  
  - Подробные инструкции по повторной подписи приложений Lookout for Work для iOS см. в статье [Процесс повторной подписи приложения Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) на веб-сайте Lookout.

  - **Включите проверку подлинности Azure AD для пользователей приложения Lookout for Work для iOS.**

    1. Перейдите на [портал Azure](https://portal.azure.com) и войдите с помощью своих учетных данных, а затем перейдите на страницу приложения.

    2. Добавьте **Приложение Lookout for Work iOS** в качестве **встроенного клиентского приложения**.

    3. Замените адрес **com.lookout.enterprise.yourcompanyname** на идентификатор пакета клиента, выбранный во время подписи пакета IPA.

    4. Добавьте дополнительный URI перенаправления: **&lt;companyportal://code/>** , за которым указывается оригинальный URI перенаправления, закодированный как URL-адрес.

    5. Добавьте **Делегированные разрешения** в приложение.

    > [!NOTE] 
    > Дополнительные сведения см. в статье [Настройка встроенного клиентского приложения в Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

  - **Добавьте IPA-файл для Lookout for Work.**

    - Отправьте повторно подписанный IPA-файл, как описано в статье [Добавление бизнес-приложений iOS в Intune](../apps/lob-apps-ios.md). Вам также нужно установить минимальную версию ОС — iOS 8.0 или более позднюю.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Настройка приложений Symantec Endpoint Protection Mobile  
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). На **шаге 7** примените этот [URL-адрес магазина приложений SEP Mobile](https://play.google.com/store/apps/details?id=com.skycure.skycure).  Для параметра **Минимальная версия операционной системы** выберите значение **Android 4.0 (Ice Cream Sandwich)** .

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения SEP Mobile в магазине](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) на **шаге 11** для параметра **URL-адрес Appstore**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Настройка приложений Check Point SandBlast Mobile  
- **Android**  
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте [URL-адрес Check Point SandBlast Mobile в магазине приложений](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения Check Point SandBlast Mobile в магазине](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) на **шаге 11** для параметра **URL-адрес Appstore**.  

### <a name="configure-zimperium-apps"></a>Настройка приложений Zimperium  
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес приложения Zimperium в магазине](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения Zimperium в магазине](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) на **шаге 11** для параметра **URL-адрес Appstore**.  
 
### <a name="configure-pradeo-apps"></a>Настройка приложений Pradeo  
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес магазина приложений Pradeo](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения Pradeo в магазине](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) на **шаге 11** для параметра **URL-адрес Appstore**.

### <a name="configure-better-mobile-apps"></a>Настройка приложений Better Mobile  
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте [URL-адрес Active Shield в магазине приложений](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения ActiveShield в магазине](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) на **шаге 11** для параметра **URL-адрес Appstore**.

### <a name="configure-sophos-apps"></a>Настройка приложений Sophos  
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес приложения Sophos в магазине](https://play.google.com/store/apps/details?id=com.sophos.smsec) на **шаге 7**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Примените этот [URL-адрес приложения ActiveShield в магазине](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) на **шаге 11** для параметра **URL-адрес Appstore**.

### <a name="configure-wandera-apps"></a>Настройка приложений Wandera  
 
- **Android**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](../apps/store-apps-android.md). Используйте этот [URL-адрес мобильного решения Wandera в магазине приложений](https://play.google.com/store/apps/details?id=com.wandera.android) на **шаге 7**. В качестве **Минимальной версии операционной системы** выберите **Android 5.0**.

- **iOS**
  - Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](../apps/store-apps-ios.md). Используйте этот [URL-адрес мобильного решения Wandera в магазине приложений](https://itunes.apple.com/app/wandera/id605469330) на **шаге 11** для параметра **URL-адрес Appstore**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Настройка приложений MTD с политикой конфигурации приложений iOS  

### <a name="lookout-for-work-app-configuration-policy"></a>Политика конфигурации приложений Lookout for Work  
- Создайте политику конфигурации приложений iOS, как описано в статье об [использовании политики конфигурации приложений iOS](../apps/app-configuration-policies-use-ios.md).

### <a name="sep-mobile-app-configuration-policy"></a>Политика конфигурации приложений SEP Mobile  
- Используйте ту же учетную запись Azure AD, которая ранее была настроена в [консоли управления Symantec Endpoint Protection](https://aad.skycure.com) и которая применялась для входа на классический портал Intune.

- **Скачайте** файл политики конфигурации приложения для iOS: 
  - Откройте [консоль управления Symantec Endpoint Protection](https://aad.skycure.com) и войдите с учетными данными администратора.

  - Перейдите в **Параметры** и в разделе **Интеграции** выберите элемент **Intune**. Выберите **Выбор интеграции EMM**. Выберите **Microsoft** и сохраните изменения.

  - Щелкните ссылку **Файлы установки интеграции** и сохраните созданный файл \*.zip. ZIP-файл содержит файл * **.plist**, который будет использоваться для создания политики конфигурации приложения для iOS в Intune.

  - Инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](../apps/app-configuration-policies-use-ios.md) помогут вам добавить политику конфигурации приложений SEP Mobile для iOS.

  - На **шаге 8** используйте вариант **Введите данные XML**, скопируйте содержимое из файла * **.plist** и вставьте его в текст политики конфигурации.

> [!NOTE]  
> Если вам не удастся получить эти файлы, обратитесь в [службу корпоративной поддержки Symantec Endpoint Protection Mobile](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Политика конфигурации приложений Check Point SandBlast Mobile  
- Добавьте политику конфигурации приложения Check Point SandBlast Mobile для iOS согласно инструкции по [использованию политик конфигурации приложений для iOS в Microsoft Intune](../apps/app-configuration-policies-use-ios.md).
  - В **шаге 8** используйте функцию **Введите данные XML**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации.

        <dict><key>MDM</key><string>INTUNE</string></dict>


### <a name="zimperium-app-configuration-policy"></a>Политика конфигурации приложений Zimperium  
- См. инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](../apps/app-configuration-policies-use-ios.md), чтобы добавить политику конфигурации приложений Zimperium для iOS.
  - В **шаге 8** используйте функцию **Введите данные XML**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации.
 
        <dict>
        <key>provider</key><string>Intune</string>
        <key>userprincipalname</key><string>{{userprincipalname}}</string>
        <key>deviceid</key>
        <string>{{deviceid}}</string>
        <key>serialnumber</key>
        <string>{{serialnumber}}</string>
        <key>udidlast4digits</key>
        <string>{{udidlast4digits}}</string>
        </dict>

### <a name="pradeo-app-configuration-policy"></a>Политика конфигурации приложений Pradeo  
Pradeo не поддерживает политики конфигурации приложений на iOS.  Вместо этого, чтобы получить настроенное приложение, обратитесь в Pradeo для получения пользовательских файлов IPA или APK, настроенных с нужными вам параметрами.

### <a name="better-mobile-app-configuration-policy"></a>Политика конфигурации приложений Better Mobile  
- Инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](../apps/app-configuration-policies-use-ios.md) помогут вам добавить политику конфигурации приложений Better Mobile для iOS.
  - В **шаге 8** используйте функцию **Введите данные XML**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации. Замените URL-адрес `https://client.bmobi.net` на подходящий URL-адрес консоли.

        <dict>
        <key>better_server_url</key>
        <string>https://client.bmobi.net</string>
        <key>better_udid</key>
        <string>{{aaddeviceid}}</string>
        <key>better_user</key>
        <string>{{userprincipalname}}</string>
        </dict>


### <a name="sophos-mobile-app-configuration-policy"></a>Политика конфигурации приложений Sophos Mobile  
Создайте политику конфигурации приложений iOS, как описано в статье об [использовании политики конфигурации приложений iOS](../apps/app-configuration-policies-use-ios.md).

### <a name="wandera-app-configuration-policy"></a>Политика конфигурации приложения Wandera  
Чтобы добавить политику конфигурации приложения Wandera для iOS, см. инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](../apps/app-configuration-policies-use-ios.md).
- На **шаге 8** используйте функцию **Введите данные XML**. Войдите на портал Wandera RADAR и перейдите в раздел **Settings (Параметры)**  > **EMM Integration (Интеграция EMM)**  > **App Push (Отправка приложения)** . Выберите **Intune**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации.  

      <dict><key>secretKey</key>
       <string>SeeRADAR</string>
       <key>apiKey</key>
       <string> SeeRADAR </string>
       <key>customerId</key>
       <string> SeeRADAR </string>
       <key>email</key>
       <string>{{mail}}</string>
       <key>firstName</key>
       <string>{{username}}</string>
       <key>lastName</key>
       <string></string>
       <key>activationType</key>
       <string>PROVISION_THEN_AWP</string></dict>  

## <a name="assign-apps-to-groups"></a>Назначение приложений группам  
- Этот шаг применяется ко всем партнерам MTD. См. инструкции по [назначению приложений группам в Intune](../apps/apps-deploy.md).

## <a name="next-steps"></a>Дальнейшие шаги  
- [Настройка политики соответствия устройств для MTD](mtd-device-compliance-policy-create.md)
