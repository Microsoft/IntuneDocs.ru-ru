---
title: Выход из системы для пользователя устройства iOS
titlesuffix: Microsoft Intune
description: Вы можете узнать, как выполнить выход из системы для пользователя устройства iOS с помощью Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 223906d37159ba4081f5a5c055392321ac02e0ab
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020628"
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Выход из системы для текущего пользователя на устройствах iOS, управляемых в Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Действие **Выход из системы для текущего пользователя** позволяет вывести из системы текущего пользователя на общем устройстве iPad, где настроена работа с iOS-приложением "Класс" с использованием [Профиля образования iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — не поддерживается
- Windows Phone — не поддерживается
- iOS — поддерживается в iOS 9.3 и более поздних версиях (только общие устройства iPad)
- macOS — не поддерживается
- Android — не поддерживается

## <a name="how-to-logout-the-current-user"></a>Выход текущего пользователя из системы

1.  Зарегистрируйтесь на портале Azure.
2.  Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3.  В колонке **Intune** выберите **Устройства**.
4.  В колонке **Устройства и группы** выберите **Все устройства**.
5.  Выберите нужное устройство iOS в списке управляемых устройств, а затем удаленное действие **Выход из системы для текущего пользователя**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
