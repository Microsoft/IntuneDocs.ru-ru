---
title: Сбор журналов устройств
description: Узнайте, как собирать журналы с управляемых устройств.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f07947a4064cbd6852edb93ea8d6d17e2c6d9101
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025575"
---
# <a name="device-logs"></a>Журналы устройств

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

При устранении неполадок вам могут потребоваться журналы с устройств пользователя. Ниже описаны инструкции для сбора этих журналов. Для сбора обычно необходим доступ к устройству или одобрение от пользователя на сбор журналов и их отправку.

### <a name="android-logs"></a>Журналы Android
Журналы в Android расположены в каталоге *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Иногда файлы не отображаются, особенно на новых устройствах с Android. В этом случае конечным пользователям следует открыть приложение корпоративного портала для Android. Затем им нужно последовательно выбрать **Параметры**>**Копировать журналы** и перезагрузить устройство.

Дополнительные сведения о том, как пользователи могут отправлять вам журналы данных, см. в следующих статьях:

- [Использование подробного журнала для помощи ИТ-администратору в устранении неполадок на устройствах](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) описывает, как пользователи могут включить функцию ведения подробных журналов, которая автоматически отправляет вам все данные журналов. По умолчанию подробное ведение журнала включено.

- [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Отправка журналов диагностических данных ИТ-администратору по USB-кабелю](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Журналы iOS

Пользователь может отправить вам ошибки регистрации, как описано в разделе [Отправка ошибок регистрации iOS ИТ-администратору](/intune-user-help/send-errors-to-your-it-admin-ios).

Пользователи могут отправлять журналы устройств в соответствии с инструкциями в разделе [Отправка журналов устройств iOS](/intune-user-help/send-logs-to-microsoft-ios).

### <a name="mac-os-x-logs"></a>Журналы Mac OS X

1. Откройте консоль приложение **Консоль**.
2. В разделе **ФАЙЛЫ** выберите **system.log**.
3. В строке меню вверху выберите пункты **Файл** > **Сохранить копию как...**. Сохраните файл.

### <a name="windows-phone"></a>Windows Phone

В приложении корпоративного портала для Windows Phone пользователи могут нажать кнопку с многоточием (**...**) для доступа к меню, а затем выбрать команду **Отправить журналы**. Это можно сделать как до, так и после входа в приложение корпоративного портала.

### <a name="windows"></a>Windows

Файлы журнала корпоративного портала Windows расположены в каталоге *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
