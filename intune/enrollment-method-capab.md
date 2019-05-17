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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd1dbb3280fbbb93423796b18f6dd85a50a41f11
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567547"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Возможности Intune по регистрации устройств Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Есть несколько способов регистрации корпоративных устройств в Intune. К каждому способу применяются различные рекомендации и возможности, как показано в приведенных ниже таблицах.

## <a name="best-practices-by-enrollment-method"></a>Рекомендации по каждому способу регистрации
| **Рекомендации** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot (пользовательский режим)](enrollment-autopilot.md)** |**[Присоединение к Azure AD с помощью Autopilot (режим самостоятельного развертывания)](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Совместное управление](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Обычно используется для образовательных учреждений|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Устройства можно использовать в качестве общих|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Личные устройства должны иметь доступ к ресурсам компании|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Самостоятельное обслуживание приложений|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Возможности по каждому способу регистрации

| **Возможности** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot (пользовательский режим)](enrollment-autopilot.md)** |**[Присоединение к Azure AD с помощью Autopilot (режим самостоятельного развертывания)](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Совместное управление](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Conditional access (Условный доступ)                                      |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Пользователи связываются в устройством                    |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Требуется Azure AD Premium                               |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Устройство может оценивать ресурсы, защищенные ЦС             |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Пользователи не должны быть администраторами на своих устройствах               |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Возможность настройки процедуры конфигурации устройства        |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Возможность регистрации устройств без участия пользователя      |![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Возможность выполнения сценариев PowerShell                       |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Поддерживает автоматическую регистрацию после присоединения к домену AD      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Поддерживает автоматическую регистрацию после гибридного присоединения к Azure AD|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Поддерживает автоматическую регистрацию после присоединения к Azure AD       |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Дальнейшие шаги

[Настройка регистрации для Windows](windows-enroll.md)

