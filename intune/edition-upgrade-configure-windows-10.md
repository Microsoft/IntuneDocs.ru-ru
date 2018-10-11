---
title: Обновление устройств Windows 10 или использование S-режима на них с помощью Microsoft Intune — Azure | Документы Майкрософт
description: Создайте профиль устройства в Microsoft Intune для обновления устройств Windows 10 до различных выпусков. Например, можно обновить Windows 10 Профессиональная до Windows 10 Корпоративная. С помощью профиля конфигурации можно также перейти в S-режим или выйти из него на устройстве. См. также поддерживаемые варианты обновления для Windows 10 Pro, выпуск N, для образовательных учреждений, Cloud, Enterprise, Core, Holographic и Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e4ba42559a068ebefb453aba18060803dc36e0
ms.sourcegitcommit: f3974c810e172f345853dacd7f2ca0abc11b1a5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44389631"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Обновление Windows 10 или выход из S-режима в Intune с помощью профиля конфигурации
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настройте профиль обновления в Intune, чтобы автоматически обновить до другого выпуска устройства, работающие под управлением Windows 10. Также см. поддерживаемые варианты обновления.

## <a name="before-you-begin"></a>Подготовка к работе
Перед тем как обновить устройства до последней версии, потребуются следующие компоненты.

- Допустимый ключ продукта для установки новой версии Windows на всех целевых устройствах политики (для выпусков Windows 10 Desktop). Вы можете использовать либо ключи многократной активации (MAK), либо ключи сервера управления ключами (KMS). Для Windows 10 Mobile и Windows 10 Holographic можно использовать файл лицензии Майкрософт, который содержит сведения о лицензии для установки новой версии Windows на всех целевых устройствах, которые подпадают под действие политики.
- Целевые устройства Windows 10, которым назначается политика, должны быть зарегистрированы в Microsoft Intune. Политику обновления выпусков нельзя использовать на компьютерах под управлением клиентского программного обеспечения Intune.

## <a name="supported-upgrade-paths"></a>Поддерживаемые варианты обновления
Ниже приведен список поддерживаемых вариантов обновления для профиля обновления выпуска Windows 10.

| Обновление с | Обновление до |
|---|---|
| Windows 10 Pro | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro для образовательных учреждений |
| Windows 10 Профессиональная N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Pro для образовательных учреждений | Windows 10 для образовательных учреждений | 
| Windows 10 Pro для образовательных учреждений N | Windows 10 для образовательных учреждений N |
| Windows 10 Cloud | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro <br/>Windows 10 Pro для образовательных учреждений | 
| Windows 10 Cloud N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Профессиональная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Корпоративная | Windows 10 для образовательных учреждений | 
| Windows 10 Корпоративная N | Windows 10 для образовательных учреждений N | 
| Windows 10 Core | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro для образовательных учреждений | 
| Windows 10 Core N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Holographic | Windows 10 Holographic для бизнеса |
| Windows 10 Mobile | Windows 10 Mobile Корпоративная |


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="upgrade-the-edition"></a>Обновление выпуска

1. На [портале Azure](https://portal.azure.com) выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Введите **имя** и **описание** для профиля. Например, можно ввести `Windows 10 edition upgrade`.
4. В поле **Платформа** выберите **Windows 10 и более поздние версии**.
5. В поле **Тип профиля** выберите **Обновление выпуска**.
6. В свойствах **Обновление выпуска** настройте следующие параметры:

   - **Выпуск, до которого необходимо обновить**: выберите выпуск Windows 10, до которого производится обновление. Устройства, на которые распространяется данная политика, обновляются до выбранного выпуска.
   - **Ключ продукта**: укажите ключ продукта, полученный от Майкрософт. После создания политики с помощью ключа продукта ключ невозможно обновить. Он скрыт по соображениям безопасности. Чтобы изменить его, необходимо повторно ввести весь ключ.
   - **Файл лицензии**: для выпуска **Windows 10 Holographic for Business** или **Windows 10 Mobile** нажмите кнопку **Обзор**, чтобы выбрать файл лицензии, полученный от Майкрософт. Этот файл лицензии содержит сведения о лицензии для выпусков, до которых обновляются целевые устройства.

7. Нажмите кнопку **OK**, чтобы сохранить изменения. Выберите **Создать** для создания профиля.

## <a name="switch-out-of-s-mode"></a>Выход из S-режима

[S-режим в Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) призван повысить безопасность и производительность. Если на устройствах выполняются только приложения из Microsoft Store, с помощью S-режима можно обеспечить защиту устройств. Если на устройствах требуются приложения, которые недоступны в Microsoft Store, выйдите из S-режима. Выход из S-режима необратим. После выхода из S-режима в Windows 10 вернуться в него невозможно.

Ниже описано, как создать профиль для управления S-режимом в Windows 10 (версии 1809 или более поздней).

1. На [портале Azure](https://portal.azure.com) выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Введите **имя** и **описание** для профиля. Например, можно ввести `Windows 10 switch off S mode`.
4. В поле **Платформа** выберите **Windows 10 и более поздние версии**.
5. В поле **Тип профиля** выберите **Обновление выпуска**.
6. Выберите **Смена режима (только для участников программы предварительной оценки Windows)** и задайте свойство **Выход из S-режима**. Доступны следующие параметры:

    - **Без настройки**: устройство остается в S-режиме. Пользователь может вывести устройство из S-режима.
    - **Оставаться в S-режиме**: пользователь не сможет вывести устройство из S-режима.
    - **Смена**: устройство выводится из S-режима.

7. Нажмите кнопку **OK**, чтобы сохранить изменения. Выберите **Создать** для создания профиля.

Созданный профиль отобразится в списке профилей.

## <a name="next-steps"></a>Дальнейшие шаги

[Назначьте профиль](device-profile-assign.md) группам.

>[!NOTE]
>Если позднее удалить назначение политики, откат версии Windows на устройстве не выполняется и она продолжает нормальную работу.
