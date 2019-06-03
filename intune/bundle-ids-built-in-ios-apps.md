---
title: Идентификаторы пакета iOS для встроенных приложений в Microsoft Intune — Azure | Документация Майкрософт
titleSuffix: ''
description: Ознакомьтесь со списком идентификаторов пакетов для встроенных приложений iOS. Используйте эти идентификаторы пакетов, чтобы явно разрешить приложения в профилях и политиках конфигурации устройств в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26f43523589da0d59afb3b667eb4ead8357f7a60
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66049029"
---
# <a name="bundle-ids-for-built-in-ios-apps-you-can-use-in-intune"></a>Идентификаторы пакетов для встроенных приложений iOS, которые можно использовать в Intune

При настройке возможностей на устройствах iOS можно также добавить встроенные приложения на устройствах iOS. В этой статье перечислены идентификаторы пакета некоторых стандартных встроенных приложений iOS. Чтобы найти идентификаторы наборов других приложений, обратитесь к поставщику программного обеспечения.

## <a name="bundle-ids"></a>Идентификаторы пакета

| Идентификатор пакета                   | имя приложения;     | Издатель |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Магазин App Store    | Apple     |
| com.apple.calculator        | "Калькулятор"   | Apple     |
| com.apple.mobilecal         | "Календарь"     | Apple     |
| com.apple.camera            | Камера       | Apple     |
| com.apple.mobiletimer       | "Часы"        | Apple     |
| com.apple.compass           | "Компас"      | Apple     |
| com.apple.MobileAddressBook | "Контакты"     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Файлы        | Apple     |
| com.apple.mobileme.fmf1     | "Найти друзей" | Apple     |
| com.apple.mobileme.fmip1    | "Найти iPhone"  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | "Здоровье"       | Apple     |
| com.apple.Home              | Корневая         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | Магазин iTunes | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | "Карты"         | Apple     |
| com.apple.MobileSMS         | "Сообщения"     | Apple     |
| com.apple.Music             | "Музыка"        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | "Заметки"        | Apple     |
| com.apple.Numbers           | Numbers      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Фотографии       | Apple     |
| com.apple.podcasts          | "Подкасты"     | Apple     |
| com.apple.reminders         | "Напоминания"    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | "Настройки"     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | "Акции"       | Apple     |
| com.apple.tips              | "Советы"         | Apple     |
| com.apple.tv                | TV           | Apple     |
| com.apple.videos            | Видео       | Apple     |
| com.apple.VoiceMemos        | VoiceMemos   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | "Погода"      | Apple     |

## <a name="next-steps"></a>Дальнейшие шаги

Используйте эти идентификаторы пакета, чтобы настроить [функции устройства](ios-device-features-settings.md), а также чтобы [разрешить или ограничить некоторые параметры](device-restrictions-ios.md) на устройствах iOS.
