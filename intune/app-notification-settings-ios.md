---
title: Создание уведомлений от приложений для устройств iOS — Microsoft Intune — Azure | Документы Майкрософт
description: Добавление или создание уведомлений от приложений для устройств iOS в Microsoft Intune. Выберите, какие приложения будут отправлять уведомления, настройте параметры уведомлений на экране блокировки, включите звук, выберите тип оповещения и добавьте индикатор событий.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2bf4919fecbba8ad4c0f3b8535adf8b97a35342e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182199"
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>Настройка параметров уведомлений от приложений для устройств iOS в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настройте отправку уведомлений от приложений, установленных на устройстве iOS. Эти параметры поддерживают защищенные устройства под управлением iOS 9.3 и более поздней версии.

## <a name="add-the-app-notification"></a>Включение уведомлений от приложений

1. Войдите на [портал Azure](https://portal.azure.com).
2. В профиле iOS или macOS выберите **Функции устройства**. В разделе [Функции устройства iOS или macOS](device-features-configure.md) приводятся инструкции по созданию профиля.
3. Выберите **Уведомления от приложений (только в защищенном режиме)**, а затем нажмите **Добавить**: ![Добавить уведомление от приложения в профиль iOS или macOS в Intune](./media/ios-macos-app-notifications.png)
4. Укажите следующие свойства.

   - **ИД пакета приложений**. Введите **идентификатор пакета приложений** того приложения, которое требуется настроить. Дополнительные сведения см. в **справочнике по идентификаторам пакетов для встроенных приложений iOS** в этой статье.
   - **Имя приложения**. Введите имя приложения, которое необходимо настроить. Это имя не отображается на устройстве и предназначено для определения приложения в списке.
   - **Издатель**. Введите издателя приложения, которое требуется настроить. Имя издателя не отображается на устройстве и предназначено для определения приложения в списке.
   - **Уведомления**. Включите или отключите для приложения параметр отправки уведомлений на устройство. Если вы отключите этот параметр, приведенные ниже параметры также будут отключены.
     - **Показать в центре уведомлений**. Включите этот параметр, чтобы разрешить приложению показывать уведомления в центре уведомлений для устройства.
     - **Показать на экране блокировки**. Включите этот параметр, чтобы уведомления приложения отображались на экране блокировки устройства.
     - **Тип оповещения**. Из списка ниже выберите необходимый тип оповещения, когда устройство разблокировано.
       - **Отсутствует**. Уведомление не отображается.
       - **Баннер**. Отобразится баннер с уведомлением.
       - **Модальный**. Когда отобразится уведомление, пользователю необходимо будет вручную отменить его, чтобы продолжить использование устройства.
     - **Эмблема на значке приложения**. Включите этот параметр, чтобы добавить эмблему на значок приложения для указания, что приложение отправило уведомление.
     - **Звуки**. Включите этот параметр для воспроизведения звука при доставке уведомления.

5. Добавьте необходимое количество приложений. Добавив приложение, нажмите **ОК**.
6. Выберите **Создать**, чтобы сохранить профиль.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Справочник по идентификаторам наборов для встроенных приложений iOS

Этот список содержит идентификаторы пакетов некоторых стандартных встроенных приложений iOS. Чтобы найти идентификаторы пакетов других приложений, обратитесь к поставщику программного обеспечения.

|||
|-|-|
|Имя приложения|BundleID|
|Магазин App Store|com.apple.AppStore|
|"Калькулятор"|com.apple.calculator|
|"Календарь"|com.apple.mobilecal|
|Камера|com.apple.camera|
|"Часы"|com.apple.mobiletimer|
|"Компас"|com.apple.compass|
|"Контакты"|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|"Найти друзей"|com.apple.mobileme.fmf1|
|"Найти iPhone"|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|"Здоровье"|com.apple.Health|
|iBooks|com.apple.iBooks|
|Магазин iTunes|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|"Карты"|com.apple.Maps|
|"Сообщения"|com.apple.MobileSMS|
|"Музыка"|com.apple.Music|
|News|com.apple.news|
|"Заметки"|com.apple.mobilenotes|
|Numbers|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|"Фото"|com.apple.mobileslideshow|
|"Подкасты"|com.apple.podcasts|
|"Напоминания"|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|"Настройки"|com.apple.Preferences|
|"Акции"|com.apple.stocks|
|"Советы"|com.apple.tips|
|"Видео"|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|"Погода"|com.apple.weather|

## <a name="next-steps"></a>Дальнейшие шаги

Назначьте профиль устройства выбранным группам. Инструкции приводятся в разделе [Назначение профилей устройств](device-profile-assign.md).