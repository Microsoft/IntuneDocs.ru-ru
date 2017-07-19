---
title: "Добавление и назначение приложений MTD в Intune"
titleSuffix: Intune on Azure
description: "Добавление приложений MTD, Microsoft Authenticator и политики конфигурации для iOS в Intune на базе Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Добавление и назначение приложений Mobile Threat Defense (MTD) в Intune

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

### <a name="skycure-app-for-android"></a>Приложение Skycure для Android

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте этот [URL-адрес приложения Skycure в магазине](https://play.google.com/store/apps/details?id=com.skycure.skycure) на **шаге 7**.

### <a name="skycure-app-for-ios"></a>Приложение Skycure для iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Skycure в магазине](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="microsoft-authenticator-app-for-ios"></a>Приложение Microsoft Authenticator для iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Microsoft Authenticator в магазине](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="lookout-for-work-android-app"></a>Приложение Lookout for Work для Android

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина Android в Microsoft Intune](store-apps-android.md). Используйте [URL-адрес приложения Lookout for Work в магазине Google](https://play.google.com/store/apps/details?id=com.lookout.enterprise) на **шаге 7**.

### <a name="lookout-for-work-ios-app"></a>Приложение Lookout for Work для iOS

- Вы можете ознакомиться с инструкциями по [добавлению приложений магазина iOS в Microsoft Intune](store-apps-ios.md). Используйте этот [URL-адрес приложения Lookout for Work в магазине iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) на **шаге 5** в разделе **Настройка сведений о приложении**.

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Приложение Lookout for Work вне магазина Apple Store

Вам нужно повторно подписать приложение Lookout for Work для iOS. Lookout распространяет приложение Lookout for Work iOS за пределами магазина iOS App Store. Перед распространением приложения нужно повторно подписать приложение с использованием сертификата корпоративного разработчика iOS.

Подробные инструкции по повторной подписи приложений Lookout for Work для iOS см. в статье [Процесс повторной подписи приложения Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) на веб-сайте Lookout.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Включение проверки подлинности Azure AD для приложения Lookout for Work для iOS

Включите проверку подлинности Azure Active Directory для пользователей iOS, выполнив следующие действия.

1. Перейдите на [портал Azure](https://portal.sazure.com) и войдите с помощью своих учетных данных, а затем перейдите на страницу приложения.
  
2. Добавьте **Приложение Lookout for Work iOS** в качестве **встроенного клиентского приложения**.

3. Замените адрес **com.lookout.enterprise.yourcompanyname** на идентификатор пакета клиента, выбранный во время подписи пакета IPA.

4.  Добавьте дополнительный URI перенаправления: **&lt;companyportal://code/>**, за которым указывается оригинальный URI перенаправления, закодированный как URL-адрес.

5.  Добавьте **Делегированные разрешения** в приложение.

    > [!NOTE] 
    > Дополнительные сведения см. в статье [Настройка встроенного клиентского приложения в Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>Добавление IPA-файла для Lookout for Work

- Отправьте повторно подписанный IPA-файл, как описано в разделе [Добавление бизнес-приложений для iOS в Intune](lob-apps-ios.md). Вам также нужно установить минимальную версию ОС — iOS 8.0 или более позднюю.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Сопоставление приложения MTD с политикой конфигурации приложений iOS

### <a name="for-skycure"></a>Для Skycure

-   Используйте ту же учетную запись Azure AD, которая ранее была настроена в консоли управления Skycure. Это должна быть учетная запись для входа в классическую консоль Intune.

-   У вас должен быть готовый к использованию файл интеграции Skycure. Это ранее скачанный из консоли управления Skycure ZIP-файл, который содержит файл **skycure\_configuration.plist** с параметрами политики конфигурации приложения для iOS.

- См. инструкции по [использованию политик конфигурации приложений Microsoft Intune для iOS](app-configuration-policies-use-ios.md), чтобы добавить политику конфигурации приложений Skycure для iOS.
    - На шаге 8 используйте параметр **Введите данные XML**, скопируйте содержимое из файла **skycure_configuration.plist** и вставьте в тело политики конфигурации.

Содержимое **skycure_configuration.plist** также можно скопировать здесь:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Для Lookout

- Создайте политику конфигурации приложений iOS, как описано в разделе [об использовании политики конфигурации приложений iOS](app-configuration-policies-use-ios.md).

## <a name="to-assign-mtd-apps"></a>Назначение приложений MTD

- См. инструкции по [назначению приложений группам в Intune](apps-deploy.md).

## <a name="next-steps"></a>Дальнейшие действия

[Настройка интеграции Skycure и Intune](skycure-mtd-connector-integration.md)
[Настройка интеграции Lookout и Intune](lookout-mtd-connector-integration.md)
