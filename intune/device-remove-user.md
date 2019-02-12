---
title: Удаление пользователя с устройства iOS с помощью Microsoft Intune
titlesuffix: ''
description: Узнайте, как удалить пользователя с устройства iOS с помощью Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c00e026a6877097abd266a7ed800500a0f467123
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851361"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Удаление пользователя с общего устройства iOS


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Действие **Удалить пользователя** удаляет выбранного пользователя из локального кэша на общем устройстве iOS. Устройство iPad необходимо настроить для управления приложением iOS Classroom с помощью [профиля образования iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — не поддерживается
- Windows Phone — не поддерживается
- iOS — поддерживается в iOS 9.3 и более поздних версиях (только общие устройства iPad)
- macOS — не поддерживается
- Android — не поддерживается

## <a name="remove-a-user"></a>Удаление пользователя

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.
3. На панели **Intune** выберите **Устройства**.
4. На панели **Устройства** выберите **Все устройства**.
5. Выберите нужное устройство iOS в списке управляемых устройств.
6. В области для устройства выберите **Пользователи**.
7. В списке щелкните имя удаляемого пользователя правой кнопкой мыши и выберите пункт **Удалить пользователя**.

## <a name="next-steps"></a>Дальнейшие шаги

- Чтобы отобразились сведения о состоянии действия **Удалить пользователя**, выберите **Устройства** > **Действия устройства**.
