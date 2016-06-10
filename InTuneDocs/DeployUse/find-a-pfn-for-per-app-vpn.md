---
# required metadata

title: Поиск имени семейства пакетов (PFN) для VPN для каждого приложения | Microsoft Intune|
description:
keywords:
author: nbigman
manager: [ALIAS]
ms.date: 05/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Поиск имени семейства пакетов (PFN) для VPN для каждого приложения

Найти имя семейства пакетов для настройки VPN для каждого приложения можно двумя способами.

## Поиск имени семейства пакетов для приложения, установленного на компьютере Windows 10 

Если приложение, с которым вы работаете, уже установлено на компьютере Windows 10, для получения PFN можно использовать командлет [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Синтаксис командлета Get-AppxPackage таков:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Примечание: для получения PFN может потребоваться запустить PowerShell с правами администратора.

Например, для получения сведений обо всех универсальных приложениях, установленных на компьютере, используйте `Get-AppxPackage`.

Чтобы получить сведения о приложении по имени или части имени приложения, используйте `Get-AppxPackage *<app_name>`. Обратите внимание на использование подстановочного знака, если вы не знаете полного имени приложения. Например, чтобы получить сведения об OneNote, используйте `Get-AppxPackage *OneNote`.


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



## Поиск имени семейства пакетов в том случае, если приложение не установлено на компьютере

1.  Перейдите на страницу https://www.microsoft.com/en-us/store/apps
2.  Введите имя приложения в строке поиска. В нашем примере это "OneNote".
3.  Щелкните ссылку на приложение. Обратите внимание, что URL-адрес, по которому вы обращаетесь, содержит последовательность букв в конце. В нашем примере URL-адрес выглядит следующим образом:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  В другой вкладке вставьте следующий URL-адрес, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`, заменив `<app id>` идентификатором приложения, полученным на странице https://www.microsoft.com/en-us/store/apps — это ряд букв в конце URL-адреса на шаге 3. В нашем примере с OneNote нужно вставить следующее: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

В Edge нужные вам сведения уже отображаются; в Internet Explorer щелкните **Открыть**, чтобы просмотреть сведения. Значение PFN указано в первой строке. Ниже приведены результаты для нашего примера:
 

`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=May16_HO3-->


