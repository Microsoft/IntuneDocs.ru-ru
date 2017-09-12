---
title: "Сброс секретного кода устройства с помощью Intune"
titlesuffix: Azure portal
description: "Сведения о том, как сбросить секретный код устройств, управляемых в Intune.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a292342000a4f60455aa44202a1bf0493ae66f0
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Сброс секретного кода на устройствах, управляемых в Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Действие **Сброс секретного кода** создает для устройства новый секретный код, который отображается в колонке **Обзор**<*имя устройства*> .

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
5. Выберите нужное устройство в списке управляемых устройств, а затем действие удаленного устройства **Сброс секретного кода**.

## <a name="next-steps"></a>Дальнейшие действия

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства и группы** выберите **Действия устройства**.
