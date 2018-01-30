---
title: "Настройка параметров Windows Information Protection в Intune"
titleSuffix: Azure portal
description: "Сведения о параметрах Intune, с помощью которых можно управлять функцией Windows Information Protection.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e33fa9b22687f7f8c4d301c6cd82ecd787c23246
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Настройка Windows Information Protection в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

С увеличением числа устройств сотрудников в организации растет риск случайной утечки корпоративных данных через приложения и службы, такие как электронная почта, социальные сети и общедоступные облака, которые находятся вне контроля организации. Например, когда сотрудники отправляют последние рабочие чертежи из личной учетной записи электронной почты, добавляют данные о продуктах в твиты или сохраняют промежуточные отчеты о продажах в общедоступное облачное хранилище.

**Windows Information Protection** позволяет предотвратить возможную утечку данных, не влияя при этом на работу сотрудника. Кроме того, эта политика обеспечивает защиту приложений и данных на устройствах, принадлежащих организации, и личных устройствах сотрудников от случайной утечки данных. При этом нет необходимости вносить какие-либо изменения в вашу среду или другие приложения.

Политика Intune управляет списком приложений, защищенных Windows Information Protection, расположениями в сети организации, уровнем защиты и настройками шифрования.

>[!NOTE]
> Чтобы использовать приложение корпоративного портала Windows 10 с Windows Information Protection, необходимо добавить приложение корпоративного портала в режиме **исключения** Windows Information Protection. 

### <a name="next-steps"></a>Дальнейшие шаги
Дополнительные сведения см. на странице
-  [Защита корпоративных данных с помощью Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)
- [Создание политики Windows Information Protection (WIP) с помощью Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Создание политики Windows Information Protection (WIP) с MDM с помощью портала Azure для Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Создание политики Windows Information Protection (WIP) с MAM с помощью портала Azure для Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
