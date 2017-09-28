---
title: "Устройства, поддерживаемые Microsoft Intune"
description: "Список поддерживаемых браузеров и платформ устройств для управления устройствами в Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4cfdf6a8aab1bda15015f85b1fb8f364e6a0edfa
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2017
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
