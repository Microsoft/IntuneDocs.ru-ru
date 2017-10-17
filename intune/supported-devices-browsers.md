---
title: "Устройства, поддерживаемые Microsoft Intune"
description: "Список поддерживаемых браузеров и платформ устройств для управления устройствами в Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6c9cc3a6a84c48da36b0219743012a15b72e6810
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2017
---
# <a name="supported-devices-and-browsers"></a>Поддерживаемые устройства и браузеры

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Эта статья предназначена для системных администраторов, которые отвечают за управление устройствами на предприятии. Сведения об установке Intune на телефоне см. в статье [Использование управляемых устройств для выполнения задач](/intune-user-help/company-portal-frequently-asked-questions).

Перед настройкой Microsoft Intune изучите следующие материалы:

- [Поддерживаемые мобильные устройства и компьютеры](#intune-supported-devices)
- [Список поддерживаемых браузеров, позволяющих использовать Intune](#intune-supported-web-browsers)

Следует также ознакомиться со статьей [Использование пропускной способности сети Intune](network-bandwidth-use.md) ([классический портал](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Устройства, поддерживаемые Intune

Вы можете управлять следующими устройствами с помощью функций управления мобильными устройствами Intune:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Поддерживаемые устройства Samsung KNOX Standard

Приложение "Корпоративный портал" пытается выполнить активацию устройства Samsung KNOX во время регистрации в MDM, только если это устройство включено в [список поддерживаемых устройств KNOX](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Это позволяет избежать ошибок активации KNOX, делающих регистрацию в MDM невозможной. Устройства, которые не поддерживают активацию Samsung KNOX, регистрируются как стандартные устройства Android. Некоторые модели устройств Samsung поддерживают KNOX, а другие нет. Перед приобретением и развертыванием устройств Samsung следует уточнить их совместимость с решением KNOX у торгового посредника.

Ниже приведен список моделей устройств Samsung, которые не поддерживают KNOX и регистрируются приложением "Корпоративный портал" для Android как обычные устройства Android:

| **Имя устройства** | **Модель устройства** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9 или C9 Pro | SM-C900F |
| Galaxy Core 2 или Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7 или Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot; или Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Intune нельзя использовать для управления операционными системами Windows Server.

### <a name="windows-pc-software-client"></a>Программный клиент для компьютера Windows

[Программный клиент Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) можно развернуть и установить на компьютере под управлением Windows в качестве альтернативного метода регистрации. Эта функция доступна только на классическом портале Intune. Программный клиент Intune можно использовать для управления компьютерами на базе Windows 7 и более поздних версий, кроме выпуска Windows 10 Домашняя.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Поддерживаемые Intune веб-браузеры

Разные задачи администрирования требуют использование следующих веб-сайтов администрирования.

- [Портал Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Портал Azure](https://portal.azure.com/)

Для этих порталов поддерживаются следующие браузеры:
- Microsoft Edge (последняя версия);
- Microsoft Internet Explorer 11;
- Safari (последняя версия, только для Mac);
- Chrome (последняя версия);
- Firefox (последняя версия).

### <a name="intune-classic-portal"></a>Классический портал Intune

Классические функции Intune, такие как программный клиент Intune для ПК и интеграция с партнерами Mobile Threat Defense, доступны только на классическом портале Intune (https://manage.microsoft.com). Для работы с классическим порталом Intune требуется браузер, поддерживающий Silverlight.

Для работы с консолью Intune можно использовать следующие браузеры с поддержкой Silverlight:
- Internet Explorer 10 или более поздней версии
- Google Chrome (до версии 42)
- Mozilla Firefox с поддержкой Silverlight [Дополнительные сведения](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge и браузеры мобильных устройств не поддерживаются для классического портала Intune, так как они не поддерживают [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Входить на портал могут только пользователи, имеющие разрешения администратора службы или являющиеся администраторами клиента с ролью глобального администратора. Чтобы получить доступ к консоли администрирования, учетной записи должна быть назначена лицензия на использование Intune и состояние входа должно быть **Разрешено**.
