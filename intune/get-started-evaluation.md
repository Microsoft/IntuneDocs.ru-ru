---
title: "Начало работы с Intune"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Что такое Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Microsoft Intune на портале Azure](./media/generic-intune-azure.png)

Microsoft Intune — одна из самых новых служб Azure. Она предоставляет [регулярно обновляемые](whats-new.md) средства для управления мобильными устройствами, компьютерами и приложениями в организации. Кроме современной консоли Azure, служба Intune также позволяет использовать классическую консоль. Классическая консоль относится к первой версии Intune и по-прежнему используется [для управления компьютерами на базе Windows с помощью программного клиента Intune](/intune-classic/deploy-use/pc-management-comparison.md). Классический портал, построенный на основе Silverlight, используется для небольшого числа задач. Все остальное, включая управление мобильными устройствами и приложениями, осуществляется на портале Azure. Это руководство по началу работы познакомит вас с основными задачами, которые потребуется выполнить для успешной работы с Intune на портале Azure.

![Колонка справки и поддержки, расположенная в нижней части списка действий в левой боковой панели Intune.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Какие возможности предоставляет Intune на портале Azure?

Intune на портале Azure предоставляет следующие возможности:

* встроенная консоль для всех [компонентов Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security);
* консоль на основе HTML, созданная согласно веб-стандартам и поддерживающая [современные веб-браузеры](supported-devices-browsers.md);
* [группы Azure Active Directory](groups-get-started.md) для обеспечения совместимости во всех приложениях Azure;
* автоматизация работы с помощью [API Microsoft Graph](intune-graph-apis.md).

## <a name="prerequisites"></a>Необходимые компоненты

Перед началом работы нужно активировать учетную запись администратора и клиента Intune. Зарегистрировать эти учетные записи можно [здесь](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Текущие подписчики также могут выполнить эти действия в динамическом клиенте. Убедитесь, что вы работаете только с тестовыми устройствами!

Кроме того, для выполнения всех описанных в руководстве задач вам нужно быть глобальным администратором в своей организации.
