---
title: "Устройства, поддерживаемые Microsoft Intune | Документация Майкрософт"
description: "Список поддерживаемых браузеров и платформ устройств для управления устройствами в Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 905be6a926dc5bab8e9b1016ba82751ee47313e5
ms.openlocfilehash: 61851f7669e9a5c3a192b2eda344fcde9c4fa3e6
ms.lasthandoff: 03/20/2017


---

# <a name="supported-devices-and-browsers"></a>Поддерживаемые устройства и браузеры

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Эта статья предназначена для системных администраторов, которые отвечают за управление устройствами на предприятии. Сведения об установке Intune на телефоне см. в статье [Использование управляемых устройств для выполнения задач](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Перед настройкой Microsoft Intune изучите следующие материалы:

- [Поддерживаемые мобильные устройства и компьютеры](#intune-supported-devices)
- [Список поддерживаемых браузеров, позволяющих использовать Intune](#intune-supported-web-browsers)

Следует также ознакомиться со статьей [Использование пропускной способности сети Intune](network-bandwidth-use.md).

## <a name="intune-supported-devices"></a>Устройства, поддерживаемые Intune

Вы можете управлять следующими устройствами с помощью функций управления мобильными устройствами Intune:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune нельзя использовать для управления операционными системами Windows Server.

Управление устройствами Intune предоставляет [эти возможности](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Программный клиент для компьютера Windows

[Программный клиент Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) можно развернуть и установить на компьютере под управлением Windows в качестве альтернативного метода регистрации. Программный клиент Intune можно использовать для управления компьютерами на базе Windows 7 и более поздних версий, кроме выпуска Windows 10 Домашняя. Управление компьютерами с помощью клиентского ПО предоставляет [следующие возможности](windows-pc-management-capabilities-in-microsoft-intune.md).

### <a name="exchange-activesync-management"></a>Управление с помощью Exchange ActiveSync

Вы можете управлять [устройствами Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) из консоли Intune. Этот вариант предоставляет ограниченный набор возможностей по сравнению с другими методами. Список поддерживаемых устройств см. в разделе [Возможности встроенного управления мобильными устройствами в Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0).

## <a name="intune-supported-web-browsers"></a>Поддерживаемые Intune веб-браузеры

Разные задачи администрирования требуют использование следующих веб-сайтов администрирования.

- [Портал Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Консоль администрирования Microsoft Intune](https://admin.manage.microsoft.com/)

|Функция Intune |Поддерживаемые браузеры|
|---------|---------|
|**Консоль администрирования Intune**     |  Internet Explorer 10 или более поздней версии<br /><br />Google Chrome (до версии 42)<br /><br />Mozilla Firefox с включенным Silverlight<br />**Примечание**. В марте 2017 г. поддержка Silverlight в Mozilla будет отменена. [Дополнительные сведения](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Портал администрирования Office 365**     |Все браузеры, включая браузеры мобильных устройств и управляемые браузеры  |
|**Веб-сайт корпоративного портала**     |**На мобильных устройствах:** используйте веб-браузер по умолчанию для каждой поддерживаемой платформы.   <br /><br />**На компьютерах под управлением Windows:** Internet Explorer 10 или более поздней версии или Microsoft Edge.<br /><br />**В Mac OS X 10.9 или более поздней версии:** Apple Safari.    |

> [!Note]
> Microsoft Edge и браузеры мобильных устройств не поддерживаются для консоли администратора, так как они не поддерживают [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Консоль Intune постепенно переводится с платформы Silverlight. В итоге все функции управления мобильными устройствами и приложениями Intune станут [доступны на новом портале Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Входить на портал могут только пользователи, имеющие разрешения администратора службы или являющиеся администраторами клиента с ролью глобального администратора. Чтобы получить доступ к консоли администрирования, учетной записи должна быть назначена лицензия на использование Intune и состояние входа должно быть **Разрешено**.

>[!div class="step-by-step"]

>[**Сеть** &rarr;](network-bandwidth-use.md)  

