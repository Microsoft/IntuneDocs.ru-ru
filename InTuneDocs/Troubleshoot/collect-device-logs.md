---
title: "Сбор журналов устройств | Microsoft Intune"
description: "Узнайте, как собирать журналы с управляемых устройств."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19b0b502d2c8c261947c461f27a0e8153df5b186
ms.openlocfilehash: 1e65c1fa25e273ba03218f79ebeff611138e8013


---

# <a name="device-logs"></a>Журналы устройств

При устранении неполадок вам могут потребоваться журналы с устройств пользователя. Ниже описаны инструкции для сбора этих журналов. Для сбора обычно необходим доступ к устройству или запрос от пользователя на сбор журналов и их отправку вам.

### <a name="android-logs"></a>Журналы Android
Журналы в Android расположены в каталоге *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

Иногда файлы не отображаются, особенно на новых устройствах с Android. В этом случае конечным пользователям следует открыть приложение корпоративного портала для Android, а затем перейти в раздел **Параметры**, выбрать команду **Копировать журналы** и перезагрузить устройство. 

Дополнительные сведения о том, как пользователи могут отправлять вам журналы данных, см. в следующих статьях:

- [Использование подробного журнала для помощи ИТ-администратору в устранении неполадок на устройствах](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) — описывает, как пользователи могут включить функцию ведения подробных журналов, которая автоматически отправляет вам все данные журналов. По умолчанию подробное ведение журнала включено.

- [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Отправка журналов диагностических данных ИТ-администратору по USB-кабелю](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Журналы iOS

Пользователь может отправить вам ошибки регистрации, как описано в разделе [Отправка ошибок регистрации iOS ИТ-администратору](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Журналы Mac OS X

1. Откройте консоль приложение **Консоль**.
2. В разделе **ФАЙЛЫ** выберите **system.log**.
3. На панели меню вверху выберите **Файл** > **Сохранить копию как...** и сохраните файл.

### <a name="windows-phone"></a>Windows Phone

В приложении корпоративного портала для Windows Phone пользователи могут нажать кнопку с многоточием **...** для доступа к меню, а затем **Отправить журналы**. Это можно сделать как до, так и после входа в приложение корпоративного портала.

### <a name="windows"></a>Windows

Файлы журнала корпоративного портала Windows расположены в каталоге *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO2-->


