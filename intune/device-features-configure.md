---
title: Создание профилей устройств iOS или macOS в Microsoft Intune — Azure | Документация Майкрософт
description: Добавьте или создайте профиль устройства iOS или macOS и настройте параметры для AirPrint, AirPlay, макета начального экрана, уведомлений приложения, общего устройства, единого входа и фильтрации веб-содержимого в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2282ba4dd3caf8c71c8624884bc124393ea52d2f
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203099"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Добавление параметров для функций устройств iOS или macOS в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Функции устройств позволяют управлять различными параметрами и возможностями на устройствах iOS и macOS, такими как:

- параметры AirPrint и AirPlay;
- макет начального экрана;
- уведомления из приложений;
- Сообщение на экране блокировки
- настройка единого входа;
- фильтрация веб-содержимого.

Эта статья содержит основные сведения о настройке профилей для функций устройств iOS. Ознакомившись с этим руководством, вы можете выполнить инструкции в дополнительных статьях и настроить параметры платформы для устройств.

## <a name="create-a-device-profile"></a>Создание профиля устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
4. Укажите следующие свойства.

   - **Имя**. Введите описательное имя для нового профиля.
   - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
   - **Платформа**. Выберите тип платформы:
     - **iOS**
     - **macOS**
   - **Тип профиля**. Выберите **Возможности устройств**.
   - **Параметры**: Параметры зависят от выбранной платформы. Параметры каждого типа профиля описаны в следующих статьях:

     - [Параметры AirPrint для iOS и MacOS](air-print-settings-ios-macos.md)
     - [Параметры AirPlay для iOS](airplay-settings-ios.md)
     - [Параметры макета начального экрана для iOS](home-screen-settings-ios.md)
     - [Параметры уведомлений приложения для iOS](app-notification-settings-ios.md)
     - [Сообщение на экране блокировки для iOS](shared-device-settings-ios.md)
     - [Настройка единого входа на устройствах с iOS для Intune](sso-ios.md)
     - [Параметры фильтра веб-содержимого для iOS](web-content-filter-settings-ios.md)

5. По завершении нажмите кнопку **ОК** и выберите **Создать**, чтобы сохранить изменения.

Созданный профиль отобразится в списке.

## <a name="next-step"></a>Дальнейшие действия

Сведения о том, как назначить этот профиль группам, см. в статье [Назначение профилей устройств](device-profile-assign.md).