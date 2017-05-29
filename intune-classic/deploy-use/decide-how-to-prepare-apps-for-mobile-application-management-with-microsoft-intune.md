---
title: "Выбор способа подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune | Документация Майкрософт"
description: "Сведения этого раздела помогут решить, когда следует применить инструмент упаковки приложений и пакет SDK, чтобы ваши пользовательские бизнес-приложения могли использовать политики управления мобильными приложениями."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ee746ec2ccd9b924c242e956a8c89fba248ca96
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="prepare-line-of-business-apps-for-mam"></a>Подготовка бизнес-приложений для MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Можно позволить приложениям использовать политики управления мобильными приложениями (MAM), используя инструмент упаковки приложений Intune или пакет SDK для приложений Intune. Используйте приведенные сведения для изучения этих двух методов и способов их использования.

## <a name="intune-app-wrapping-tool"></a>Инструмент упаковки приложений Intune
Инструмент упаковки приложений используется в основном для внутренних бизнес-приложений. Инструмент представляет собой программу командной строки, которая создает оболочку вокруг приложения, что позволяет управлять приложением с помощью политики MAM Intune.

Для использования инструмента исходный код не требуется, однако необходимы учетные данные подписи.  Дополнительные сведения об учетных данных подписи см. в [блоге Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Документацию по инструменту упаковки приложений см. в статьях [Инструмент упаковки приложений Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) и [Инструмент упаковки приложений iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Инструмент упаковки приложений **не** поддерживает Apple App Store или Магазин Google Play. Кроме того, он не поддерживает отдельные функции, требующие интеграции во время разработки (см. следующую таблицу сравнения функций).


Дополнительные сведения о средстве упаковки приложений для MAM на устройствах, не зарегистрированных в Intune, см. в разделе [Защита бизнес-приложений и данных на незарегистрированных устройствах](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Причины для использования инструмента упаковки приложений
* В приложении отсутствуют встроенные функции защиты данных.
* Приложение является относительно простым.
* Приложение развертывается для внутренних целей.
* Отсутствует доступ к исходному коду приложения.
* Вы не являетесь разработчиком приложения.
* Приложение поддерживает минимальные действия по проверке подлинности пользователя.


### <a name="supported-app-development-platforms"></a>Поддерживаемые платформы разработки приложений

|**Инструмент упаковки приложений** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |да|да|
|**Android**| Нет |да|

## <a name="intune-app-sdk"></a>Пакет SDK для приложений Intune
Пакет SDK для приложений предназначен главным образом для клиентов, имеющих приложения в Apple App Store или Магазине Google Play и стремящихся управлять ими с помощью Intune. Однако преимуществами интеграции пакета SDK может воспользоваться любое приложение, даже бизнес-приложение.

Дополнительные сведения о пакете SDK см. в разделе [Обзор](../develop/intune-app-sdk.md). Сведения о начале работы с пакетом SDK см. в статье [Начало работы с пакетом SDK для приложений Microsoft Intune](../develop/intune-app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>Причины для использования пакета SDK
* В приложении отсутствуют встроенные функции защиты данных.
* Приложение является относительно сложным и обладает разветвленным интерфейсом.
* Приложение развертывается в общедоступном магазине приложений, например Google Play или Apple App Store.
* Вы являетесь разработчиком приложения и располагаете техническими знаниями по использованию пакета SDK.
* В приложении используется интеграция с другими пакетами SDK.
* Приложение часто обновляется.

### <a name="supported-app-development-platforms"></a>Поддерживаемые платформы разработки приложений

|**Пакет SDK для приложений Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Да, используйте [компонент Xamarin из пакета SDK для приложений Intune](../develop/intune-app-sdk-xamarin.md).|Да, используйте [подключаемый модуль Cordova из пакета SDK для приложений Intune](../develop/intune-app-sdk-cordova.md).|
|**Android**| Да, используйте [компонент Xamarin из пакета SDK для приложений Intune](../develop/intune-app-sdk-xamarin.md).|Да, используйте [подключаемый модуль Cordova из пакета SDK для приложений Intune](../develop/intune-app-sdk-cordova.md).|

## <a name="feature-comparison"></a>Сравнение функций
В этой таблице перечислены параметры, которые можно использовать для пакета SDK приложений и инструмента упаковки приложений.

> [!NOTE]
> Инструмент упаковки приложений можно использовать с автономной службой Intune или службой Intune с Configuration Manager.

|Компонент|Пакет SDK для приложений|Инструмент упаковки приложений|
|-----------|---------------------|-----------|
|Отображать веб-содержимое только в корпоративном управляемом браузере|X|X|
|Prevent Android, iTunes or iCloud backups (Запретить резервное копирование в Android, iTunes или iCloud)|X|X|
|Разрешить приложению передавать данные в другие приложения|X|X|
|Разрешить приложению получать данные из других приложений|X|X|
|Ограничить вырезание, копирование и вставку данных между приложениями|X|X|
|Требовать простой PIN-код для доступа|X|X|
|Замена встроенного ПИН-кода приложения на ПИН-код Intune|X||
|Specify the number of attempts before PIN reset (Указать число попыток до сброса ПИН-кода)|X|X|
|Разрешить вход с использованием отпечатков пальцев вместо ПИН-кода |X|X|
|Требовать корпоративные учетные данные для доступа|X|X|
|Block managed apps from running on jailbroken or rooted devices (Запретить запуск управляемых приложений на устройствах со снятой защитой или административным доступом)|X|X|
|Шифрование данных приложения|X|X|
|Recheck the access requirements after a specified number of minutes (Проверять требования доступа повторно через указанное число минут)|X|X|
|Specify the offline grace period (Указать льготный период автономности)|X|X|
|Block screen capture (Android only) (Блокировать снимки экрана, только Android)|X|X|
|Полная очистка|X|X|
|выборочная очистка; <br></br>**Примечание.** При удалении профиля управления для iOS удаляется и приложение.|X||
|Запретить "Сохранить как" |X||
|Support for Multi-Identity (Поддержка множественного удостоверения)|X||
|Поддержка MAM без регистрации устройства|X|X|
|Настраиваемый стиль |X|||
### <a name="see-also"></a>См. также

[Инструмент упаковки приложений Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Инструмент упаковки приложений iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Подготовка приложений для управления мобильными приложениями с помощью пакета SDK](use-the-sdk-to-enable-apps-for-mobile-application-management.md)

