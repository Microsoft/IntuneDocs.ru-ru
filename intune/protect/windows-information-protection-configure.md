---
title: Параметры Windows Information Protection в Microsoft Intune
titleSuffix: Microsoft Intune
description: Сведения о параметрах Microsoft Intune, с помощью которых можно управлять функцией Windows Information Protection.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f4c8f30359869761482e55680c9d935722bdf67
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508743"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Настройка Windows Information Protection в Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

С увеличением числа устройств сотрудников в организации растет риск случайной утечки корпоративных данных через приложения и службы, такие как электронная почта, социальные сети и общедоступные облака, которые находятся вне контроля организации. Например, когда сотрудники отправляют последние рабочие чертежи из личной учетной записи электронной почты, добавляют данные о продуктах в твиты или сохраняют промежуточные отчеты о продажах в общедоступное облачное хранилище.

**Windows Information Protection** позволяет предотвратить возможную утечку данных, не влияя при этом на работу сотрудника. Кроме того, эта политика обеспечивает защиту приложений и данных на устройствах, принадлежащих организации, и личных устройствах сотрудников от случайной утечки данных. При этом нет необходимости вносить какие-либо изменения в вашу среду или другие приложения.

Политика Intune управляет списком приложений, защищенных Windows Information Protection, расположениями в сети организации, уровнем защиты и настройками шифрования.

>[!NOTE]
> Чтобы использовать приложение корпоративного портала Windows 10 с Windows Information Protection, необходимо добавить приложение корпоративного портала в режиме **исключения** Windows Information Protection. 

Дополнительные сведения см. на странице
- [Защита корпоративных данных с помощью Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)
- [Создание политики Windows Information Protection (WIP) с помощью Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Создание политики Windows Information Protection (WIP) с MDM с помощью портала Azure для Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Создание политики Windows Information Protection (WIP) с MAM с помощью портала Azure для Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
