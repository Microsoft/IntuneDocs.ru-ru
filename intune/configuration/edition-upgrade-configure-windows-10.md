---
title: Обновление устройств Windows 10 или использование S-режима на них с помощью Microsoft Intune в Azure | Документы Майкрософт
description: Используйте Microsoft Intune для обновления устройств с Windows 10 до различных выпусков или для включения режима S. Администраторы могут использовать профиль конфигурации устройства для обновления версии "Windows 10 Профессиональная" до "Windows 10 Корпоративная", а также чтобы выключать режим S. См. также поддерживаемые варианты обновления для Windows 10 Pro, выпуск N, для образовательных учреждений, Cloud, Enterprise, Core, Holographic и Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3595e75a73868378c9c366de6c751c21a9151ae3
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059516"
---
# <a name="upgrade-windows-10-editions-or-switch-out-of-s-mode-on-devices-using-microsoft-intune"></a>Обновление выпусков Windows 10 или выход из режима S на устройствах с помощью Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Вам может потребоваться обновление ваших устройств Windows 10 в рамках вашего решения управления мобильными устройствами (MDM). Например, вы можете обновить устройство с Windows 10 Профессиональной до Windows 10 Корпоративной. Или вы хотите, чтобы устройство вышло из режима S.

[Режим S Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) (открывает другой веб-сайт Майкрософт) предназначен для обеспечения безопасности и высокой производительности. Вы можете использовать Intune для выхода из режима S. Выход из S-режима необратим. После выхода из S-режима в Windows 10 вернуться в него невозможно.

Ознакомьтесь с [часто задаваемыми вопросами](https://support.microsoft.com/help/4020089/windows-10-in-s-mode-faq) о режиме S.

Данная функция применяется к:

- Windows 10 и более поздней версии
- Windows 10 1809 или более поздней версии для использования S-режима
- Windows Holographic for Business

Эти функции настраиваются администратором и доступны в Intune. Intune использует "профили конфигурации" для создания и настройки этих параметров для вашей организации. После того как вы добавили эти компоненты в профиле, можете передать или развернуть профиль в устройство с Windows 10 в вашей организации. При развертывании профиля Intune автоматически обновляет устройства или выходит из режима S.

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

![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)  (X) = not supported    
![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro Education|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro Education N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Cloud|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Cloud N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Enterprise|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Enterprise N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Core|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Core N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Mobile|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Holographic|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png) -->

## <a name="create-the-profile"></a>Создание профиля

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Выберите **Устройства** > **Профили конфигурации** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя**. Введите описательное имя для нового профиля. Например, можно ввести `Windows 10 edition upgrade profile` или `Windows 10 switch off S mode`.
    - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите **Windows 10 и более поздних версий**.
    - **Тип профиля**. Выберите **Обновление выпуска**.
    - **Параметры**: Введите параметры, которые вы хотите настроить. См. полный список параметров и сведения об их назначении:

        - [Windows 10 (and newer) device settings to upgrade editions or enable S mode in Intune](edition-upgrade-windows-settings.md) (Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения S-режима в Intune)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Щелкните **OK** > **Создать**, чтобы сохранить изменения.

Созданный вами профиль отобразится в списке. Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).

## <a name="next-steps"></a>Дальнейшие шаги

Созданный профиль готов к назначению. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Просмотрите все параметры обновления и S-режима в статьях [Параметры устройства Windows 10 (и более поздних) для обновления выпусков или включения режима S в Intune](edition-upgrade-windows-settings.md) или [Обновление устройств с Windows Holographic до Windows Holographic for Business](holographic-upgrade.md).
