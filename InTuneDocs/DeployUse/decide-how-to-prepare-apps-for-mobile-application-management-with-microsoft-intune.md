---
# required metadata

title: Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune
Можно позволить приложениям использовать политики управления мобильными приложениями, используя инструмент упаковки приложений Intune или пакет SDK для приложений Intune. Используйте приведенные сведения для изучения этих двух методов и способов их использования.

## Инструмент упаковки приложений Intune
Инструмент упаковки приложений используется в основном для внутренних бизнес-приложений. Инструмент представляет собой приложение командной строки, которое создает оболочку вокруг приложения, что позволяет управлять приложением с помощью политики управления мобильными приложениями Intune. Для использования инструмента исходный код не требуется, однако необходимы учетные данные подписи.  Дополнительные сведения об учетных данных подписи см. в [блоге Intune](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx). Документацию к инструменту см. в статьях [Инструмент упаковки приложений Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) и [Инструмент упаковки приложений iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)..

Инструмент упаковки приложений не поддерживает приложения в Магазине приложений или Google Play, а также функции, требующие интеграции во время разработки (см. следующую таблицу сравнения функций).

Инструмент упаковки приложений следует использовать вместо пакета SDK, если приложение уже было записано или исходный код недоступен.

## Пакет SDK для приложений Intune
Пакет SDK для приложений предназначен главным образом для клиентов, имеющих приложения в Магазине приложений или Google Play и стремящихся управлять приложениями с помощью Intune. Однако преимуществами интеграции пакета SDK может воспользоваться любое приложение, даже бизнес-приложение.

Для интеграции пакета SDK вам нужен доступ к исходному коду приложения. Инструкции по интеграции пакета SDK см. в разделе [Пакет SDK для приложений Microsoft Intune](https://msdn.microsoft.com/library/mt627769.aspx)..

## Сравнение функций
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
|Require fingerprint instead of PIN (iOS only) (Запрашивать отпечатки пальцев вместо ПИН-кода, только iOS)<br></br>**Примечание.** Доступно только в средах MAM.|X||
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

### См. также
[Инструмент упаковки приложений Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Инструмент упаковки приложений iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Подготовка приложений для управления мобильными приложениями с помощью пакета SDK](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->

