---
title: "Ранний выпуск | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Предстоящие изменения в Microsoft Intune в октябре
**Ранний выпуск** содержит список функций, которые будут включены в предстоящие выпуски Microsoft Intune. Эта информация предоставляется в рамках соглашения о неразглашении, в крайне ограниченном объеме и может изменяться. Некоторые из указанных здесь компонентов могут быть не готовы к сроку, поэтому их выпуск может быть отложен. Другие функции проходят проверку в пилотном проекте, которая должна доказать их готовность для развертывания у клиентов. При наличии любых вопросов или проблем обратитесь к своему контактному лицу по Intune/PM.

Эта страница периодически обновляется. Следите за обновлением сведений о предстоящих изменениях.

Следующие изменения находятся в разработке для Intune. В будущем все эти функции будут также поддерживаться в гибридных развертываниях (Configuration Manager с Intune). Дополнительные сведения о новых гибридных функциях см. на [странице новых гибридных функций](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Управление печатью из приложений, контролируемых политиками MAM
Теперь можно запретить печать данных организации из приложений, которые имеют политики MAM. Этот параметр доступен на [портале Azure](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) и поддерживается устройствами с [iOS](..deployuse/ios-mam-policy-settings) и [Android](..deployuse/android-mam-policy-settings).
<!--TFS 1014328-->

### Новый корпоративный портал Microsoft Intune доступен для устройств с Windows 10
Корпорация Майкрософт выпускает новый корпоративный портал Microsoft Intune для устройств с Windows 10. Это приложение, которое использует новый формат Windows 10 Universal, представит пользователю обновленный интерфейс в приложении и аналогичный интерфейс на всех устройствах, компьютерах и мобильных устройствах под управлением Windows 10, при этом оно включает те же функциональные возможности, которые доступны пользователям сейчас.

Это новое приложение также позволит пользователям использовать дополнительные функциональные возможности платформы, такие как единый вход (SSO) и проверка подлинности на основе сертификатов на устройствах с Windows 10. Приложение станет доступно в качестве обновления для существующих установок корпоративного портала Windows 8.1 и Windows Phone 8.1 в Магазине Windows.
<!--TFS 1016502-->

### Поддержка Android for Work

Intune теперь входит в программу [Android for Work](https://enterprise.google.com/android/partners/). Предоставление поддержки для функций Android for Work для Intune начнется в этом месяце.

[Ознакомьтесь с объявлением Майкрософт о поддержке Intune для Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Совместимость Android Samsung KNOX с Intune

Для некоторых моделей телефонов Samsung Galaxy Ace отсутствует возможность управления с помощью Intune в качестве устройств Samsung KNOX. При регистрации этих устройств с помощью Intune управление ими будет осуществляться в качестве стандартных устройств Android.
Затронутые номера моделей:

* SM-G313HU
* SM G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

От вас и ваших пользователей дополнительные действия не требуются.
Дополнительные сведения см. на веб-сайте [Samsung KNOX](https://www.samsungknox.com).

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Приложение корпоративного портала для Windows 8 устарело; поддержка для платформ Windows Phone 8 и Windows RT прекращена.
Начиная с октября 2016 г. Microsoft Intune прекращает поддержку корпоративного портала для Windows 8. Кроме того, Microsoft Intune прекращает поддержку платформ Windows Phone 8 и Windows RT. Как следствие, вы не сможете регистрировать или обновлять любые устройства с Windows Phone 8 или Windows RT.

Но вы можете продолжить управление уже зарегистрированными устройствами с Windows Phone 8, Windows RT и Windows 8. Чтобы продолжить беспроблемное распространение приложений на устройства Windows 8 и Windows Phone 8, обновите их до Windows 8.1 и Windows Phone 8.1 и используйте соответствующие приложения "Корпоративный портал" для Windows 8.1 и Windows Phone 8.1.

Начиная с ноября 2016 г. будет прекращена поддержка корпоративного портала Windows Phone 8.
<!--TFS 1255391-->

### Условный доступ для управления мобильными приложениями
Теперь вы можете создать политику условного доступа, чтобы заблокировать неуправляемым мобильным приложениям доступ к [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) и [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Также можно заблокировать встроенные почтовые клиенты и приложения, для которых отключена функция MAM в пакете SDK приложения Intune.  Это можно сделать, создав политику условного доступа и указав приложения, которым требуется предоставить доступ к Exchange Online и SharePoint Online с помощью портала Azure.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Интеграция Lookout для защиты устройств с iOS
В октябре Майкрософт интегрируется с решением мобильной защиты от угроз Lookout для защиты мобильных устройств с iOS путем обнаружения вредоносных программ, опасных приложений и многого другого на таких устройствах. Решение Lookout помогает определить настраиваемый уровень угроз. Вы можете создать правило политики соответствия в Intune, чтобы определить соответствие устройств на основе оценки рисков Lookout. Используя политики условного доступа, вы можете разрешить или заблокировать доступ к ресурсам организации на основе состояния соответствия устройства.

Чтобы конечные пользователи не соответствующих политике устройств с iOS могли получить доступ к корпоративным данным, потребуется зарегистрироваться, установить приложение Lookout for Work на устройствах, активировать приложение и устранить угрозы в приложении Lookout for Work.
<!--TFS 1319493-->

### Пакет SDK приложения Intune и инструмент упаковки для приложения для Android
Можно позволить приложениям применять политики управления мобильными приложениями (MAM) Intune, используя инструмент упаковки приложений Intune или пакет SDK для приложений Intune. Новые обновления для инструмента упаковки для приложения и пакета SDK содержат следующие возможности.

* Поддержка Android N
* Поддержка политик Intune MAM без необходимости регистрации устройств
* Поддержка приложений Android на базе Xamarin

Можно проверить MAM без регистрации устройства и поддержки Xamarin с помощью общедоступной предварительной версии инструмента упаковки приложений Android здесь: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview).
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### См. также
См. статью [Новые возможности в Microsoft Intune](whats-new-in-microsoft-intune.md) для ознакомления с нововведениями.



<!--HONumber=Oct16_HO1-->


