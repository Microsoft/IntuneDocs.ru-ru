---
title: "Добавление и назначение приложений MTD в Intune"
titleSuffix: Azure portal
description: "Добавление приложений MTD, Microsoft Authenticator и политики конфигурации для iOS в Intune на портале Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ba0bbe8d10b3161af19b45e3a37f51101730d567
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Добавление и назначение приложений Mobile Threat Defense (MTD) в Intune

> [!NOTE] 
> Этот раздел относится ко всем партнерам по Mobile Threat Defense.

Вы можете использовать Intune для добавления и развертывания приложений MTD, чтобы конечные пользователи могли получать уведомления при определении угроз в их мобильных устройствах и рекомендации по их устранению.

Для устройств iOS требуется приложение [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), чтобы можно было проверять удостоверения пользователей в Azure AD. Кроме того, требуется политика конфигурации приложений iOS, указывающая, какое приложение iOS MTD следует использовать с Intune.

> [!TIP]
> Корпоративный портал Intune работает на устройствах Android в качестве посредника, чтобы можно было проверять удостоверения пользователей в Azure AD.

## <a name="before-you-begin"></a>Подготовка к работе

-   Описанные ниже действия следует выполнять на [портале Azure](https://portal.azure.com/).

-   Убедитесь, что вы знакомы со следующими процессами.

    -   [Добавление приложения в Intune](apps-add.md).

    -   [Добавление политики конфигурации приложения для iOS в Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Назначение приложения в Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Добавление политики конфигурации приложений для iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-apps"></a>Добавление приложений

### <a name="all-mtd-partners"></a>Все партнеры по MTD

#### <a name="microsoft-authenticator-app-for-ios"></a>Приложение Microsoft Authenticator для iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Microsoft Authenticator в магазине](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте [URL-адрес приложения Lookout for Work в магазине Google](https://play.google.com/store/apps/details?id=com.lookout.enterprise) на **шаге 7**.

#### <a name="ios"></a>iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Lookout for Work в магазине iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Приложение Lookout for Work вне магазина Apple Store

Вам нужно повторно подписать приложение Lookout for Work для iOS. Lookout распространяет приложение Lookout for Work iOS за пределами магазина iOS App Store. Перед распространением приложения нужно повторно подписать приложение с использованием сертификата корпоративного разработчика iOS.

Подробные инструкции по повторной подписи приложений Lookout for Work для iOS см. в статье [Процесс повторной подписи приложения Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) на веб-сайте Lookout.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Включение проверки подлинности Azure AD для приложения Lookout for Work для iOS

Включите проверку подлинности Azure Active Directory для пользователей iOS, выполнив следующие действия.

1. Перейдите на [портал Azure](https://portal.azure.com) и войдите с помощью своих учетных данных, а затем перейдите на страницу приложения.
  
2. Добавьте **Приложение Lookout for Work iOS** в качестве **встроенного клиентского приложения**.

3. Замените адрес **com.lookout.enterprise.yourcompanyname** на идентификатор пакета клиента, выбранный во время подписи пакета IPA.

4.  Добавьте дополнительный URI перенаправления: **&lt;companyportal://code/>**, за которым указывается оригинальный URI перенаправления, закодированный как URL-адрес.

5.  Добавьте **Делегированные разрешения** в приложение.

    > [!NOTE] 
    > Дополнительные сведения см. в статье [Настройка встроенного клиентского приложения в Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

##### <a name="add-the-lookout-for-work-ipa-file"></a>Добавление IPA-файла для Lookout for Work

- Отправьте повторно подписанный IPA-файл, как описано в разделе [Добавление бизнес-приложений для iOS в Intune](lob-apps-ios.md). Вам также нужно установить минимальную версию ОС — iOS 8.0 или более позднюю.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте этот [URL-адрес приложения Skycure в магазине](https://play.google.com/store/apps/details?id=com.skycure.skycure) на **шаге 7**.

#### <a name="ios"></a>iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Skycure в магазине](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

#### <a name="android"></a>Android

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте [URL-адрес Check Point SandBlast Mobile в магазине приложений](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) на **шаге 7**.

#### <a name="ios"></a>iOS

- Обратитесь в [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/), чтобы получить приложение iOS. Просмотрите инструкции по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md), а затем используйте URL-адрес из магазина Apple на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте этот [URL-адрес приложения Zimperium в магазине](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) на **шаге 7**.

#### <a name="ios"></a>iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Zimperium в магазине](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Сопоставление приложения MTD с политикой конфигурации приложений iOS

### <a name="for-lookout"></a>Для Lookout

- Создайте политику конфигурации приложений iOS, как описано в разделе [об использовании политики конфигурации приложений iOS](app-configuration-policies-use-ios.md).

### <a name="for-skycure"></a>Для Skycure

-   Используйте ту же учетную запись Azure AD, которая ранее была настроена в [консоли управления Skycure](https://aad.skycure.com). Это должна быть учетная запись для входа на классический портал Intune.

-   Нужно **скачать** файл политики конфигурации приложения для iOS. 
    -   Перейдите в [консоль управления Skycure](https://aad.skycure.com) и войдите с учетными данными администратора.
    
    -   Последовательно выберите пункты **Параметры** &gt; **Интеграция устройств управления** &gt; **Выбор интеграции EMM**, выберите **Microsoft Intune**, затем сохраните свой выбор.
    
    -   Щелкните ссылку **Файлы установки интеграции** и сохраните созданный \*ZIP-файл. ZIP-файл содержит файл **skycure\_configuration.plist**, который будет использоваться для создания политики конфигурации приложения для iOS в Intune.
    
    -   См. инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](app-configuration-policies-use-ios.md), чтобы добавить политику конфигурации приложений Skycure для iOS.
    
    - На **шаге 8** используйте параметр **Введите данные XML**, скопируйте содержимое из файла **skycure_configuration.plist** и вставьте его в текст политики конфигурации.

Содержимое **skycure_configuration.plist** также можно скопировать здесь:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

- Добавьте политику конфигурации приложения Check Point SandBlast Mobile для iOS согласно инструкции по [использованию политик конфигурации приложений для iOS в Microsoft Intune](app-configuration-policies-use-ios.md).
    - В **шаге 8** используйте функцию **Введите данные XML**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации.

```
<dict><key>MDM</key><string>INTUNE</string></dict>

```

### <a name="for-zimperium"></a>Для Zimperium

- См. инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](app-configuration-policies-use-ios.md), чтобы добавить политику конфигурации приложений Zimperium для iOS.
    - В **шаге 8** используйте функцию **Введите данные XML**, скопируйте содержимое ниже и вставьте его в текст политики конфигурации.

```
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

```

## <a name="to-assign-apps-all-mtd-partners"></a>Назначение приложений (все партнеры по MTD)

- См. инструкции по [назначению приложений группам в Intune](apps-deploy.md).

## <a name="next-steps"></a>Дальнейшие шаги

- [Добавление политики соответствия устройств для MTD](mtd-device-compliance-policy-create.md)
