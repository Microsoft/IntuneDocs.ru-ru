---
title: "Настройка параметров Windows Information Protection в Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune в Azure. Сведения о параметрах Intune, с помощью которых можно управлять функцией Windows Information Protection."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc58b07fe33ff6223dfa182fb4f81f15379295fa
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Настройка Windows Information Protection в Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

С увеличением числа устройств сотрудников в организации растет риск случайной утечки корпоративных данных через приложения и службы, такие как электронная почта, социальные сети и общедоступные облака, которые находятся вне контроля организации. Например, когда сотрудники отправляют последние рабочие чертежи из личной учетной записи электронной почты, добавляют данные о продуктах в твиты или сохраняют промежуточные отчеты о продажах в общедоступное облачное хранилище.

**Windows Information Protection** позволяет предотвратить возможную утечку данных, не влияя при этом на работу сотрудника. Кроме того, эта политика обеспечивает защиту приложений и данных на устройствах, принадлежащих организации, и личных устройствах сотрудников от случайной утечки данных. При этом нет необходимости вносить какие-либо изменения в вашу среду или другие приложения.

Политика Intune управляет списком приложений, защищенных Windows Information Protection, расположениями в сети организации, уровнем защиты и настройками шифрования.

>[!NOTE]
> Чтобы использовать приложение корпоративного портала Windows 10 с Windows Information Protection, необходимо добавить приложение корпоративного портала в режиме **исключения** Windows Information Protection. 

### <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения см. в статье [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Защита корпоративных данных с помощью Windows Information Protection).

