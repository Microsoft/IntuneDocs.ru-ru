---
title: "Новые возможности | Microsoft Intune"
description: "Новые возможности в выпусках Microsoft Intune этого месяца и за прошлые периоды"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Новые возможности Microsoft Intune. Октябрь 2016 г.
Узнайте о новых возможностях этого выпуска Microsoft Intune. Кроме того, здесь можно узнать о предстоящих изменениях, к которым следует подготовиться, а также сведения о прошлых выпусках.

В будущем все эти функции будут также поддерживаться в гибридных развертываниях (Configuration Manager с Intune). Дополнительные сведения о новых гибридных функциях см. на [странице новых гибридных функций](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Новые возможности

### Условный доступ для управления мобильными приложениями
Вы сможете предоставить доступ к Exchange Online только для приложений, которые поддерживают политики управления мобильными приложениями Intune, таких как Outlook. [Эту новую функцию](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) удобно совмещать с политиками управления мобильными приложениями Intune (MAM), так как вы можете блокировать доступ к встроенным почтовым клиентам и другим приложениям, для которых не были настроены политики Intune MAM. Это гарантирует, что пользователи получат доступ к данным организации только в приложениях, которые можно защитить с помощью Intune MAM. Начать работу с управлением мобильными приложениями Intune можно на портале Azure. Новый раздел "Условный доступ" находится в колонке "Настройки".

### Условный доступ для ПК под управлением Windows
Теперь вы можете создавать политики условного доступа через консоль администрирования Intune, чтобы заблокировать компьютерам под управлением Windows доступ к [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) и [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Можно также создать политики условного доступа для блокировки доступа к классическим и универсальным приложениям Office.

### Поддержка Android for Work
Intune теперь входит в программу Android for Work. Предоставление поддержки для функций Android for Work для Intune начнется в этом месяце.
[Ознакомьтесь с объявлением Майкрософт о поддержке Intune для Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Следующие разделы по Intune являются новыми или были обновлены с учетом сведений по Android for Work:

ИТ-специалистам
- [Настройка Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Ограничение доступа к электронной почте в Exchange Online и новой выделенной среде Exchange Online с помощью Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Ограничение доступа к электронной почте в локальной организации Exchange и прежней выделенной среде Exchange Online с помощью Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Параметры политики соответствия для устройств Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Развертывание приложений Android for Work](/intune/deploy-use/android-for-work-apps)
- [Настройка приложений Android for Work с помощью политик конфигурации мобильных приложений](/intune/deploy-use/afw-app-configuration-policy)
- [Параметры политики Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Конечным пользователям
- [Что происходит при создании профиля работы](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Создание профиля работы и регистрация устройства в Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Интеграция Lookout для защиты устройств с iOS
В октябре Майкрософт интегрируется с решением мобильной защиты от угроз Lookout для защиты мобильных устройств с iOS путем обнаружения вредоносных программ, опасных приложений и многого другого на таких устройствах. Решение Lookout помогает определить настраиваемый уровень угроз. Вы можете создать правило политики соответствия в Intune, чтобы определить соответствие устройств на основе оценки рисков Lookout. Используя политики условного доступа, вы можете разрешить или заблокировать доступ к ресурсам организации на основе состояния соответствия устройства.

Чтобы конечные пользователи не соответствующих политике устройств с iOS могли получить доступ к корпоративным данным, потребуется зарегистрироваться, установить приложение Lookout for Work на устройствах, активировать приложение и устранить угрозы в приложении Lookout for Work. [Настройка и развертывание приложений Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Инструмент упаковки приложений Intune для Android
Можно позволить приложениям применять политики управления мобильными приложениями (MAM) Intune с помощью инструмента упаковки приложений Intune. Теперь имеется поддержка политик Intune MAM без необходимости регистрации устройств.

### Управление печатью из приложений, контролируемых политиками MAM
Теперь можно запретить печать данных организации из приложений, которые имеют политики MAM. Этот параметр доступен на [портале Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) и поддерживается устройствами с [iOS](/Intune/deploy-use/ios-mam-policy-settings) и [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

## Объявления

### Совместимость Android Samsung KNOX с Intune
Для некоторых моделей телефонов Samsung Galaxy Ace отсутствует возможность управления с помощью Intune в качестве устройств Samsung KNOX. При регистрации этих устройств с помощью Intune управление ими будет осуществляться в качестве стандартных устройств Android.

Затронутые номера моделей:

* SM-G313HU
* SM G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

От вас и ваших пользователей дополнительные действия не требуются. Дополнительные сведения см. на веб-сайте [Samsung KNOX](https://www.samsungknox.com).

### Приложение корпоративного портала для Windows 8 устарело; поддержка для платформ Windows Phone 8 и Windows RT прекращена.
Начиная с октября 2016 г. Microsoft Intune прекращает поддержку корпоративного портала для Windows 8. Кроме того, Microsoft Intune прекращает поддержку платформ Windows Phone 8 и Windows RT. Как следствие, вы не сможете регистрировать или обновлять любые устройства с Windows Phone 8 или Windows RT.

Но вы можете продолжить управление уже зарегистрированными устройствами с Windows Phone 8, Windows RT и Windows 8. Чтобы продолжить беспроблемное распространение приложений на устройства Windows 8 и Windows Phone 8, обновите их до Windows 8.1 и Windows Phone 8.1 и используйте соответствующие приложения "Корпоративный портал" для Windows 8.1 и Windows Phone 8.1.

Начиная с ноября 2016 г. будет прекращена поддержка корпоративного портала Windows Phone 8.
<!--TFS 1255391-->

## Предстоящие изменения

### Новый корпоративный портал Microsoft Intune доступен для устройств с Windows 10
Корпорация Майкрософт выпускает новый корпоративный портал Microsoft Intune для устройств с Windows 10. Это приложение, которое использует новый формат Windows 10 Universal, представит пользователю обновленный интерфейс в приложении и аналогичный интерфейс на всех устройствах, компьютерах и мобильных устройствах под управлением Windows 10, при этом оно включает те же функциональные возможности, которые доступны пользователям сейчас.

Это новое приложение также позволит пользователям использовать дополнительные функциональные возможности платформы, такие как единый вход (SSO) и проверка подлинности на основе сертификатов на устройствах с Windows 10. Приложение станет доступно в качестве обновления для существующих установок корпоративного портала Windows 8.1 и Windows Phone 8.1 в Магазине Windows. Дополнительные сведения см. по адресу [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### См. также
* [Блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Стратегии развития облачной платформы](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Предыдущие выпуски Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


