---
title: Обновление устройств Windows 10 с помощью Microsoft Intune — Azure | Документы Майкрософт
description: Создание профиля устройства в Microsoft Intune для обновления устройств Windows 10 до более новой версии. См. также поддерживаемые варианты обновления для Windows 10 Pro, выпуск N, для образовательных учреждений, Cloud, Enterprise, Core, Holographic и Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 994ab8e7d955d18b293e4d9e9661e0c44baaaa1f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="configure-windows-10-edition-upgrade-profile-in-intune"></a>Настройка профиля обновления выпуска Windows 10 в Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Настройте профиль обновления в Intune, чтобы автоматически обновить до другого выпуска устройства, работающие под управлением Windows 10. Также см. поддерживаемые варианты обновления.

## <a name="before-you-begin"></a>Подготовка к работе
Перед тем как обновить устройства до последней версии, потребуется один из следующих элементов:

- Допустимый ключ продукта для установки новой версии Windows на всех целевых устройствах политики (для выпусков Windows 10 Desktop). Вы можете использовать либо ключи многократной активации (MAK), либо ключи сервера управления ключами (KMS). Или можно использовать файл лицензии Майкрософт со сведениями о лицензии для установки новой версии Windows на всех целевых устройствах, которые подпадают под действие политики (для выпусков Windows 10 Mobile и Windows 10 Holographic).
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

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Создание профиля устройства с параметрами ограничения для устройства
1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Конфигурация устройства** и нажмите **Профили**, а затем **Создать профиль**.
4. Введите **имя** и **описание** профиля обновления выпуска.
5. В раскрывающемся списке **Платформа** выберите **Windows 10 и более поздних версий**.
6. В раскрывающемся списке **Тип профиля** выберите **Обновление выпуска**.
7. В свойствах **Обновление выпуска** настройте следующие параметры:
   - **Выпуск, до которого необходимо обновить**. В раскрывающемся списке выберите версию Windows 10 Desktop, Windows 10 Holographic или Windows 10 Mobile, до которой вы хотите обновить целевые устройства.
   - **Ключ продукта**. Укажите ключ продукта, полученный от Майкрософт, с помощью которого можно обновить все целевые устройства Windows 10 Desktop. 
    После создания политики, содержащей ключ продукта, ключ невозможно обновить. Он скрыт по соображениям безопасности. Чтобы изменить его, необходимо повторно ввести весь ключ.
   - **Файл лицензии**. Нажмите **Обзор** чтобы выбрать файл лицензии, полученный от Майкрософт. Этот файл лицензии содержит сведения о лицензии для выпуска Windows Holographic или Windows 10 Mobile, до которых обновляются целевые устройства.
8. Когда закончите, нажмите **Создать**, чтобы сохранить изменения.

Созданный профиль отобразится в списке профилей.

## <a name="next-steps"></a>Дальнейшие шаги

Сведения о том, как назначить этот профиль группам, см. в статье [Назначение профилей устройств](device-profile-assign.md).

>[!NOTE]
>Если позднее удалить назначение политики, откат версии Windows на устройстве не выполняется и она продолжает нормальную работу.