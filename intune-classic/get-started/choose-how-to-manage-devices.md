---
title: Выбор способа управления устройствами
description: Узнайте о различных способах регистрации устройств и управления ими.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bac3bc13f302dc9c89c9f84b7e65610e92f5ccf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="choose-how-to-manage-devices"></a>Выбор способа управления устройствами

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

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

Подробное описание возможностей управления для каждого способа см. в разделе [Mobile device managem/intune/supported-devices-browserssoft-intune).
Сведения об устройствах и компьютерах, поддерживаемых Intune, см. в разделе [Поддерживаемые мобильные устройства и компьютеры](/intune/supported-devices-browsers#intune-supported-devices).

## <a name="next-steps"></a>Дальнейшие шаги

- [Выбор способа регистрации мобильных устройств](/intune-classic/get-started/choose-how-to-enroll-devices1)
- [Управление компьютерами с ОС Windows при помощи клиентского программного обеспечения Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)
- [Управление мобильными устройствами Exchange ActiveSync с использованием Microsoft Intune](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).
