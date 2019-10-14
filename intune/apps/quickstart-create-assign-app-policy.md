---
title: Краткое руководство. Создание и назначение политики защиты приложений
titleSuffix: Microsoft Intune
description: В этом кратком руководстве вы будете использовать Microsoft Intune для создания и назначения политики защиты приложений.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8642672de048b88f709fef72d2027ec78c3b4327
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724637"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Краткое руководство. Создание и назначение политики защиты приложения

В этом кратком руководстве вы будете использовать Intune для создания и назначения политики защиты приложений для клиентского приложения на устройстве конечного пользователя. Intune использует политики защиты приложений, чтобы гарантировать, что ваши приложения соответствуют требованиям к защите данных организации.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Предварительные условия

- Для работы с этим кратким руководством необходимо [создать пользователя](../fundamentals/quickstart-create-user.md), [создать группу](../fundamentals/quickstart-create-group.md), [зарегистрировать устройство](../quickstart-setup-auto-enrollment.md) и [добавить и назначить приложение](../quickstart-add-assign-app.md).

## <a name="sign-in-to-intune"></a>Вход в Intune

Войдите в [Intune](https://aka.ms/intuneportal) в качестве [глобального администратора или администратора службы Intune](../fundamentals/users-add.md#types-of-administrators). Если вы создали подписку на пробную версию Intune, учетная запись, с помощью которой вы создали подписку, является глобальным администратором.

## <a name="create-an-app-protection-policy"></a>Создание политики защиты приложений

Чтобы создать политику защиты приложений, сделайте следующее:

1. На панели [Intune](https://aka.ms/intuneportal) выберите **Клиентские приложения** > **Политики защиты приложений** > **Создать политику**. 
2. Введите следующие сведения: 

    - **Имя**. *Защита содержимого Windows 10*
    - **Описание** *Пользователи, связанные с этой политикой, не смогут вырезать, копировать и вставлять содержимое из назначенного приложения в другие неуправляемые приложения на устройстве.*
    - **Платформа**. *Windows 10*
    - **Состояние регистрации**: *С регистрацией*

3. Выберите **Защищенные приложения**, чтобы выбрать приложения, которые должны соответствовать этой политике.
4. Нажмите кнопку **Добавить приложения**.
5. В разделе **Рекомендуемые приложения** выберите **Word Mobile**.
5. Щелкните **OK** > **OK**. 
6. Выберите **Обязательные параметры**, чтобы настроить приложение.
7. Нажмите кнопку **Разрешить переопределения**, чтобы задать режим Windows Information Protection. Этот параметр блокирует перемещение корпоративных данных из защищенного приложения.
8. Нажмите кнопку **ОК** > **Создать**.

Теперь вы увидите политику защиты приложений в Intune.

### <a name="assign-the-app-protection-policy"></a>Назначение политики защиты приложений

После создания политики защиты приложений в Intune ее можно назначить группам. 

Ниже приведены инструкции по назначению политики защиты приложений.

1. в [Intune](https://aka.ms/intuneportal) выберите **Intune** > **Клиентские приложения** > **Политики защиты приложений**. 
2. Выберите нужную политику защиты приложений. В этом кратком руководстве это политика **Защита содержимого Windows 10**.
3. Выберите **Назначения**.
4. На вкладке **Включить** выберите **Выбрать группы для включения**.
5. Выберите группу **Тест-инженеры Contoso**.
6. Выберите **Выбрать** > **Сохранить**. 

Теперь политика защиты приложений назначена.

> [!NOTE]
> Политики защиты приложений можно применять только к группам, которые содержат пользователей, но не устройства.

## <a name="next-steps"></a>Дальнейшие шаги

В этом кратком руководстве вы создали и назначили политику защиты приложений. Пользователи приложения, которым назначена эта политика, не смогут вырезать, копировать и вставлять любое содержимое между назначенным приложением и другими неуправляемыми приложениями на устройстве. Этот тип защиты позволяет защитить данные организации. Дополнительные сведения о политиках защиты приложений в Intune см. в статье [Что такое политики защиты приложений?](app-protection-policy.md).

Чтобы выполнить эту серию кратких руководств по Intune, переходите к следующему руководству.

> [!div class="nextstepaction"]
> [Краткое руководство. Создание и назначение настраиваемой роли](../fundamentals/create-custom-role.md)