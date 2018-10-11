---
title: Безопасность и передача данных в Intune
description: Сведения о защите и совместном использовании персональных данных в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5613c1284110e85a910db8f156ff4f62a54af4ad
ms.sourcegitcommit: dc6979f2b14d522530577cc7f212cc822356acc9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47453550"
---
# <a name="data-security-and-sharing-in-intune"></a>Безопасность и передача данных в Intune


## <a name="data-security"></a>Безопасность данных

Microsoft Intune — это ключевой компонент облачного предложения Microsoft Enterprise Mobility + Security. Для поддержки [стратегии управления данными](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) все облачные службы Майкрософт разрабатываются с соблюдением принципов [конфиденциальности](https://www.microsoft.com/en-us/trustcenter/privacy) и [безопасности](https://www.microsoft.com/en-us/trustcenter/security/) корпорации Майкрософт.  

В Microsoft Intune принимаются те же технические и организационные меры, которые команда разработчиков службы Microsoft Azure использует для защиты от нарушения безопасности данных.

Дополнительные сведения см. в разделе [Service Trust Portal](https://www.microsoft.com/en-us/TrustCenter/stp).

Intune использует методы минимизации данных, такие как

- aggregation
- необязательный сбор данных для некоторых компонентов;
- снижение точности или уровня конфиденциальности данных.

Intune также использует такие методы, как системы безопасности RBAC и JIT, для инцидентов поддержки, чтобы обеспечить защиту данных по умолчанию. 

### <a name="data-breach-reporting"></a>Отчеты о нарушении безопасности данных

При выявлении регистрируемого клиентом инцидента безопасности (CRSI) клиенты уведомляются об этом. Данный процесс включает в себя обращение к команде разработчиков Microsoft Office 365 для сообщения о нарушении всем клиентам Microsoft Office 365 через Intune.

## <a name="data-sharing"></a>Общий доступ к данным

Когда администраторы клиента включают определенные функции (например, Программу регистрации устройств Apple), Microsoft Intune получает согласие администратора на обмен данными с соответствующими третьими лицами. В таких случаях Intune может предоставлять персональные данные:

- третьим лицам, выступающим в качестве агентов корпорации Майкрософт;
- третьим лицам, не выступающим в качестве агентов корпорации Майкрософт, но только если администраторы клиента дают на это явное разрешение в Intune.

Все третьи лица, выступающие в роли агентов Майкрософт, включаются в [список субподрядчиков веб-служб](https://aka.ms/Online_Serv_Subcontractor_List).

Обмен данными с этими лицами осуществляется для упрощения поддержки клиентов и технической поддержки, обслуживания и других операций.

Контракт клиента с третьим лицом регулирует, какие именно персональные данные Intune хранятся в соответствующей сторонней службе. Он также предоставляет Intune разрешение на передачу данных в стороннюю службу.  

Сведения о данных, передаваемых третьим сторонам, см. в следующих статьях:
- [Данные, отправляемые Intune в Apple](data-intune-sends-to-apple.md)
- [Данные, отправляемые Intune в Google](data-intune-sends-to-google.md)
- [Данные, которые Apple отправляет в Intune](data-apple-sends-to-intune.md)
- [Данные, которые Google отправляет в Intune](data-google-sends-to-intune.md)
- [Сведения, передаваемые с Jamf Pro в Intune](conditional-access-integrate-jamf.md#information-shared-from-jamf-pro-to-intune)

### <a name="system-center-configuration-manager-data-sharing"></a>Общий доступ к данным System Center Configuration Manager

Служба Microsoft Intune не обменивается никакими данными с System Center Configuration Manager. System Center Configuration Manager — это локальный продукт, развертывание, управление и обслуживание которого осуществляет непосредственно клиент. Данные о диагностике и использовании, собираемые Configuration Manager, применяются лишь для улучшения процедуры установки, качества и безопасности будущих выпусков.

Дополнительные сведения см. в разделе [Данные о диагностике и использовании для SCCM](https://docs.microsoft.com/en-us/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data.md). 


## <a name="next-steps"></a>Дальнейшие шаги

Сведения о [просмотре и изменении](privacy-data-view-correct.md) персональных данных в Intune.
