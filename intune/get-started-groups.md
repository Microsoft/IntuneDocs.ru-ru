---
title: "Начало работы с группами"
titleSuffix: Intune on Azure
description: "Организация пользователей в группы для упрощения управления политиками и приложениями, к которым они могут получить доступ."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 276a594abdd3c92051041a5faa34d3ee7633e32c
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-groups"></a>Начало работы с группами

Группы используются для управления пользователями и контроля доступа сотрудников к ресурсам компании. Эти ресурсы могут быть частью вашего каталога либо могут быть внешними ресурсами, такими как приложения SaaS или сайты SharePoint.

Microsoft Intune использует Azure Active Directory (Azure AD) для управления доступом к корпоративным ресурсам. Этот доступ контролируется с помощью ролей в каталоге. Затем Intune управляет этим доступом для мобильных устройств, позволяя членам этой группы получить доступ к ресурсам.

## <a name="how-do-i-create-a-group"></a>Создание группы

1. Войдите на [портал Azure](https://portal.azure.com).
2. С помощью функции **Поиск ресурсов** найдите **Intune**.
3. Открыв колонку **Microsoft Intune**, выберите **Группы**.
4. В колонке **Пользователи и группы — все группы** выберите **Создать группу**.
5. В колонке **Группа** добавьте **Имя** и **Описание** для группы.
6. Задайте значение **Назначено** для параметра **Тип членства**. Не используйте параметр **Включить функции Office** для тестовой группы.
7. Нажмите кнопку **Создать**.

Если вы успешно создали группу, она должна появиться в списке **Все группы**. В противном случае попробуйте создать другую группу.

## <a name="next-steps"></a>Дальнейшие действия

[Начало работы с политиками](get-started-policies.md). Создание политик, запрещающих пользователям выполнять несанкционированные действия на их устройствах.

## <a name="learn-more"></a>Дополнительные сведения

* [Установка ограничений регистрации в Intune](groups-add.md)
* [Использование групп для управления доступом к ресурсам в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
