---
title: "Сбор журналов устройств | Документы Майкрософт"
description: "Узнайте, как собирать журналы с управляемых устройств."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 211b996263aae7a42f8370eb343c7e759ef87790
ms.openlocfilehash: 5aae8edd2b851eb94156e82bc9b6e604644cb900


---

# <a name="device-logs"></a>Журналы устройств

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

При устранении неполадок вам могут потребоваться журналы с устройств пользователя. Ниже описаны инструкции для сбора этих журналов. Для сбора обычно необходим доступ к устройству или одобрение от пользователя на сбор журналов и их отправку.

### <a name="android-logs"></a>Журналы Android
Журналы в Android расположены в каталоге *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Иногда файлы не отображаются, особенно на новых устройствах с Android. В этом случае конечным пользователям следует открыть приложение корпоративного портала для Android. Затем им нужно последовательно выбрать **Параметры**>**Копировать журналы** и перезагрузить устройство.

Дополнительные сведения о том, как пользователи могут отправлять вам журналы данных, см. в следующих статьях:

- [Использование подробного журнала для помощи ИТ-администратору в устранении неполадок на устройствах](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) описывает, как пользователи могут включить функцию ведения подробных журналов, которая автоматически отправляет вам все данные журналов. По умолчанию подробное ведение журнала включено.

- [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune/enduser/send-logs-to-your-it-admin-by-email-android)

- [Отправка журналов диагностических данных ИТ-администратору по USB-кабелю](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Журналы iOS

Пользователь может отправить вам ошибки регистрации, как описано в разделе [Отправка ошибок регистрации iOS ИТ-администратору](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Журналы Mac OS X

1. Откройте консоль приложение **Консоль**.
2. В разделе **ФАЙЛЫ** выберите **system.log**.
3. В строке меню вверху выберите пункты **Файл** > **Сохранить копию как...**. Сохраните файл.

### <a name="windows-phone"></a>Windows Phone

В приложении корпоративного портала для Windows Phone пользователи могут нажать кнопку с многоточием (**...**) для доступа к меню, а затем выбрать команду **Отправить журналы**. Это можно сделать как до, так и после входа в приложение корпоративного портала.

### <a name="windows"></a>Windows

Файлы журнала корпоративного портала Windows расположены в каталоге *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Feb17_HO2-->


