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
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Сброс или удаление секретного кода устройства с помощью Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Чтобы создать секретный код устройства, используйте действие **Удалить секретный код**.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows Phone 8.1 (без присоединения к Azure Active Directory), включая выпуски до Windows 10 Creators Update
- Windows 10 Creators Update и более поздние версии
- iOS
- Android до версии Android 7

Эта возможность не поддерживается в следующих системах:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Сброс секретного кода

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Устройства**, а затем — **Все устройства**.
4. Выберите нужное устройство в списке управляемых устройств и щелкните **Дополнительно**. Затем выберите удаленное действие **Удалить секретный код**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, на панели **Устройства** выберите **Действия устройства**.
