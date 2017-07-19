---
title: "Параметры уведомлений приложений Intune для устройств iOS"
titleSuffix: Intune on Azure
description: "Сведения о параметрах, которые вы можете использовать, чтобы управлять уведомлениями приложений для устройств iOS.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36a9e9a5be9b2dc45ded1a99c7a5871780f7d9b2
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2017
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>Параметры уведомлений приложений Intune для устройств iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Вы можете настроить параметры отправки уведомлений в приложениях на устройстве. Эти параметры поддерживают защищенные устройства под управлением iOS 9.3 и более поздней версии.

## <a name="configure-settings"></a>Настройка параметров

1. В колонке "Функции устройства" выберите **Уведомления приложений (только в защищенном режиме)**.
2. В колонке **Уведомления приложений** выберите **Добавить**, а затем задайте приведенные ниже значения.
    - **ИД пакета приложений**. Введите **идентификатор набора приложений** того приложения, которое требуется настроить. См. **справочник по идентификаторам наборов для встроенных приложений iOS** в этой статье.
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
3. Добавьте необходимое количество приложений. После этого нажмите кнопку **ОК**.
4. Нажимайте кнопку **ОК**, пока не вернетесь к колонке **Создание профиля**, а затем выберите **Создать**. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Справочник по идентификаторам наборов для встроенных приложений iOS

Этот список содержит идентификаторы наборов некоторых стандартных встроенных приложений iOS. Чтобы найти идентификаторы наборов других приложений, обратитесь к поставщику программного обеспечения. 

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

## <a name="next-steps"></a>Дальнейшие действия

Теперь профиль устройства можно назначить определенным группам. Дополнительные сведения см. в статье [Назначение профилей устройств](device-profile-assign.md).
