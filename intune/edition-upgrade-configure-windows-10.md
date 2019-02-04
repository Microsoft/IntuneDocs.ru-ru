---
title: Обновление устройств Windows 10 или использование S-режима на них с помощью Microsoft Intune в Azure | Документы Майкрософт
description: Используйте Microsoft Intune для обновления устройств Windows 10 до различных выпусков или для включения S-режима. Администраторы могут использовать профиль конфигурации устройства для обновления Windows 10 Профессиональной до Windows 10 Корпоративной, а также чтобы включать и выключать S-режим. См. также поддерживаемые варианты обновления для Windows 10 Pro, выпуск N, для образовательных учреждений, Cloud, Enterprise, Core, Holographic и Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3eea1d1f100515b29dfda3b2297005f61e05ea23
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831621"
---
# <a name="upgrade-windows-10-editions-or-enable-s-mode-on-devices-using-microsoft-intune"></a>Обновление устройств Windows 10 или использование S-режима на них с помощью Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Вам может потребоваться обновление ваших устройств Windows 10 в рамках вашего решения управления мобильными устройствами (MDM). Например, вы можете обновить устройство с Windows 10 Профессиональной до Windows 10 Корпоративной. Вы также можете включить S-режим для мобильных устройств, чтобы они выполняли запуск приложений только из Microsoft Store.

[S-режим в Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) призван повысить безопасность и производительность. Если на устройствах выполняются только приложения из Microsoft Store, с помощью S-режима можно обеспечить защиту устройств. Если устройства используют приложения, которые недоступны в Microsoft Store, выйдите из S-режима. Выход из S-режима необратим. После выхода из S-режима в Windows 10 вернуться в него невозможно.

Данная функция применяется к:

- Windows 10 и более поздней версии
- Windows 10 1809 или более поздней версии для использования S-режима
- Windows Holographic for Business

Эти функции настраиваются администратором и доступны в Intune. Intune использует "профили конфигурации" для создания и настройки этих параметров для вашей организации. После того как вы добавили эти компоненты в профиле, можете передать или развернуть профиль в устройство с Windows 10 в вашей организации. Во время развертывания профиля Intune автоматически обновляет устройство или включает S-режим.

В этой статье перечислены поддерживаемые пути обновления и показано, как создать профиль конфигурации устройства. Вы также можете увидеть все доступные обновления и настройки S-режима для Windows 10 в [этой статье](edition-upgrade-windows-settings.md).

> [!NOTE]
> Если позднее удалить назначение политики, откат версии Windows на устройстве не выполняется. Устройство продолжает выполнение в обычном режиме.

## <a name="prerequisites"></a>Предварительные условия

Прежде чем начать процесс обновления, выполните следующие необходимые условия.

- Допустимый ключ продукта для установки новой версии Windows на всех целевых устройствах политики (для выпусков Windows 10 Desktop). Вы можете использовать либо ключи многократной активации (MAK), либо ключи сервера управления ключами (KMS).
- Для выпусков Windows 10 Mobile и Windows 10 Holographic вы можете использовать лицензионный файл Microsoft. Лицензионный файл включает в себя сведения о лицензии, чтобы установить обновленную версию на всех целевых устройствах политики.
- Целевые устройства Windows 10, которым назначается политика, должны быть зарегистрированы в Microsoft Intune. Политику обновления выпусков нельзя использовать на компьютерах под управлением клиентского программного обеспечения Intune.

## <a name="supported-upgrade-paths"></a>Поддерживаемые варианты обновления

Ниже приведен список поддерживаемых вариантов обновления для профиля обновления выпуска Windows 10.

| Обновление с | Обновление до |
|---|---|
| Windows 10 Pro | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro для образовательных учреждений |
| Windows 10 Профессиональная N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Pro для образовательных учреждений | Windows 10 для образовательных учреждений | 
| Windows 10 Pro для образовательных учреждений N | Windows 10 для образовательных учреждений N |
| Windows 10 Cloud | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro <br/>Windows 10 Pro для образовательных учреждений | 
| Windows 10 Cloud N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Профессиональная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Корпоративная | Windows 10 для образовательных учреждений | 
| Windows 10 Корпоративная N | Windows 10 для образовательных учреждений N | 
| Windows 10 Core | Windows 10 для образовательных учреждений <br/>Windows 10 Корпоративная <br/>Windows 10 Pro для образовательных учреждений | 
| Windows 10 Core N | Windows 10 для образовательных учреждений N <br/>Windows 10 Корпоративная N <br/>Windows 10 Pro для образовательных учреждений N | 
| Windows 10 Holographic | Windows 10 Holographic для бизнеса |
| Windows 10 Mobile | Windows 10 Mobile Корпоративная |

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

## <a name="create-the-profile"></a>Создание профиля

1. На [портале Azure](https://portal.azure.com) выберите **Все службы** > отфильтруйте список по **Intune** > выберите **Intune**.
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя**. Введите описательное имя для нового профиля. Например, можно ввести `Windows 10 edition upgrade profile` или `Windows 10 switch off S mode`.
    - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите платформу:  

        - **Windows 10 и более поздних версий**.

    - **Тип профиля**. Выберите **Обновление выпуска**.
    - **Параметры**: Введите параметры, которые вы хотите настроить. См. полный список параметров и сведения об их назначении:

        - [Windows 10 (and newer) device settings to upgrade editions or enable S mode in Intune](edition-upgrade-windows-settings.md) (Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения S-режима в Intune)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Щелкните **OK** > **Создать**, чтобы сохранить изменения. 

Созданный вами профиль отобразится в списке. Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).

## <a name="next-steps"></a>Дальнейшие шаги

Созданный профиль готов к назначению. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Просмотрите все параметры обновления и S-режима в статьях [Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения режима S в Intune](edition-upgrade-windows-settings.md) или [Обновление устройств с Windows Holographic до Windows Holographic for Business](holographic-upgrade.md).
