---
title: "Сброс и удаление секретных кодов устройств с помощью Intune"
titlesuffix: Azure portal
description: "Сведения о том, как сбросить и удалить секретный код устройств, управляемых в Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ff5fb2634e2bc6019404d55d1c322146b32eb7f
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
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

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
