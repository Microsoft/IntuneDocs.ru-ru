---
title: "Поиск имени семейства пакетов для VPN для каждого приложения"
description: "Сведения о поиске имени семейства пакетов для настройки VPN для каждого приложения."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: eea3b9e2888f07399c8cda1e81ae8a5318d02d42
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Поиск имени семейства пакетов (PFN) для конфигурации VPN для каждого конкретного приложения

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Найти имя семейства пакетов для настройки VPN для каждого приложения можно двумя способами.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Поиск имени семейства пакетов для приложения, установленного на компьютере Windows 10

Если приложение, с которым вы работаете, уже установлено на компьютере Windows 10, для получения имени семейства пакетов можно использовать командлет [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Синтаксис командлета Get-AppxPackage таков:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Для получения имени PFN может потребоваться запустить PowerShell с правами администратора.

Например, для получения сведений обо всех универсальных приложениях, установленных на компьютере, используйте `Get-AppxPackage`.

Чтобы получить сведения о приложении по имени или части имени приложения, используйте `Get-AppxPackage *<app_name>`. Обратите внимание на использование подстановочного знака: он особенно удобен, если вам неизвестно полное имя приложения. Например, чтобы получить сведения об OneNote, используйте `Get-AppxPackage *OneNote`.


Ниже приведена полученная информация об OneNote:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Поиск имени семейства пакетов в том случае, если приложение не установлено на компьютере

1.  Перейдите на страницу https://www.microsoft.com/store/apps.
2.  Введите имя приложения в строке поиска. В нашем примере это "OneNote".
3.  Щелкните ссылку на приложение. Обратите внимание, что URL-адрес, по которому вы переходите, содержит последовательность букв в конце. В нашем примере URL-адрес выглядит следующим образом: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.  Вставьте следующий URL-адрес в адресную строку другой вкладки: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Замените `<app id>` идентификатором приложения, полученным на странице https://www.microsoft.com/store/apps (это ряд букв в конце URL-адреса на этапе 3). В нашем примере с OneNote нужно вставить следующее: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

В Microsoft Edge отображаются нужные вам сведения; в Internet Explorer щелкните **Открыть**, чтобы просмотреть сведения. Значение PFN указано в первой строке. Ниже приведены результаты для нашего примера:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
