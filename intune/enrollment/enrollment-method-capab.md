---
title: Возможности Intune по регистрации устройств Windows
titleSuffix: Microsoft Intune
description: Возможности для каждого способа регистрации устройств Windows
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b68ec61496c3c15acc8facc22a6fdfe3c65f06eb
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547874"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Возможности Intune по регистрации устройств Windows
[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Есть несколько способов регистрации корпоративных устройств в Intune. К каждому способу применяются различные рекомендации и возможности, как показано в приведенных ниже таблицах.

## <a name="best-practices-by-enrollment-method"></a>Рекомендации по каждому способу регистрации
| **Рекомендации** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot (пользовательский режим)](enrollment-autopilot.md)** |**[Присоединение к Azure AD с помощью Autopilot (режим самостоятельного развертывания)](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Совместное управление](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Обычно используется для образовательных учреждений|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Устройства можно использовать в качестве общих|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Личные устройства должны иметь доступ к ресурсам компании|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Самостоятельное обслуживание приложений|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Возможности по каждому способу регистрации

| **Возможности** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot (пользовательский режим)](enrollment-autopilot.md)** |**[Присоединение к Azure AD с помощью Autopilot (режим самостоятельного развертывания)](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Совместное управление](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Условный доступ                                      |![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)\*\*|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Пользователи связываются в устройством                    |![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Требуется Azure AD Premium                               |![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Устройство может оценивать ресурсы, защищенные ЦС             |![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Пользователи не должны быть администраторами на своих устройствах               |![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Возможность настройки процедуры конфигурации устройства        |![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Возможность регистрации устройств без участия пользователя      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Возможность выполнения сценариев PowerShell                       |![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/checkmark.png)\*| 
|Поддерживает автоматическую регистрацию после присоединения к домену AD      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Поддерживает автоматическую регистрацию после гибридного присоединения к Azure AD|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|
|Поддерживает автоматическую регистрацию после присоединения к Azure AD       |![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![Флажок](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|

\* Рабочие нагрузки клиентских приложений в Configuration Manager должны быть перемещены в Intune Pilot или Intune.

\** [Устройства заблокированы для условного доступа, за исключением Windows 10 версии 1803 и выше.](device-enrollment-manager-enroll.md)

## <a name="next-steps"></a>Дальнейшие шаги

[Настройка регистрации для Windows](windows-enroll.md)

