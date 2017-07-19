---
title: "Начало работы с группами"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Начало работы с группами

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Microsoft Intune использует Azure Active Directory (Azure AD) для [управления доступом к корпоративным ресурсам](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Этот доступ контролируется с помощью ролей в каталоге. Затем Intune управляет этим доступом для мобильных устройств, позволяя членам этой группы получить доступ к ресурсам.

__Создание группы__

1. Войдите на [портал Azure](https://portal.azure.com).
2. С помощью функции **Поиск ресурсов** найдите раздел **Пользователи и группы**.
3. Открыв колонку **Пользователи и группы**, выберите **Все группы**.
4. В колонке **Пользователи и группы — все группы** выберите **Создать группу**.
5. В колонке **Группа** добавьте **Имя** и **Описание** для группы.
6. Задайте значение **Назначено** для параметра **Тип членства**. Не используйте параметр **Включить функции Office** для тестовой группы.
7. Нажмите кнопку **Создать**.

Если вы успешно создали группу, она должна появиться в списке **Все группы**. В противном случае попробуйте создать другую группу.
