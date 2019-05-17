---
title: Операционные системы и браузеры, поддерживаемые Microsoft Intune
titleSuffix: ''
description: Список поддерживаемых браузеров и платформ устройств для управления устройствами в Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/03/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc0cf701450e594fd4b72a8e0565246994bb8a9e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460620"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Поддерживаемые в Intune операционные системы и браузеры

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Перед настройкой Microsoft Intune просмотрите список поддерживаемых операционных систем и браузеров.

Сведения об установке Intune на устройстве см. в статьях [Использование управляемых устройств для выполнения задач](/intune-user-help/company-portal-frequently-asked-questions) и [Использование пропускной способности сети Intune](network-bandwidth-use.md).

Дополнительные сведения о поддержке поставщиков служб конфигурации см. в справочнике о [поставщиках служб конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="intune-supported-operating-systems"></a>Операционные системы, поддерживаемые Intune

Вы можете управлять устройствами с указанными ниже операционными системами.

[!INCLUDE [mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Поддерживаемые устройства Samsung Knox Standard

Чтобы избежать ошибок активации Knox, которые препятствуют регистрации в MDM, приложение "Корпоративный портал" пытается выполнить активацию устройства Samsung Knox во время регистрации в MDM, только если это устройство включено в [список поддерживаемых устройств Knox](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Устройства, которые не поддерживают активацию Samsung Knox, регистрируются как стандартные устройства Android. Некоторые модели устройств Samsung поддерживают Knox, а другие нет. Перед приобретением и развертыванием устройств Samsung следует уточнить их совместимость с Knox у торгового посредника.

> [!NOTE]
> Для регистрации устройств Samsung Knox может потребоваться [предоставить доступ к серверам Samsung](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers). 

Следующие модели устройств Samsung не поддерживают Knox. Они регистрируются как обычные устройства Android в приложении "Корпоративный портал" для Android:

| **Имя устройства** | **Номера моделей устройства** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2 или Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7 или Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot; или Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="windows-pc-software-client"></a>Программный клиент для компьютера Windows

[Программный клиент Intune](manage-windows-pcs-with-microsoft-intune.md) можно развернуть и установить на компьютере под управлением Windows в качестве альтернативного метода регистрации. Эта функция доступна только на классическом портале Intune. Программный клиент Intune можно использовать для управления компьютерами на базе Windows 7 и более поздних версий, кроме выпуска Windows 10 Домашняя.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Поддерживаемые Intune веб-браузеры

Разные задачи администрирования требуют использование следующих веб-сайтов администрирования.

- [Центр администрирования Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Портал Azure](https://portal.azure.com/)

Для этих порталов поддерживаются следующие браузеры:
- Microsoft Edge (последняя версия);
- Microsoft Internet Explorer 11;
- Safari (последняя версия, только для Mac);
- Chrome (последняя версия);
- Firefox (последняя версия).




### <a name="intune-classic-portal"></a>Классический портал Intune

Классические функции Intune, такие как программный клиент Intune для ПК и интеграция с партнерами Mobile Threat Defense, доступны только на классическом портале Intune (https://manage.microsoft.com)). Для работы с классическим порталом Intune требуется браузер, поддерживающий Silverlight.

Для работы с консолью Intune можно использовать следующие браузеры с поддержкой Silverlight:
- Internet Explorer 10 или более поздней версии
- Google Chrome (до версии 42)
- Mozilla Firefox с поддержкой Silverlight [Дополнительные сведения](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge и браузеры мобильных устройств не поддерживаются для классического портала Intune, так как они не поддерживают [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Входить на портал могут только пользователи, имеющие разрешения администратора службы или являющиеся администраторами клиента с ролью глобального администратора. Чтобы получить доступ к консоли администрирования, учетной записи должна быть назначена лицензия на использование Intune и состояние входа должно быть **Разрешено**.
