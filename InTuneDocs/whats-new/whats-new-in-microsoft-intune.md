---
title: "Новые возможности | Microsoft Intune"
description: "Новые возможности в выпусках Microsoft Intune этого месяца и за прошлые периоды"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Новые возможности Microsoft Intune — октябрь 2016 г.
Узнайте о новых возможностях этого выпуска Microsoft Intune. Кроме того, здесь можно узнать о предстоящих изменениях, к которым следует подготовиться, а также сведения о прошлых выпусках.

> [!Note]
> В будущем все эти функции будут также поддерживаться в гибридных развертываниях (Configuration Manager с Intune). Дополнительные сведения о новых гибридных функциях см. на [странице новых гибридных функций](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Новые возможности

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Новый корпоративный портал Microsoft Intune доступен для устройств с Windows 10__. Корпорация Майкрософт выпустила новое [приложение корпоративного портала Microsoft Intune для устройств с Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Это приложение, которое использует новый формат Windows 10 Universal, представит пользователю обновленный интерфейс в приложении и аналогичный интерфейс на всех устройствах, компьютерах и мобильных устройствах под управлением Windows 10, при этом оно включает те же функциональные возможности, которые доступны пользователям сейчас.

Это новое приложение также позволит пользователям использовать дополнительные функциональные возможности платформы, такие как единый вход (SSO) и проверка подлинности на основе сертификатов на устройствах с Windows 10. Приложение станет доступно в качестве обновления для существующих установок корпоративного портала Windows 8.1 и Windows Phone 8.1 в Магазине Windows. Дополнительные сведения см. по адресу [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Обновления в Intune и Android for Work__

> Хотя приложения Android for Work можно разворачивать с действием __Необходимо__, в случае миграции групп Intune на новый интерфейс Azure AD приложения можно развернуть только с действием __Доступно__.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Пакет SDK для приложений Intune для подключаемого модуля Cordova сейчас поддерживает MAM без регистрации
Разработчики приложений теперь могут использовать пакет SDK для приложений Intune для подключаемого модуля Cordova для включения функций MAM без регистрации устройств в своих приложениях на основе Cordova для iOS и Android. Пакет SDK для приложений Intune для подключаемого модуля Cordova можно найти [здесь](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Пакет SDK для приложений Intune для компонента Xamarin сейчас поддерживает MAM без регистрации
Разработчики приложений теперь могут использовать пакет SDK для приложений Intune для компонента Xamarin, чтобы включать функции MAM без регистрации устройств в своих приложениях на основе Xamarin для iOS и Android. Пакет SDK для приложений Intune для компонента Xamarin можно найти [здесь](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Объявления

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Для отправки сертификата для подписи Symantec больше не требуется подписанный корпоративный портал Windows Phone 8
При отправке сертификата для подписи Symantec больше не требуется подписанное приложение корпоративного портала Windows Phone 8. Сертификат можно отправить без сторонних средств.

## <a name="deprecations"></a>Устаревшие возможности

### <a name="support-for-the-windows-phone-8-company-portal"></a>Поддержка корпоративного портала Windows Phone 8
Поддержка корпоративного портала Windows Phone 8 будет прекращена. Кроме того, в октябре 2016 г. прекращена поддержка платформ Windows Phone 8 и Windows RT. В октябре 2016 г. прекращена поддержка также корпоративного портала Windows 8.


### <a name="see-also"></a>См. также
* [Блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Стратегии развития облачной платформы](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Предыдущие выпуски Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


