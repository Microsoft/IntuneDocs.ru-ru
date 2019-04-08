---
title: Предотвращение утечки данных на неуправляемых устройствах
titleSuffix: Microsoft Intune
description: Разрешите доступ к корпоративным данным на устройствах, обеспечив защиту от утечки данных с помощью Microsoft Intune.
keywords: защита данных предотвращение утечек устройство Office 365
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 324187db4951ffb6b80e9cc488a2a0fb59f40a9a
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799378"
---
# <a name="prevent-data-leaks-on-non-managed-devices-using-microsoft-intune"></a>Предотвращение утечки данных на неуправляемых устройствах с помощью Microsoft Intune

Если вы разрешаете доступ к корпоративным данным, размещенным в Office 365, вы можете контролировать такие операции пользователей, как предоставление общего доступа и сохранение данных, без риска намеренной или случайной утечки данных. Microsoft Intune предоставляет политики защиты приложений, которые задаются для защиты корпоративных данных на устройствах сотрудников. Необязательно, чтобы устройства были зарегистрированы в службе Intune. 

Настройка политик защиты приложений с помощью Intune поддерживается для устройств, управляемых с помощью стороннего решения для управления устройствами. ИТ-отдел управляет только корпоративными данными, не затрагивая личные данные на устройстве. 

Можно задать политику защиты приложений для мобильных приложений Office на устройствах под управлением Windows, iOS или Android. Эти политики позволяют определять такие правила, как ПИН-код на основе приложений или шифрование корпоративных данных, а также более сложные параметры для ограничения использования таких операций, как вырезка, копирование, вставка и сохранение для управляемых и неуправляемых приложений. Вы также можете выполнить удаленную очистку корпоративных данных, не требуя от пользователей регистрации устройств. 

Политики защиты приложений Intune не зависят от среды управления устройствами. Политики защиты приложений позволяют управлять мобильными приложениями Office на устройствах, входящих и не входящих в область управления Intune, а также на устройствах под управлением сторонних MDM-решений. 

## <a name="before-you-begin"></a>Подготовка к работе

Если в среде выполнены перечисленные ниже требования, вы можете использовать следующий план действий.
* Компания готова к безопасному переходу в облако.
* Компания использует Office 365 Exchange Online, SharePoint Online, OneDrive для бизнеса или Yammer.
* Компания имеет лицензии Microsoft 365, Enterprise Mobility + Security (EMS) и Azure Information Protection.
* Компания дает пользователям возможность доступа к корпоративным данным с корпоративных или личных устройств Windows, iOS или Android. 
* Компания не намерена требовать регистрацию личных устройств в службе управления устройствами. 

## <a name="action-plan"></a>План действий

Для устройств iOS и Android 

1. Ознакомьтесь с принципами работы [политик защиты приложений](app-protection-policy.md).
2. Узнайте, как [создать и развернуть политики защиты приложений](app-protection-policies.md) для мобильных приложений Office. 
3. Осуществляйте [мониторинг политик защиты приложений](app-protection-policies-monitor.md), которые вы создаете и развертываете. 

Для устройств Windows 10 

1. Ознакомьтесь с [принципами работы Windows Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip). 
2. Подготовьтесь к настройке [политик защиты приложений для Windows 10](app-protection-policies-configure-windows-10.md).
3. [Создайте и разверните политики защиты приложений WIP с помощью Intune](windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>Что следует рассказать сотрудникам и учащимся

При необходимости поделитесь следующими ссылками для получения дополнительных сведений: 
* [Что происходит при управлении приложением iOS с помощью политик защиты приложений](app-protection-enabled-apps-ios.md)
* [Что происходит при управлении приложением Android с помощью политик защиты приложений](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a>Дальнейшие шаги

Требуется помощь по реализации этого сценария EMS или Office 365 или других? При наличии хотя бы 150 лицензий для Microsoft 365, Microsoft Enterprise Mobility + Security или Azure Active Directory Premium воспользуйтесь [преимуществами FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 
