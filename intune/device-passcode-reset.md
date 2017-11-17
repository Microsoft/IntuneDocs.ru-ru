---
title: "Сброс и удаление секретных кодов устройств с помощью Intune"
titlesuffix: Azure portal
description: "Сведения о том, как сбросить и удалить секретный код устройств, управляемых в Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: 474a24ba67f6bf4f00268bf9e4eba52331a6b82d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Сброс и удаление секретного кода на устройствах, управляемых в Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

В этой статье термины *удаление* и *сброс* взаимозаменяемы.

Действие **Удалить секретный код** создает для устройства новый секретный код, который отображается в колонке  **Обзор**<*имя устройства*> .

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — не поддерживается
- Windows Phone — поддерживается с Windows Phone 8.1 до Windows 10 Creators Update без присоединения к Azure AD, Windows 10 Creators Update и более поздние версии
- iOS — поддерживается
- macOS — не поддерживается
- Android — поддерживается в версиях до Android 7. Android for Work не поддерживается.

## <a name="how-to-reset-a-passcode"></a>Сброс секретного кода

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем — удаленное действие устройства **Удалить секретный код**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
