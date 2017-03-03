---
title: "Выбор способа управления устройствами | Документы Майкрософт"
description: "Узнайте о различных способах регистрации устройств и управления ими."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e13a9c426e07ebb2443bd403d1a5c7274afd387e
ms.openlocfilehash: dea0700e2901bfed566a87d7c599569219de85a2
ms.lasthandoff: 12/20/2016


---

# <a name="choose-how-to-manage-devices"></a>Выбор способа управления устройствами

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Чтобы воспользоваться преимуществами множества функций, предоставляемых Intune, таких как развертывание приложений и управление параметрами устройств, все устройства должны быть *управляемыми*. Способ управления устройствами зависит от возможностей Intune, которые вы хотите использовать. Сведения в этом разделе помогут вам выбрать метод, который наиболее полно соответствует вашим потребностям.

Чтобы управлять устройствами на базе iOS, Mac OS X, Android или Windows Phone, их следует *зарегистрировать*.

Для управления компьютерами на базе Windows используются два способа:

1. Регистрация устройства **либо**
2. Установка *программного клиента Intune*.

## <a name="decide-which-method-to-use"></a>Выбор применимого способа
Используйте эту диаграмму для принятия решения о способе управления устройствами.

![Диаграмма для принятия решения о способе управления устройствами.](./media/choose-manage-method.png)

Зарегистрируйте компьютеры Windows для получения максимального набора функций. Однако программный клиент Intune может оказаться более уместным в следующих случаях:

- Windows 7
- Обновления программного обеспечения Windows и использование лицензий
- Endpoint Protection и брандмауэр Windows
- Удаленная помощь пользователям с помощью программного обеспечения TeamViewer

Подробное описание возможностей управления, доступных при каждом из способов, см. в разделах [Возможности управления мобильными устройствами](mobile-device-management-capabilities-in-microsoft-intune.md) и [Возможности программного клиента Intune для ПК](windows-pc-management-capabilities-in-microsoft-intune.md).
Сведения об устройствах и компьютерах, поддерживаемых Intune, см. в разделе [Поддерживаемые мобильные устройства и компьютеры](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune#intune-supported-devices).

## <a name="next-steps"></a>Дальнейшие действия

- [Выбор способа регистрации мобильных устройств](/intune/get-started/choose-how-to-enroll-devices1)
- [Управление компьютерами с ОС Windows при помощи клиентского программного обеспечения Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)
- [Управление мобильными устройствами Exchange ActiveSync с использованием Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).

