---
title: "Синхронизация устройств с Intune"
titlesuffix: Azure portal
description: "Сведения о синхронизации устройств с Intune для получения последних политик и действий."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab24b147b32c94ba51728c0c223de3e6c92dd215
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Синхронизация устройств с Intune для получения последних политик и действий


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие устройства **Синхронизация** заставляет выбранное устройство немедленно выполнить возврат в Intune. При возврате устройство сразу же получает все ожидающие действия или политики, которые были ему назначены.  Это действие позволяет сразу проверять назначенные политики и устранять возникшие с ними неполадки, не дожидаясь следующего запланированного возврата.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается
- Windows Phone — поддерживается
- iOS — поддерживается
- macOS — поддерживается
- Android — поддерживается

## <a name="how-to-sync-a-device"></a>Синхронизация устройства

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем — удаленное действие **Синхронизация**.
7. Нажмите кнопку **Да**, чтобы подтвердить действие.

## <a name="next-steps"></a>Дальнейшие действия

Выберите **Действия устройства**, чтобы просмотреть состояние действия синхронизации. 
