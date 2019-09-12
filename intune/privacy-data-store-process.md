---
title: Хранение и обработка данных в Intune
description: Сведения о хранении и обработке персональных данных в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2947969c1c07d595a0a5baa48be11ba7a941424
ms.sourcegitcommit: e477e399cba673a2a9e1fa342e8303ed993801eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739223"
---
# <a name="data-storage-and-processing-in-intune"></a>Хранение и обработка данных в Intune

После [сбора данных](privacy-data-collect.md) службой Intune они сохраняются и обрабатываются описанным ниже образом.

## <a name="storing-personal-data"></a>Хранение персональных данных

Все собранные данные, не относящиеся к телеметрии, обрабатываются службой Intune и сохраняются в одном или нескольких следующих местах хранения: 

- SQLAzure 
- Надежные коллекций (Service Fabric)  
- Хранилище Azure 

Данные телеметрии (журналы служб, журналы производительности, ошибки и т. д.), наиболее важные для мониторинга и стабильный работы службы, отправляются в хранилища данных телеметрии Майкрософт.

### <a name="storage-locations"></a>Места хранения

Корпорация Майкрософт предоставляет и поддерживает службы Intune во многих регионах по всему миру. Intune соблюдает решения о местах хранения, сделанные администратором данных клиента.

Дополнительные сведения см. на странице со сведениями о [расположении данных](https://www.microsoft.com/trust-center/privacy/data-location).

### <a name="personal-data-retention"></a>Хранение персональных данных

В общем случае персональные данные хранятся службой Intune в течение 30 дней после удаления пользователя из системы управления Intune.

Данные телеметрии, собранные в рамках использования Intune, хранятся не более 30 дней.

Журналы аудита хранятся до одного года.

## <a name="processing-personal-data"></a>Обработка персональных данных

Intune обрабатывает персональные данные с использованием систем, сертифицированных по стандарту ISO. Дополнительные сведения см. в разделе [Service Trust Portal](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Профилирование и маркетинг

Microsoft Intune не использует персональные данные, собранные в рамках предоставления службы, для профилирования или в коммерческих целях. 

### <a name="restrict-processing-of-personal-data"></a>Ограничение обработки персональных данных

Чтобы ограничить обработку персональных данных пользователя, можно удалить его учетную запись следующим образом:
1. Экспорт электронной копии персональных данных пользователя, включая:
    - учетные записи
    - данные службы;
    - связанные журналы.
2. Удаление учетной записи пользователя и связанных с ней данных из Intune.

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения о том, как Intune [обеспечивает защиту и совместное использование](privacy-data-secure-share.md) персональных данных. 
