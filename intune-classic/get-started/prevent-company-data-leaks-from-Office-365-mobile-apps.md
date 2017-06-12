---
title: "Предотвращение утечки корпоративных данных из мобильных приложений Office 365 | Документы Майкрософт"
description: "Используйте Intune, чтобы защитить данные своей организации с помощью политик управления мобильными приложениями (MAM), которые позволяют избежать утечки корпоративных данных из мобильных приложений Office 365 и других бизнес-приложений."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: db350fbefe5ed9b1aa796ee8430000d33ebd1b4e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Краткое руководство по началу работы. Предотвращение утечки корпоративных данных из мобильных приложений Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune поможет вам защитить данные своей организации с помощью политик управления мобильными приложениями (MAM), которые позволяют избежать утечки корпоративных данных из мобильных приложений Office 365 и других бизнес-приложений (LOB). Для использования политик Intune MAM от конечных пользователей не требуется регистрировать свои устройства в решении для управления мобильными устройствами (MDM) Intune. Таким образом, если есть пользователи, которые не хотят регистрировать свои мобильные устройства BYOD iOS или Android в решении MDM от корпорации Майкрософт (Intune, Configuration Manager или EAS), или вы хотите защитить корпоративные данные без управления устройствами конечных пользователей, или вы уже используете решение MDM другой компании, то Intune может помочь вам повысить степень защиты своих данных.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Подходит ли для меня это краткое руководство по началу работы?
Вы хотите разрешить конечным пользователям осуществлять доступ к данным приложений Office 365 и бизнес-приложений с помощью устройств iOS и Android, не регистрируясь при этом в решении для управления мобильными устройствами (MDM), но по-прежнему хотите контролировать, какие действия они могут осуществлять с этими данными (например, копировать и вставлять данные в личные приложения)?

Если это так, то Microsoft Intune позволяет задать политики MAM для мобильных приложений Office 365 на устройствах iOS и Android, включая ограничения на вырезание, копирование и вставку, запрет команды "Сохранить как", настройку обязательного ввода ПИН-кода и возможность удаленной очистки данных, защищенных с помощью MAM.  Это обеспечивает защиту корпоративных данных и не требует регистрации устройств в решении MDM, поэтому конечные пользователи смогут по-прежнему комфортно работать с мобильными приложениями Office.

## <a name="how-do-i-do-it"></a>Как это сделать?
1.    Получите общее представление о том, [как происходит управление мобильными приложениями в Intune /intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.    Узнайте, [что необходимо для того, чтобы приступить к созданию политик MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) на портале Azure.
3.    [Создайте и разверните политики MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) с помощью Intune.

### <a name="additional-information"></a>Дополнительная информация:
- [Работа конечных пользователей](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) с приложениями с включенной поддержкой MAM.
- [Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune](/intune-classic/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> Список партнеров Microsoft Intune &rarr;</a>, предоставляющих приложения с включенной поддержкой MAM.

## <a name="what-should-i-do-next"></a>Дальнейшие действия
[Переход с решения MDM другой компании на Microsoft Intune](/intune-classic/deploy-use/migrate-to-intune)

[Регистрация устройств для управления в Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
