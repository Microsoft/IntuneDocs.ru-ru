---
title: "Сбор журналов устройств | Microsoft Intune"
description: "Узнайте, как собирать журналы с управляемых устройств."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3a081109cd499d3bdda75cb6c8a4dab9d9d28fab
ms.openlocfilehash: ec7d522e8dcff66d1b84fed3c4c0cc708e555e67


---

# <a name="device-logs"></a>Журналы устройств

При устранении неполадок вам могут потребоваться журналы с устройств пользователя. Ниже описаны инструкции для сбора этих журналов. Для сбора обычно необходим доступ к устройству или запрос от пользователя на сбор журналов и их отправку вам.

### <a name="android-log-location"></a>Расположение журналов в Android
Журналы в Android расположены в каталоге *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Пользователь также может отправить файлы журналов по электронной почте, как описано в статье [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### <a name="ios-logs"></a>Журналы iOS

Пользователь может отправить вам ошибки регистрации, как описано в разделе [Отправка ошибок регистрации iOS ИТ-администратору](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-devices"></a>Устройства Mac OS X

1. Откройте консоль приложение **Консоль**.
2. В разделе **ФАЙЛЫ** выберите **system.log**.
3. На панели меню вверху выберите **Файл** > **Сохранить копию как...** и сохраните файл.

### <a name="windows-phone"></a>Windows Phone

На **корпоративном портале Windows Phone** пользователь должен выбрать **...** для доступа к меню, а затем **Отправить журналы**. Этот параметр доступен как до, так и после входа на портал.

### <a name="windows"></a>Windows

Для корпоративного портала Windows файлы журнала расположены в каталоге *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Oct16_HO3-->


