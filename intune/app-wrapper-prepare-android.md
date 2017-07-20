---
title: "Создание программы-оболочки для приложений Android с помощью соответствующего инструмента"
description: "В этой статье описано, как создать программу-оболочку для приложений Android, не меняя код самого приложения, а также подготовить приложения для применения политики управления мобильными приложениями."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 299e2ed0a84c7158a582ee874f0711eb3c379532
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2017
---
# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Подготовка приложений Android для управления мобильными приложениями с помощью инструмента упаковки для приложений Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Инструмент упаковки для приложений Microsoft Intune для Android используется для изменения поведения внутрикорпоративных приложений Android за счет ограничения возможностей приложения без изменения кода самого приложения.

Этот инструмент представляет собой программу командной строки Windows, которая выполняется в PowerShell и создает "оболочку" вокруг приложения Android. После упаковки приложения его функциональность можно изменить, настроив [политики управления мобильными приложениями](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) в Intune.


Перед запуском инструмента просмотрите раздел [Вопросы безопасности при запуске инструмента упаковки для приложений](#security-considerations-for-running-the-app-wrapping-tool). Чтобы скачать этот инструмент, посетите раздел [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) (Инструмент упаковки для приложений Microsoft Intune для Android) на GitHub.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Выполнение необходимых условий для использования средства изоляции приложений

-   Инструмент упаковки для приложений необходимо запустить на компьютере под управлением Windows 7 или более поздней версии Windows.

-   Входное приложение должно представлять собой допустимый пакет приложения Android с расширением APK, а также:

    -   не может быть зашифровано;
    -   не может быть упаковано с помощью инструмента упаковки для приложений Intune;
    -   должно быть написано для Android 4.0 или более поздней версии.

-   Приложение должно быть разработано внутри вашей компании или по ее заказу. Этот инструмент невозможно использовать для приложений, скачанных из магазина Google Play.

-   Чтобы запустить инструмент, необходимо установить последнюю версию [среды выполнения Java](http://java.com/download/) и убедиться, что для переменной пути Java в переменных среды Windows задано значение C:\ProgramData\Oracle\Java\javapath. Дополнительные сведения см. в [документации по Java](http://java.com/download/help/).

    > [!NOTE]
    > В некоторых случаях 32-разрядная версия Java может привести к проблемам с памятью. Рекомендуется установить 64-разрядную версию.

- В Android все пакеты приложений (.apk) должны быть подписаны. Используйте средство Java KeyTool для создания учетных данных, необходимых для подписи упакованного выходного приложения. Например, приведенная ниже команда использует исполняемый файл Java keytool.exe, чтобы создавать ключи, которые можно применять для подписи в инструменте упаковки для приложений.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Этот пример создает пару ключей (открытый ключ и связанный с ним закрытый 2048-битный ключ) с помощью алгоритма RSA. Затем открытый ключ упаковывается в самозаверяющий сертификат X.509 версии 3, который хранится как цепочка сертификатов из одного элемента. Эти цепочка сертификатов и закрытый ключ хранятся в новом хранилище ключей с именем "mykeystorefile" и определяются по псевдониму "mykeyalias". Запись в хранилище ключей действительна в течение 50 000 дней.

    Команда предложит указать пароли для ключа и хранилища ключей. Используйте безопасные пароли, но не забывайте их, так как они потребуются позже для запуска инструмента упаковки для приложений.

    Подробную документацию по Java [KeyTool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) и Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) можно получить на веб-сайте документации Oracle.

## <a name="install-the-app-wrapping-tool"></a>Установка инструмента упаковки для приложений

1.  Из [репозитория GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) скачайте на компьютер Windows установочный файл инструмента упаковки для приложений Intune в Android — InstallAWT.exe. Откройте установочный файл.

2.  Примите условия лицензионного соглашения, а затем завершите установку.

Запомните папку, в которую был установлен инструмент. По умолчанию используется расположение C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Запуск инструмента упаковки для приложений

1.  На компьютере Windows, где установлен инструмент упаковки для приложений, откройте окно PowerShell.

2.  Из папки, куда был установлен инструмент, импортируйте модуль PowerShell инструмента упаковки для приложений:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Запустите инструмент с помощью команды **invoke-AppWrappingTool** со следующим синтаксисом.
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 В следующей таблице приведены свойства команды **invoke-AppWrappingTool**.

|Свойство|Данные|Пример|
|-------------|--------------------|---------|
|**-InputPath**&lt;строка&gt;|Путь исходного приложения Android (APK).| |
|**-OutputPath**&lt;строка&gt;|Путь к "выходному" приложению Android. Если это тот же путь к каталогу, что и InputPath, произойдет сбой упаковки.| |
|**-KeyStorePath**&lt;строка&gt;|Путь к KEYSTORE-файлу, который содержит пару открытого и закрытого ключей для подписания.|По умолчанию файлы хранилища ключей находятся в папке "C:\Program Files (x86)\Java\jreX.X.X_XX\bin". |
|**-KeyStorePassword**&lt;SecureString&gt;|Пароль, используемый для расшифровки KEYSTORE-файла. Для Android требуется, чтобы все пакеты приложения (с расширением APK) были подписаны. Используйте средство Java KeyTool, чтобы создать пароль для хранилища ключей. Дополнительные сведения о Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) Java см. здесь.| |
|**-KeyAlias**&lt;строка&gt;|Имя ключа, используемого для подписания.| |
|**-KeyPassword**&lt;SecureString&gt;|Пароль, используемый для расшифровки закрытого ключа, который будет использоваться для подписания.| |
|**-SigAlg**&lt;SecureString&gt;| (Необязательно.) Имя используемого алгоритма подписи. Этот алгоритм должен быть совместим с закрытым ключом.|Примеры: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | Команда поддерживает общие параметры PowerShell, такие как verbose и debug (необязательно). |


- Список общих параметров см. в разделе [Центр скриптов Майкрософт](https://technet.microsoft.com/library/hh847884.aspx).

- Чтобы просмотреть подробные сведения об использовании инструмента, введите следующую команду.

    ```
    Help Invoke-AppWrappingTool
    ```

**Пример:**

Импорт модуля PowerShell.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Запустите инструмент упаковки для приложений в собственном приложении HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Затем появится запрос на **KeyStorePassword** и **KeyPassword**. Введите учетные данные, использованные при создании файла ключа хранилища.

Упакованное приложение и файл журнала создаются и сохраняются по указанному выходному пути.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Вопросы безопасности при запуске инструмента упаковки для приложений
Во избежание потенциального спуфинга, раскрытия информации и атак с несанкционированным повышением привилегий:

-   Убедитесь, что входное бизнес-приложение, выходное приложение и Java KeyStore находятся на том же компьютере Windows, где запущен инструмент упаковки для приложений.

-   Импортируйте выходное приложение в консоль Intune на том же компьютере, где запущен инструмент. Дополнительные сведения о Java Keytool см. [здесь](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Если выходное приложение и инструмент расположены по UNC-пути и вы не используете инструмент и входные файлы на одном и том же компьютере, настройте среду на безопасную работу с помощью [протокола IPsec](http://wikipedia.org/wiki/IPsec) или [подписывания SMB](https://support.microsoft.com/kb/887429).

-   Убедитесь, что приложение получено из надежного источника.

-   Обеспечьте безопасность выходного каталога, содержащего упакованное приложение. Рассмотрите возможность использования каталога уровня пользователя в качестве выходного каталога.

### <a name="see-also"></a>См. также
- [Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune](apps-prepare-mobile-application-management.md)

- [Подготовка приложений для управления мобильными приложениями с помощью пакета SDK](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
