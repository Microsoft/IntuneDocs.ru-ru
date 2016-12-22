---
title: "Поддерживаемые мобильные устройства и браузеры | Microsoft Intune"
description: "Выводится список поддерживаемых устройств и браузеров, позволяющих использовать Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/01/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: b0eab195c00aae4b593fff535179a1b993c36dde


---

# <a name="supported-devices-and-web-browsers-for-intune"></a>Поддерживаемые мобильные устройства и веб-браузеры для Intune

Как администратор Intune вы можете управлять различными устройствами из веб-браузера. Этот раздел содержит следующее:

- [Списки поддерживаемых платформ устройств](#intune-supported-devices)
- [Список поддерживаемых браузеров, позволяющих использовать Intune](#intune-supported-web-browsers)

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

>[&larr; **Необходимые условия**](what-to-know-before-you-start-microsoft-intune.md)     [**Сетевое взаимодействие** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Dec16_HO2-->


