---
title: "Новые возможности | Документы Майкрософт"
description: "Новые возможности в выпусках Microsoft Intune этого месяца и за прошлые периоды"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1d9ebc7fd727b80091625ed5256ae634323a9257
ms.openlocfilehash: f7e71d20923e113b533668a7b5aef688de196182


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Новые возможности Microsoft Intune — ноябрь 2016 г.
Узнайте о новых возможностях этого выпуска Microsoft Intune. Кроме того, здесь можно узнать о предстоящих изменениях, к которым следует подготовиться, а также сведения о прошлых выпусках.

> [!Note]
> В будущем все эти функции будут также поддерживаться в гибридных развертываниях (Configuration Manager с Intune). Дополнительные сведения о новых гибридных функциях см. на [странице новых гибридных функций](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Общедоступная предварительная версия нового интерфейса администратора Intune в Azure<!--736542-->
В начале 2017 года мы планируем перенести все административные функции в Azure. Это позволит обеспечить интегрированное и эффективное управление основными рабочими процессами EMS на современной платформе служб, расширяемой с помощью интерфейсов API Graph. Предваряя выпуск общедоступной версии этого портала для всех клиентов Intune, мы рады сообщить, что позже в этом месяце начнем развертывать предварительную версию этого нового интерфейса администрирования для отдельных клиентов.

В интерфейсе администратора на портале Azure будут реализованы уже объявленные возможности группирования и определения целевых объектов. Если применить новые параметры группирования на имеющемся клиенте, на нем также будет реализован новый интерфейс администратора. А пока вы можете узнать, что именно мы приготовили для Microsoft Intune на портале Azure, в нашей [новой документации](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Вопросы о сроках переноса вашего клиента отравляйте нашей команде по миграции по адресу [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Интеграция служб управления телекоммуникационными расходами в общедоступной предварительной версии портала Azure<!--747605-->
В настоящее время мы начинаем предварительную интеграцию со сторонними службами управления телекоммуникационными расходами (TEM) на портале Azure. Используйте службу Intune, чтобы установить ограничения на использование национальных данных и данных, передаваемых в роуминге. Мы начинаем эту интеграцию со службой [Saaswedo](http://www.saaswedo.com). Чтобы включить эту функцию в клиенте пробной версии, [обратитесь в службу поддержки корпорации Майкрософт](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="new-capabilities"></a>Новые возможности

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Многофакторная идентификация на всех платформах <!--747590-->
Теперь Многофакторную идентификацию (MFA) можно применить для определенной группы пользователей во время регистрации устройств iOS, Android, Windows 8.1+, Windows Phone 8.1+ на портале управления Azure. Это можно сделать, настроив MFA в приложении для регистрации Microsoft Intune в Azure Active Directory.

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Возможность ограничения на регистрацию мобильных устройств<!--747596-->
В Intune добавлены новые ограничения на регистрацию, определяющие, какие платформы мобильных устройств разрешено регистрировать. Intune разделяет платформы мобильных устройств на категории: iOS, macOS, Android, Windows и Windows Mobile.
* Ограничение на регистрацию мобильных устройств не означает ограничение на регистрацию клиентов ПК.
* Только для iOS существует один дополнительный параметр для блокировки регистрации персональных устройств.

Все новые устройства в Intune помечаются как персональные, если только ИТ-администратор не отметит их как принадлежащие организации, как описано в [этой статье](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Объявления

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Многофакторная идентификация при выполнении регистрации на портале Azure <!--VSO 750545-->
Ранее, чтобы настроить MFA для процессов регистрации в Intune, администраторы использовали консоль Intune или Configuration Manager (до выпуска за октябрь 2016 г.). В этом обновлении параметры MFA можно настроить на [портале Microsoft Azure](https://manage.windowsazure.com). Для этого на портал нужно войти, используя учетные данные Intune. Дополнительные сведения см. [здесь](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china--vso-658093--"></a>Теперь приложение корпоративного портала для Android доступно в Китае <!--VSO 658093-->
Мы публикуем приложение корпоративного портала для Android, которое можно скачать в Китае. Так как в Китае отсутствует магазин Google Play, это приложение для устройств Android можно скачать в китайских магазинах приложений. Приложение корпоративного портала для Android можно будет скачать в следующих магазинах:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

В этом приложении взаимодействие со службой Microsoft Intune осуществляется с помощью Сервисов Google Play. В настоящее время Сервисы Google Play еще недоступны в Китае, поэтому на выполнение одной из следующих задач понадобится до 8 часов. 

|Консоль администрирования Intune| Приложение корпоративного портала Intune для Android |Веб-сайт корпоративного портала Intune|   
|---|---|---|
|Полная очистка| Удаление удаленного устройства| Удаление устройства (локального и удаленного)|
|Selective wipe (Выборочная очистка)| Сброс устройства| Сброс устройства|
|Развертывание нового или обновленного приложения| Установка доступных бизнес-приложений| Сброс секретного кода устройства|
|удаленная блокировка;|||
|Сброс секретного кода|||

## <a name="deprecations"></a>Устаревшие возможности

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Firefox больше не поддерживает Silverlight<!--VSO TBA-->
Mozilla удаляет поддержку Silverlight в версии 52 [браузера Firefox](https://www.mozilla.org/firefox), начиная с марта 2017 г. В результате вы больше не сможете войти в существующую консоль Intune, с помощью браузера Firefox, версия которого старше 51. Для доступа к консоли администрирования рекомендуется использовать Internet Explorer 10 или 11 либо [версию Firefox, выпущенную до версии 52](https://ftp.mozilla.org/pub/firefox/releases/). Переход Intune на портал Azure позволит решению поддерживать несколько [современных браузеров](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) без зависимости от Silverlight.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Удаление политик мобильных почтовых ящиков Exchange Online <!--770687-->
Начиная с декабря, администраторы больше не смогут просматривать или настраивать политики для мобильных почтовых ящиков Exchange Online (EAS) в консоли Intune. Это изменение будет реализовано на всех клиентах Intune в течение декабря и января. Все имеющиеся политики останутся прежними. Чтобы настроить новые политики, используйте командную консоль Exchange. Дополнительные сведения см. [здесь](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Приложения Intune AV Player, Image Viewer и PDF Viewer больше не поддерживаются в Android <!--747553-->
С середины декабря 2016 года пользователи больше не смогут использовать приложения Intune AV Player, Image Viewer и PDF Viewer. Они были заменены на приложение Azure Information Protection. Дополнительные сведения о приложении Azure Information Protection см. [здесь](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>См. также
* [Блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Стратегии развития облачной платформы](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Новые возможности — архив](whats-new-archive.md)



<!--HONumber=Dec16_HO4-->


