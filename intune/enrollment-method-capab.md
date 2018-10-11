---
title: Возможности Intune для каждого способа регистрации устройств Windows
titlesuffix: Microsoft Intune
description: Узнайте, какие возможности поддерживает каждый способ регистрации устройств Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c9e440aef7f434cbe675506fd6f22a9bd26b2c31
ms.sourcegitcommit: 528d2bc70bfd25803a2d9f0fe9372c8a5f5e7dad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47446826"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Возможности каждого способа регистрации устройств Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune позволяет управлять устройствами и приложениями в рамках рабочего процесса, а также способом их доступа к корпоративным данным. Устройства должны быть зарегистрированы в службе Intune. Есть несколько способов регистрации корпоративных устройств. К каждому способу применяются различные рекомендации и возможности, как показано в приведенных ниже таблицах.

## <a name="best-practices-by-enrollment-method"></a>Рекомендации по каждому способу регистрации
| **Рекомендации** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Обычно используется для образовательных учреждений|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Устройства можно использовать в качестве общих|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Личные устройства должны иметь доступ к ресурсам компании|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|
|Самостоятельное обслуживание приложений|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Возможности по каждому способу регистрации

| **Возможности** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Conditional access (Условный доступ)                                      |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Пользователи связываются в устройством                    |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Требуется Azure AD Premium                               |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|
|Устройство может оценивать ресурсы, защищенные ЦС             |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|
|Пользователи не должны быть администраторами на своих устройствах               |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Возможность настройки процедуры конфигурации устройства        |![X](media/xmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Возможность регистрации устройств без участия пользователя      |![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|
|Возможность выполнения сценариев PowerShell                       |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Поддерживает автоматическую регистрацию после присоединения к домену AD      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|
|Поддерживает автоматическую регистрацию после гибридного присоединения к Azure AD|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|
|Поддерживает автоматическую регистрацию после присоединения к Azure AD       |![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Дальнейшие шаги

[Параметры регистрации](enrollment-options.md)

