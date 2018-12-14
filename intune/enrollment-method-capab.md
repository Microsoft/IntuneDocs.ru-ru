---
title: Возможности Intune по регистрации устройств Windows
titlesuffix: Microsoft Intune
description: Возможности для каждого способа регистрации устройств Windows
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
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: f32a0967c094c16b76ad4c4572ebd8e80c6115b2
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032135"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Возможности Intune по регистрации устройств Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Есть несколько способов регистрации корпоративных устройств в Intune. К каждому способу применяются различные рекомендации и возможности, как показано в приведенных ниже таблицах.

## <a name="best-practices-by-enrollment-method"></a>Рекомендации по каждому способу регистрации
| **Рекомендации** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Обычно используется для образовательных учреждений|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Устройства можно использовать в качестве общих|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Личные устройства должны иметь доступ к ресурсам компании|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|
|Самостоятельное обслуживание приложений|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Флажок](media/checkmark.png)|![Флажок](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Возможности по каждому способу регистрации

| **Возможности** | **[Присоединение к Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Присоединение к Azure AD с помощью Autopilot](enrollment-autopilot.md)** |**[Массовая регистрация](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[Объект групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
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

[Настройка регистрации для Windows](windows-enroll.md)

