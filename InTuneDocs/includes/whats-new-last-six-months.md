## <a name="november-2016"></a>Ноябрь 2016 г.

### <a name="new-capabilities"></a>Новые возможности

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

__Пакет SDK для приложений Intune для подключаемого модуля Cordova сейчас поддерживает MAM без регистрации__. Разработчики приложений теперь могут использовать пакет SDK для приложений Intune для подключаемого модуля Cordova, чтобы включать функции MAM без регистрации устройств в своих приложениях на основе Cordova для iOS и Android. Пакет SDK для приложений Intune для подключаемого модуля Cordova можно найти [здесь](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Компонент Xamarin из пакета SDK для приложений Intune сейчас поддерживает MAM без регистрации__. Разработчики приложений теперь могут использовать компонент Xamarin из пакета SDK для приложений Intune, чтобы включать функции MAM без регистрации устройств в своих приложениях на основе Xamarin для iOS и Android. Пакет SDK для приложений Intune для компонента Xamarin можно найти [здесь](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Объявления

__Отправка сертификата для подписи Symantec больше не требует подписанный корпоративный портал Windows Phone 8__. Чтобы отправить сертификат для подписи Symantec, подписи больше не требуется подписанное приложение корпоративного портала Windows Phone 8. Сертификат можно отправить без сторонних средств.

###<a name="deprecations"></a>Устаревшие возможности

__Поддержка корпоративного портала Windows Phone 8__. Поддержка корпоративного портала Windows Phone 8 не будет прекращена. Кроме того, в октябре 2016 г. прекращена поддержка платформ Windows Phone 8 и Windows RT. В октябре 2016 г. прекращена поддержка также корпоративного портала Windows 8.

## <a name="october-2016"></a>Октябрь 2016 г.

### <a name="conditional-access-for-mobile-application-management"></a>Условный доступ для управления мобильными приложениями
Вы сможете предоставить доступ к Exchange Online только для приложений, которые поддерживают политики управления мобильными приложениями Intune, таких как Outlook. [Эту новую функцию](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) удобно совмещать с политиками управления мобильными приложениями Intune (MAM), так как вы можете блокировать доступ к встроенным почтовым клиентам и другим приложениям, для которых не были настроены политики Intune MAM. Это гарантирует, что пользователи получат доступ к данным организации только в приложениях, которые можно защитить с помощью Intune MAM. Начать работу с управлением мобильными приложениями Intune можно на портале Azure. Новый раздел "Условный доступ" находится в колонке "Настройки".

### <a name="conditional-access-for-windows-pcs"></a>Условный доступ для ПК под управлением Windows
Теперь вы можете создавать политики условного доступа через консоль администрирования Intune, чтобы заблокировать компьютерам под управлением Windows доступ к [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) и [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Можно также создать политики условного доступа для блокировки доступа к классическим и универсальным приложениям Office.

### <a name="android-for-work-support"></a>Поддержка Android for Work

> [!IMPORTANT]

> Хотя приложения Android for Work можно разворачивать с действием __Необходимо__, в случае миграции групп Intune на новый интерфейс Azure AD приложения можно развернуть только с действием __Доступно__.

Intune теперь входит в программу Android for Work. Начиная с этого месяца, мы начинаем развертывать поддержку функций Android for Work и продолжим эту работу в течение следующих нескольких месяцев. Обратите внимание на то, что в доступном развертывании AfW используются новые параметры группирования и таргетирования. Вновь подготовленные учетные записи Intune смогут использовать эту функцию, как только получат доступ к Android for Work.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

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

### <a name="lookout-integration-to-protect-ios-devices"></a>Интеграция Lookout для защиты устройств с iOS
В октябре Майкрософт интегрируется с решением мобильной защиты от угроз Lookout для защиты мобильных устройств с iOS путем обнаружения вредоносных программ, опасных приложений и многого другого на таких устройствах. Решение Lookout помогает определить настраиваемый уровень угроз. Вы можете создать правило политики соответствия в Intune, чтобы определить соответствие устройств на основе оценки рисков Lookout. Используя политики условного доступа, вы можете разрешить или заблокировать доступ к ресурсам организации на основе состояния соответствия устройства.

Чтобы конечные пользователи не соответствующих политике устройств с iOS могли получить доступ к корпоративным данным, потребуется зарегистрироваться, установить приложение Lookout for Work на устройствах, активировать приложение и устранить угрозы в приложении Lookout for Work. [Настройка и развертывание приложений Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Инструмент упаковки приложений Intune для Android
Можно позволить приложениям применять политики управления мобильными приложениями (MAM) Intune с помощью инструмента упаковки приложений Intune. Теперь имеется поддержка политик Intune MAM без необходимости регистрации устройств.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Управление печатью из приложений, контролируемых политиками MAM
Теперь можно запретить печать данных организации из приложений, которые имеют политики MAM. Этот параметр доступен на [портале Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) и поддерживается устройствами с [iOS](/Intune/deploy-use/ios-mam-policy-settings) и [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Поддержка отпечатков пальцев на устройствах Android
Теперь политики управления мобильными приложениями (MAM) Android позволяют пользователям получать доступ к приложению, используя вместо PIN-кода отпечаток пальца. Этот и другие параметры политики управления мобильными приложениями для устройств Android рассматриваются [здесь](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Объявления

__Совместимость Android Samsung KNOX с Intune__. Для некоторых моделей телефонов Samsung Galaxy Ace отсутствует возможность управления с помощью Intune в качестве устройств Samsung KNOX. При регистрации этих устройств с помощью Intune управление ими будет осуществляться в качестве стандартных устройств Android.

Затронутые номера моделей:

* SM-G313HU
* SM G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

От вас и ваших пользователей дополнительные действия не требуются. Дополнительные сведения см. на веб-сайте [Samsung KNOX](https://www.samsungknox.com).

__Приложение корпоративного портала для Windows 8 устарело; поддержка для платформ Windows Phone 8 и Windows RT прекращена__. Начиная с октября 2016 г. поддержка корпоративного портала Windows 8 в Microsoft Intune будет прекращена. Кроме того, Microsoft Intune прекращает поддержку платформ Windows Phone 8 и Windows RT. Как следствие, вы не сможете регистрировать или обновлять любые устройства с Windows Phone 8 или Windows RT.

Но вы можете продолжить управление уже зарегистрированными устройствами с Windows Phone 8, Windows RT и Windows 8. Чтобы продолжить беспроблемное распространение приложений на устройства Windows 8 и Windows Phone 8, обновите их до Windows 8.1 и Windows Phone 8.1 и используйте соответствующие приложения "Корпоративный портал" для Windows 8.1 и Windows Phone 8.1.

Начиная с ноября 2016 г. будет прекращена поддержка корпоративного портала Windows Phone 8.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Предстоящие изменения

__Новый корпоративный портал Microsoft Intune доступен для устройств с Windows 10__. Корпорация Майкрософт выпускает новый корпоративный портал Microsoft Intune для устройств с Windows 10. Это приложение, которое использует новый формат Windows 10 Universal, представит пользователю обновленный интерфейс в приложении и аналогичный интерфейс на всех устройствах, компьютерах и мобильных устройствах под управлением Windows 10, при этом оно включает те же функциональные возможности, которые доступны пользователям сейчас.

Это новое приложение также позволит пользователям использовать дополнительные функциональные возможности платформы, такие как единый вход (SSO) и проверка подлинности на основе сертификатов на устройствах с Windows 10. Приложение станет доступно в качестве обновления для существующих установок корпоративного портала Windows 8.1 и Windows Phone 8.1 в Магазине Windows. Дополнительные сведения см. по адресу [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Сентябрь 2016 г.
### <a name="new-features-announcements-and-information"></a>Новые функции, объявления и сведения
* [Условный доступ в Windows](#windows-conditional-access)
* [Поддержка iOS 10](#ios-10-support)
* [Инструмент упаковки для приложений поддерживает MAM без регистрации устройств для Android и iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios).
* [Переход групп Intune в Azure Active Directory начнется в сентябре](#intune-groups-begin-transitioning-to-azure-active-directory-in-september).
* [Интеграция Lookout для защиты устройств с Android](#lookout-integration-to-protect-android-devices)
* [Обновления корпоративного портала для Android, iOS и Windows](#company-portal-updates)
* [Глоссарий Intune](#intune-glossary)
* [Предстоящие изменения](#whats-coming)

### <a name="windows-conditional-access"></a>Условный доступ Windows
Теперь вы можете создавать политики условного доступа через консоль администрирования Intune, чтобы заблокировать компьютерам под управлением Windows доступ к Exchange Online и SharePoint Online. Можно также создать политики условного доступа для блокировки доступа к классическим и универсальным приложениям Office.

### <a name="ios-10-support"></a>Поддержка iOS 10
Существующие сценарии Intune MDM и MAM совместимы с iOS 10. Советы см. в [блоге службы поддержки Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Инструмент упаковки для приложений поддерживает MAM без регистрации устройств для Android и iOS
Инструмент упаковки для приложений Intune — это программа командной строки, которая используется для включения поддержки Intune MAM в бизнес-приложения для iOS и Android. Это самый простой способ внедрить пакет SDK для Intune MAM в приложение, чтобы принудительно применять политики MAM, развернутые в Intune. С помощью политик MAM можно делать следующее.

1. Шифровать данные приложения.
2. Требовать, чтобы информационный работник вводил ПИН-код при запуске приложения.
3. Разрешить приложению перемещать данные только в другие управляемые приложения.
4. Предотвращать архивацию данных приложения в Android, iTunes и iCloud.
5. Разрешать вырезание, копирование и вставку только в других управляемых приложениях.

Общедоступная предварительная версия обновленного инструмента упаковки для приложений Intune теперь поддерживает MAM без регистрации устройства во внутренних бизнес-приложениях в iOS и Android. Это означает, что конечным пользователям не требуется регистрировать устройства в Intune, чтобы использовать бизнес-приложения с поддержкой MAM.

Любой пользователь может протестировать общедоступную предварительную версию и прочитать полезную документацию, расположенную в GitHub msintuneappsdk.

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Перед установкой и использованием инструмента упаковки для приложений Microsoft Intune для предварительных выпусков Android и iOS необходимо выполнить следующее.

* Ознакомиться с условиями лицензии Майкрософт для инструмента упаковки для приложений Microsoft Intune для предварительных выпусков Android и iOS
* Распечатать и сохранить копию условий лицензии для своих записей. Скачивая и используя инструмент упаковки для приложений Microsoft Intune для предварительных выпусков Android, вы соглашаетесь с этими условиями лицензии. Если вы не согласны, не используйте это программное обеспечение.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Переход групп Intune в Azure Active Directory начнется в сентябре
В новых учетных записях Intune будут использоваться группы безопасности Azure Active Directory, а не группы пользователей Intune. Вы будете знать, что работаете с группами безопасности, так как на странице групп портала Intune будет ссылка, указывающая на портал управления Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Интеграция Lookout для защиты устройств Android
Майкрософт интегрируется с решением мобильной защиты от угроз Lookout для защиты мобильных устройств Android путем обнаружения вредоносных программ, опасных приложений и многого другого на устройствах. Решение Lookout помогает определить настраиваемый уровень угроз. Вы можете создать правило политики соответствия в Intune, чтобы определить соответствие устройств на основе оценки рисков Lookout. Используя политики условного доступа, вы можете разрешить или заблокировать доступ к ресурсам организации на основе состояния соответствия устройства.

Чтобы конечные пользователи не соответствующих политике устройств могли получить к ним доступ, потребуется зарегистрироваться, установить приложение Lookout for Work на устройствах Android, активировать приложение и устранить угрозы в приложении Lookout for Work. Дополнительные сведения см. в разделе [Ограничение доступа на основе риска для устройства, сети и приложений](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Обновления корпоративного портала

__Android__

<p style="margin-left: 40px">**Добавление элемента "Уведомления" в корпоративный портал для Android**<br/>
<p style="margin-left: 40px">На домашнюю страницу корпоративного портала для Android добавлен новый значок — "Уведомления". Если коснуться этого значка, вы перейдете на страницу "Уведомления". Здесь для пользователей будут показаны все элементы в приложении корпоративного портала, на которые нужно обратить внимание, например несоответствие устройств, обновление и активация регистрации. В приложении корпоративного портала для iOS уже есть такой интерфейс уведомлений. С появлением страницы "Уведомления" страница "Настройка доступа к ресурсам организации" уже не будет отображаться при каждом запуске или возобновлении работы корпоративного портала для Android, если устройство уже зарегистрировано. Если вы создаете собственное руководство для конечных пользователей, возможно, придется обновить документацию, чтобы отразить это изменение. Обновленные снимки экрана см. [здесь](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Изменения в поддержке для приложения корпоративного портала в iOS**<br/>
<p style="margin-left: 40px">Теперь всем пользователям приложения корпоративного портала Microsoft Intune для iOS необходимо использовать последнюю версию. Новые пользователи могут скачать только последнюю версию, а существующим пользователям требуется обновить ее. Для использования последней версии необходима ОС iOS 8.0 или более поздней версии, поэтому на устройствах под управлением более старых версий iOS невозможно пользоваться корпоративным порталом и регистрировать устройства. Для этого нужно обновить версию iOS до 8.0 или более поздней версии, а затем обновить приложение корпоративного портала до последней версии. Зарегистрированные устройства под управлением iOS с версией ниже 8.0 будут по-прежнему отображаться в консоли администрирования Intune, где ими по-прежнему можно будет управлять.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Улучшения в способах доступа к приложениям для конечных пользователей iOS**<br/>
<p style="margin-left: 40px">В плитки приложений в приложении корпоративного портала для iOS будут внесены описанные ниже изменения. Различные представления для всех пользовательских приложений будут помещены в централизованное расположение — на веб-сайт корпоративного портала. Ограничения корпорации Apple запрещают размещать в приложении корпоративного портала бизнес-приложения и управляемые приложения из магазина приложений, поэтому для поиска всех своих приложений пользователям приходится открывать различные представления.

<p style="margin-left: 40px">Плитка **Приложения организации** раньше указывала на список всех приложений на вкладке "ВСЕ" веб-сайта корпоративного портала, и она будет продолжать работать так же. Название плитки было изменено на **Все приложения**.

<p style="margin-left: 40px">Плитка **Другие приложения** раньше указывала на представление в приложении корпоративного портала, в котором перечислены все приложения, которые Apple разрешает отображать в приложении корпоративного портала. Название плитки было изменено на **Рекомендуемые приложения**. Коснувшись этой плитки, пользователь перейдет на вкладку "РЕКОМЕНДУЕМЫЕ" веб-сайта корпоративного портала.

<p style="margin-left: 40px">Плитка **Категории** раньше указывала на представление со списком категорий приложений, расположенное в приложении корпоративного портала. Название плитки не изменилось, но теперь она указывает на вкладку "КАТЕГОРИИ" веб-сайта корпоративного портала. Обновленные снимки экрана см. [здесь](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Запрос на установку приложения Managed Browser в iOS (если ИТ-специалист настроит это требование для приложения)**<br/>
<p style="margin-left: 40px">Если вы настроили открытие веб-клипа только в управляемом браузере, но управляемый браузер не установлен на устройстве, в приложении корпоративного портала на устройстве пользователям будет предлагаться установить управляемый браузер перед установкой веб-клипа.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**В приложение корпоративного портала для Windows Phone 8.1 добавлена кнопка обратной связи**<br/>
<p style="margin-left: 40px">Приложение корпоративного портала для Windows Phone 8.1 позволяет конечным пользователям отправлять отзывы о приложении с помощью новой кнопки "Отправить отзыв". Чтобы найти кнопку, коснитесь значка с тремя точками в правом нижнем углу экрана приложения корпоративного портала и выберите команду **Отправить отзыв**. Собранные и анонимизированные отзывы помогут Майкрософт совершенствовать работу приложения корпоративного портала с точки зрения пользователей.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Глоссарий Intune</br>
Мы добавили в библиотеку новый [раздел глоссария](https://docs.microsoft.com/intune/understand-explore/intune-glossary), помогающий понять некоторые термины, используемые в продукте Intune.

## <a name="august-2016"></a>Август 2016 г.
### <a name="app-management"></a>Управление приложениями
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Скрытые и отображающиеся приложения для iOS 9.3__. Для устройств под управлением iOS 9.3 или более поздней версии можно использовать список скрытых и отображаемых приложений в политике общей конфигурации в следующих целях:
- Указание списка приложений, которые будут скрыты от пользователей. Пользователи будут видеть и не смогут запускать эти приложения.
- Указание списка приложений, которые пользователи будут видеть и смогут запускать. Другие приложения не будут доступны для просмотра или запуска.

К числу приложений, которые можно указать, относятся как развернутые, так и встроенные приложения iOS, такие как "Сообщения" и "Заметки". Дополнительные сведения см. в статье [Параметры политики iOS в Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Политика разрешенных и заблокированных приложений для устройств Samsung KNOX__. Теперь вы можете настроить пользовательскую политику для устройств Samsung KNOX, которая позволяет создать следующее:
- Список приложений, запуск которых заблокирован на конкретном устройстве. Даже если такое приложение установлено, его невозможно активировать на устройстве.
- Список приложений, которые пользователи устройства могут установить из магазина Google Play. Другие приложения невозможно установить из магазина.

Эти настройки могут использовать только устройства под управлением Samsung KNOX.
Подробные сведения см. в статье [Использование настраиваемых политик для разрешения и блокировки приложений для устройств Samsung KNOX](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Новые приложения, совместимые с политиками системы управления мобильными приложениями (MAM)__. Приложение Yammer для [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) и [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) теперь совместимо с [политиками системы управления мобильными приложениями Intune (MAM)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) независимо от того, зарегистрировано устройство или нет.

Полный список совместимых с MAM приложений см. на сайте [партнеров по приложениям Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Приложения Intune Viewer__. С выпуском нового приложения для управления RMS-доступом мы удаляем следующие приложения Intune Viewer начиная с августа 2016 года:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer для Android в Google Play

Вместо приложений Intune Viewer мы рекомендуем использовать новое [приложение управления правами (RMS-доступом) для Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), которое позволяет развернуть одно, а не три отдельных приложения для безопасного просмотра корпоративных файлов на устройствах. Когда приложение Intune Viewer больше не будет поддерживаться, оно будет удалено из магазина Google Store и станет недоступным для использования в будущем.

### <a name="device-management"></a>Управление устройствами
__Поддержка Android 7.0__ Intune обеспечивает поддержку уровня "день 0" для следующей операционной системы, Android 7.0, для мобильных устройств.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Удаление возможности удаленного сброса секретного кода на устройствах с Android 7.0 компанией Google
Google удаляет возможность для ИТ-администраторов и конечных пользователей удаленно сбрасывать секретный код на устройствах с Android 7.0. Ранее ИТ-администраторы могли удаленно сбросить секретный код пользователя, а конечные пользователи могли сбросить свои секретные коды на веб-сайте корпоративного портала.



### <a name="company-portal-updates"></a>Обновления корпоративного портала
__Веб-сайт корпоративного портала__
- **Ссылка на корпоративном портале для отправки отзыва в корпорацию Майкрософт** <br/>
Веб-сайт корпоративного портала позволяет конечным пользователям перейти по новой ссылке "Обратная связь" в нижней части страницы, чтобы отправить отзывы о работе сайта в корпорацию Майкрософт. Собранные и анонимизированные отзывы помогут Майкрософт совершенствовать работу веб-сайта корпоративного портала (с точки зрения пользователей).
<!--- TFS 1313657 checked--->

__iOS__
- **Минимальная версия Managed Browser для iOS изменена на 8.0**<br/>
Приложение Microsoft Intune Managed Browser для iOS обновлено для поддержки устройств под управлением iOS 8.0 или более поздней версии. На устройствах под управлением iOS 7.1 по-прежнему можно использовать текущую версию приложения Managed Browser. Но мы рекомендуем сообщить пользователям о необходимости обновления iOS до версии 8.0 или более поздней, чтобы они могли воспользоваться всеми преимуществами новых функций Managed Browser.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Предстоящие изменения
__Переход групп Intune на группы Azure Active Directory начиная с сентября 2016 года__. Сейчас Intune создает новый интерфейс управления группами, который использует группы безопасности Azure Active Directory (AAD) в качестве групп пользователей и устройств в Intune. **Когда мы представим новый портал администрирования Intune на основе Azure**, эти группы будут использоваться для управления всеми группами, развертывания политик и профилей.

Таким образом, вам не придется дублировать группы в разных службах. **Кроме того, этот интерфейс предоставляет доступ к некоторым новым компонентам группы Azure Active Directory Premium (AADP)** и обеспечивает расширяемость благодаря использованию PowerShell и Graph. Это также унифицирует интерфейс управления группами в решении по управлению корпоративной мобильностью.

Чтобы обеспечить переход на использование групп безопасности, интерфейс в **текущей консоли администрирования** подвергнется некоторым изменениям. **Сведения об этих изменениях и использовании групп безопасности AAD будут внесены в документацию по Intune**.

Пользователи, которые только начали знакомиться с Intune, увидят **некоторые изменения групп безопасности раньше уже имеющихся клиентов**.

Помимо изменений в управлении группами **следующие функциональные возможности будут объявлены устаревшими**:
- исключение участников или групп при создании группы;
- группы **Несгруппированные пользователи** и **Несгруппированные устройства**;
- **управление группами** в роли администратора службы;
- настраиваемые оповещения на основе групп для правил уведомлений;
- сведение с использованием групп в отчетах.
<!--- TFS 1295329--->

__Добавление элемента "Уведомления" на корпоративный портал для Android__. В сентябре будет выпущено обновление корпоративного портала для Android: на домашней странице будет представлен новый значок **Уведомления**. Если коснуться этого значка, будет выполнен переход на страницу **Уведомления**. Здесь для пользователя будут приведены все элементы в приложении корпоративного портала, на которые нужно обратить внимание, например несоответствие устройств, обновление и активация регистрации. Это обновление также можно увидеть при использовании приложения корпоративного портала iOS. С появлением страницы **Уведомления** вы не будете видеть страницу **Настройка доступа компании** при каждом запуске или возобновлении работы корпоративного портала для Android, если устройство уже зарегистрировано. Мы знаем, что многие из вас создали руководство для пользователей, и понимаем важность предварительного уведомления, когда для вашего руководства или снимков экрана может потребоваться обновление. Обновите свою документацию с учетом предстоящих изменений в интерфейсе. Чтобы скачать обновленные снимки экрана, перейдите по адресу: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Устаревание служб
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Изменения в поддержке для приложения корпоративного портала в iOS**<br/>
В сентябре использование последней версии приложения корпоративного портала Microsoft Intune для iOS станет обязательным для всех пользователей. Новые пользователи смогут скачать только последнюю версию, а текущие пользователи должны будут обновить приложение до нее. Для использования последней версии необходима ОС iOS 8.0 или более поздней версии, поэтому на устройствах под управлением более старых версий iOS будет невозможно пользоваться корпоративным порталом и регистрировать устройства. Чтобы это стало возможным, нужно обновить версию iOS до 8.0 или более поздней версии, а затем обновить приложение корпоративного портала до последней версии. Зарегистрированные устройства под управлением iOS с версией ниже 8.0 будут по-прежнему отображаться в консоли администрирования Intune, где ими по-прежнему можно будет управлять.  

- **Минимальная версия Managed Browser для iOS изменена на 8.0**<br/>
В августе будет выпущено обновление для приложения Microsoft Intune Managed Browser для iOS. Это обновление поддерживает только устройства под управлением iOS версии 8.0 или более поздней. На устройствах под управлением iOS версии 7.1 все еще можно будет использовать текущую версию приложения Managed Browser. Однако мы рекомендуем сообщить пользователям о необходимости обновления iOS до версии 8.0 или более поздней, чтобы они могли воспользоваться всеми преимуществами новых функций Managed Browser.  
<!---TFS 1313253--->

- **Приложения "Корпоративный портал" для Windows 8 и Windows Phone 8 признаны устаревшими начиная с сентября 2016 года** <br/>
Начиная с сентября 2016 года Microsoft Intune прекращает поддержку приложений "Корпоративный портал" Microsoft Intune для платформ Windows Phone 8 и Windows 8. Чтобы продолжить распространение приложений на эти устройства, обновите устройства до Windows 8.1 и Windows Phone 8.1 и используйте соответствующие приложения "Корпоративный портал" для Windows 8.1 и Windows Phone 8.1.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Июль 2016 г.
### <a name="app-management"></a>Управление приложениями

__Улучшение возможности обновления профиля подготовки приложения__. В мобильные бизнес-приложения Apple iOS включен профиль подготовки и код, подписанный сертификатом. При запуске приложения на устройстве iOS операционная система подтверждает целостность приложения iOS и принудительно применяет политики, определенные в профиле подготовки.

Срок действия корпоративного сертификата подписи, который используется для подписи приложений, обычно составляет 3 года. Однако срок действия профиля подготовки истекает через 1 год. Вместе с этим обновлением Intune предоставляет инструменты для упреждающего развертывания новой политики профиля подготовки на устройствах с приложениями, срок действия которых вскоре истекает, хотя сертификат все еще действителен. Дополнительные сведения см. в статье [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Обновление бизнес-приложений с помощью политик профиля подготовки для мобильных устройств iOS).
<!--- TFS 1280247--->

__Пакет SDK для Xamarin доступен для приложений Intune__. Пакет SDK для Xamarin позволяет использовать возможности управления мобильными приложениями Intune в мобильных приложениях iOS и Android, созданных с помощью Xamarin. Этот компонент можно найти в [хранилище Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) или на [странице GitHub для Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Управление устройствами
__Увеличенные ограничения на регистрацию устройств__. Максимальное число настраиваемых устройств, которые можно зарегистрировать в Intune, увеличено с 5 до 15 на одного пользователя.
<!---TFS 1289896 --->

__Интеграция TeamViewer для компьютеров Windows с клиентским ПО Intune__
[Интеграция TeamViewer](https://www.teamviewer.com) для компьютеров с ОС Windows под управлением клиентского программного обеспечения Intune позволяет устанавливать сеансы удаленного помощника с этими компьютерами для вашего отдела технической поддержки. Сюда входят Windows 7, 8, 8.1 и Windows 10. Дополнительные сведения см. в статье [Общие задачи управления ПК с ОС Windows и клиентом Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Обновления корпоративного портала

__Веб-сайт корпоративного портала__
- **Повышено удобство регистрации устройств Windows конечными пользователями**<br/>
Упрощены шаги регистрации для Windows 8.1, Windows 10 Desktop и Windows 10 Mobile на веб-сайте корпоративного портала (при использовании условного доступа). Теперь пользователи будут видеть отдельные шаги "Регистрация устройства" и "Подключение к рабочему месту". Это упрощает просмотр состояния устройства и завершение процесса при сбое подключения к рабочему месту. Кроме того, отдельные шаги должны упростить процесс устранения неполадок для администраторов ИТ. Раньше, когда пользователи пытались зарегистрироваться и подключиться к рабочему месту (при успешной регистрации, но сбое подключения), зарегистрированное устройство не отображалось в списке устройств, вызывая замешательство пользователей.

__Android__
- **Приложение корпоративного портала для Android**<br/>
Если на устройстве Android отобразилось сообщение об ошибке, информирующее об отсутствии необходимого сертификата, [действия](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) по установке отсутствующего сертификата можно получить, нажав кнопку "Решение проблемы". Если после выполнения этих действий сообщение об ошибке все еще отображается, пользователям будет предложено обратиться к администратору ИТ, предоставив ему [ссылку](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) на этот раздел, где описаны действия, которые он может предпринять, чтобы решить проблему с сертификатом.

- **Разрешение установки приложений на стороне клиента только для зарегистрированных устройств**<br/>
На устройствах Android, которые не были зарегистрированы в Intune с помощью приложения корпоративного портала Intune для Android, больше нельзя устанавливать приложения через веб-сайт корпоративного портала.
<!---TFS 1299082--->

__iOS__
- **Изменения в учетных записях диспетчеров регистрации устройств в приложении корпоративного портала для iOS**<br/>
Чтобы повысить производительность и масштабируемость, Intune больше не отображает все диспетчеры регистрации устройств (DEM) в области **Мои устройства** приложения корпоративного портала iOS. Теперь отображается только локальное устройство, на котором выполняется приложение, и только в том случае, если оно зарегистрировано через приложение корпоративного портала.

Пользователь диспетчера регистрации устройств может выполнять действия на локальном устройстве, однако удаленно управлять другими зарегистрированными устройствами можно только из консоли администрирования Intune. Кроме того, Intune прекращает использование учетных записей диспетчеров регистрации устройств за счет применения программы регистрации устройств Apple или средства Apple Configurator. Оба этих метода уже поддерживают регистрацию общих устройств iOS без привлечения пользователя.

Используйте учетные записи диспетчеров регистрации устройств только в том случае, когда регистрация общих устройств без привлечения пользователя недоступна. Дополнительные сведения см. в статье [Регистрация корпоративных устройств с помощью диспетчера регистрации устройств в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Изменение названий компонентов Windows
- [Microsoft Passport для Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) теперь называется **Windows Hello для бизнеса**.
- [Защита корпоративных данных](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) теперь называется **Windows Information Protection**.

## <a name="june-2016"></a>Июнь 2016 г.
### <a name="intune-service-health"></a>Работоспособность службы Intune
Сведения о работоспособности службы Intune были перемещены в центральное расположение с другими службами Майкрософт. Эти сведения теперь доступны на портале управления Office 365 в разделе о работоспособности службы. Дополнительные сведения см. в [этой записи блога](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Управление приложениями
- **Улучшения в процедуре настройки политик данных предприятия в Windows 10.** Мы внесли улучшения в процедуру настройки политик защиты корпоративных данных в Windows 10. Они касаются создания правил для приложений, определения границ сети и других параметров защиты корпоративных данных. Дополнительные сведения см. в статье [Создание политики защиты данных предприятия (EDP) с помощью Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Управление устройствами
- **Параметр политики Защитника Windows для защиты от потенциально нежелательных приложений.** В общую политику конфигурации для Windows 10 Desktop и Mobile добавлен новый параметр Защитника Windows под названием **Обнаружение потенциально нежелательных приложений**. Этот параметр можно использовать для защиты зарегистрированных настольных компьютеров с Windows от программ, которые Защитник Windows определил как потенциально нежелательные. Можно настроить защиту от запуска этих приложений или использовать режим аудита для оповещения об установке потенциально нежелательного приложения. Дополнительные сведения см. в статье [Параметры политики Windows 10 в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Условный доступ
- **Политика управления доступом к сети в ISE Cisco для Intune.**  Клиенты, которые используют Cisco Identity Service Engine (ISE) 2.1 и Microsoft Intune, могут настроить политику управления доступом к сети в ISE.

    При использовании этой политики доступ для устройств, которым требуется подключение к сети через VPN или Wi-Fi, предоставляется только при соблюдении следующих условий:

    * Устройства должны находиться под управлением Intune.
    * Устройства должны удовлетворять всем развернутым политикам соответствия требованиям Intune.

 Конечные пользователи устройств, не соответствующих политике, получат запрос на регистрацию, и для получения доступа должны устранить все проблемы с соответствием.
- **Условный доступ для браузера.** Для [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) и [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) можно задать политику условного доступа, чтобы доступ к ним имели только поддерживаемые веб-браузеры на управляемых и соответствующих политике устройствах iOS и Android. Пользователям, пытающимся войти на сайты Outlook Web Access (OWA) и SharePoint с устройств iOS и Android, будет предложено сначала зарегистрировать устройство в Intune, а также устранить все несоответствия.
<!---TFS 1175844--->

- **Dynamics CRM Online поддерживает условный доступ.** Клиенты могут задать политику условного доступа для службы [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) так, чтобы доступ к ней имели только управляемые и соответствующие политике устройства iOS и Android. Конечным пользователям, которые попытаются войти в мобильное приложение Dynamics CRM в iOS и Android, будет предложено сначала зарегистрироваться в Intune, а также устранить все несоответствия требованиям.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Обновления корпоративного портала Intune

__Приложение корпоративного портала для Android__

- Когда ИТ-администратор применяет новую политику "На устройствах должна быть запрещена установка приложений из неизвестных источников (Android 4.0+)", на устройствах под управлением Android 4.0 и более поздних версий будет выводиться сообщение "Установку из неизвестных источников необходимо отключить". Пользователям потребуется перейти в меню **Настройки** > **Безопасность** и выключить параметр **Неизвестные источники**. По ссылке в сообщении о соответствии приводятся дополнительные [сведения](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) о сообщении и о причинах, по которым необходимо отключить этот параметр.

- Когда ИТ-администратор применяет новую политику "На устройствах должна быть включена проверка приложений на предмет угроз безопасности (Android 4.0+)", на устройствах под управлением Android 4.0 и более поздних версий будет выводиться сообщение "Проверьте устройство на предмет угроз безопасности". Пользователям потребуется перейти в меню **Настройки** > **Google** > **Безопасность** и включить параметр **Проверка устройства на предмет угроз безопасности**. По ссылке в сообщении о соответствии приводятся дополнительные [сведения](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) о сообщении и о причинах, по которым необходимо включить этот параметр.

- Когда ИТ-администратор применяет новую политику "На устройствах должна быть отключена отладка по USB (Android 4.2+)", на устройствах под управлением Android 4.2 и более поздних версий будет выводиться сообщение "Необходимо отключить отладку по USB". Пользователям потребуется перейти в меню **Настройки** > **Для разработчиков** и отключить параметр **Отладка по USB**. По ссылке в сообщении о соответствии приводятся дополнительные [сведения](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) о сообщении и о причинах, по которым необходимо отключить этот параметр.

- Когда ИТ-администратор применяет новую политику "Минимальная версия исправления безопасности Android (Android 6.0+)", на устройствах под управлением Android 6.0 и более поздних версий будет выводиться сообщение "На устройстве отсутствует минимальная версия исправления безопасности Android". Пользователям потребуется установить исправление безопасности. По ссылке в сообщении о соответствии приводятся дополнительные [сведения](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) о том, как установить исправление безопасности и просмотреть установленную версию исправления безопасности.

__Приложение корпоративного портала для iOS__

- Теперь пользователям будет предложена улучшенная процедура установки бизнес приложений. Если установка приложения занимает много времени, пользователи могут вручную синхронизировать свои устройства, чтобы принудительно возобновить процесс синхронизации. Инструкции для конечных пользователей см. в статье [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Синхронизация устройства с iOS вручную).

- Приложение корпоративного портала Microsoft Intune для iOS было обновлено для обеспечения поддержки iOS 8.0 и более поздних версий. Это обновление означает, что пользователи смогут установить приложение корпоративного портала и зарегистрировать новые устройства в Intune только в том случае, если устройство работает под управлением iOS 8.0 или более поздней версии. Пользователи, которые уже зарегистрировали устройства с неподдерживаемой версией iOS, могут продолжать использовать приложение корпоративного портала на своем устройстве.


<!--HONumber=Jan17_HO1-->


