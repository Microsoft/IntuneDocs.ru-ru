---
title: Добавление системных приложений Android для бизнеса в Microsoft Intune
titleSuffix: ''
description: Сведения о добавлении системных приложений Android для бизнеса в Microsoft Intune
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ffc99b34016eba6511f63d1df2184abc3cae858
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725170"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Добавление системных приложений Android для бизнеса в Microsoft Intune

Перед назначением приложения устройству или группе пользователей необходимо сначала добавить его в Microsoft Intune. Системные приложения поддерживаются на устройствах Android Enterprise. Вы можете включить системное приложение для [выделенных устройств Android для бизнеса](../enrollment/android-kiosk-enroll.md) или [полностью управляемых устройств](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Добавление приложения

Вы можете добавить приложение Android для бизнеса в Intune на портале Azure, сделав следующее:

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. В панели **Intune** выберите **Клиентские приложения** > **Приложения** > **Добавить**.
3. В области **Добавление приложения** выберите пункт **Системное приложение Android для бизнеса** в списке доступных типов **Другие**.
4. Чтобы настроить сведения о приложении, выберите **Настройка** и укажите следующие сведения.
    - **Имя приложения**. Введите имя приложения.
    - **Издатель**. Введите имя издателя приложения.  
    - **Имя пакета**. Введите имя пакета. Intune проверит допустимость имени пакета.
5. Нажмите кнопку **ОК**.
6. Нажмите кнопку **Добавить**.

Созданное приложение отображается в списке приложений, из которого его можно назначить выбранным группам. 

Системные приложения Android для бизнеса включат или отключат приложения, которые уже являются частью платформы. Чтобы включить приложение, назначьте системное приложение как **Обязательное**. Чтобы отключить приложение, назначьте системное приложение как **Удалить**. Системные приложения нельзя назначить как доступные для пользователя.

## <a name="next-steps"></a>Дальнейшие шаги

- [назначение приложений группам](apps-deploy.md).
