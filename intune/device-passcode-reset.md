---
title: Сброс секретных кодов для устройств с помощью Microsoft Intune в Azure | Документация Майкрософт
description: Удалите или сбросьте секретный код, используя соответствующее действие на устройствах, управляемых и наблюдаемых с помощью Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Сброс или удаление секретного кода устройства с помощью Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Чтобы создать секретный код устройства, используйте действие **Удалить секретный код**.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Версии, начиная с Windows Phone 8.1 до Windows 10 Creators Update без присоединения к Azure AD, Windows 10 Creators Update и более поздние версии
- iOS
- Android до версии Android 7

Эта возможность **не** поддерживается в следующих системах:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Сброс секретного кода

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Устройства**, а затем — **Все устройства**.
4. Выберите нужное устройство в списке управляемых устройств, а затем нажмите **...Еще** и выберите удаленное действие **Удалить секретный код**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, на панели **Устройства** выберите **Действия устройства**.
