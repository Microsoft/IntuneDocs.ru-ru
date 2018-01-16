---
title: "Удаление пользователя с устройства iOS с помощью Intune"
titlesuffix: Azure portal
description: "Вы можете узнать, как удалить пользователя с устройства iOS с помощью Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b99e42318a5432f0ad27fb7d6dc2054220b3a0a
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Удаление пользователя с общего устройства iOS с помощью Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Удалить пользователя** удаляет выбранного пользователя из локального кэша на общем устройстве iPad, где настроена работа с iOS-приложением «Класс» с использованием [Профиля образования iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — не поддерживается
- Windows Phone — не поддерживается
- iOS — поддерживается в iOS 9.3 и более поздних версиях (только общие устройства iPad)
- macOS — не поддерживается
- Android — не поддерживается

## <a name="how-to-remove-a-user"></a>Удаление пользователя

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства** выберите **Все устройства**.
5. Выберите нужное устройство iOS в списке управляемых устройств.
6. В колонке для этого устройства выберите **Пользователи**.
7. В списке щелкните имя удаляемого пользователя правой кнопкой мыши и выберите пункт **Удалить пользователя**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
