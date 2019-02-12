---
title: Интеграция Check Point SandBlast MTD | Microsoft Intune
titlesuffix: Microsoft Intune
description: Как настроить решение CheckPoint SandBlast Mobile Threat Defense (MTD) в Intune для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1dcd355ac5b0376db2977f046258ce6bb83a2234
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846707"
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Интеграция Check Point SandBlast Mobile с Intune

## <a name="before-you-begin"></a>Подготовка к работе

> [!NOTE] 
> Описанные ниже действия необходимо выполнить в [консоли Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/).

Перед началом интеграции Check Point SandBlast Mobile с Intune убедитесь, что у вас есть следующее:

-   Подписка на Microsoft Intune

-   Учетные данные администратора Azure Active Directory для предоставления следующих разрешений:

    -   Вход и чтение профилей пользователей

    -   Доступ к каталогу от имени вошедшего в систему пользователя

    -   Чтение данных каталога

    -   Отправка сведений об устройстве в Intune

-   Учетные данные администратора для доступа к консоли Check Point SandBlast Mobile MTD.

### <a name="check-point-sandblast-app-authorization"></a>Авторизация приложения Check Point SandBlast

Авторизация приложения Check Point SandBlast выполняется следующим образом:

-   Вы разрешаете службе Check Point SandBlast Mobile передавать в Intune сведения о состоянии работоспособности устройства.

-   CheckPoint SandBlast Mobile синхронизируется с членством в группе регистрации Azure AD и заполняет базу данных устройства.

-   Вы разрешаете консоли администрирования Check Point SandBlast использовать единый вход (SSO) Azure AD.

-   Вы разрешаете приложению Check Point SandBlast Mobile выполнять вход, используя SSO Azure AD.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Настройка интеграции Check Point SandBlast Mobile

1.  Откройте [Консоль Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/) и выполните вход под своими учетными данными.

2.  Откройте вкладку **Параметры**.

3.  Выберите **Управление устройствами**, а затем **Параметры**.

4.  Выберите **Microsoft Intune** в раскрывающемся списке = **службы MDM**.

5.  После того, как Microsoft Intune будет выбран в качестве службы MDM, появится всплывающее окно **Конфигурация Microsoft Intune**. В этом окне выберите пункт **Добавить в организацию** для каждой платформы ваших устройств: iOS, Android и Windows, чтобы разрешить Check Point SandBlast Mobile взаимодействовать с Intune и Azure AD.

    ![Изображение конфигурации Check Point MTD в Intune](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Чтобы перейти к следующему шагу, необходимо добавить все платформы устройств.

6.  Нажмите кнопку **Принять**, чтобы разрешить приложению Check Point SandBlast Mobile взаимодействовать с Intune и Azure Active Directory.

7.  После того, как все платформы устройств будут включены, необходимо указать группу безопасности Azure AD.

8.  Выберите пункт **Проверка**, а после успешной проверки группы безопасности Azure AD нажмите кнопку **Сохранить**.

## <a name="next-steps"></a>Дальнейшие шаги

- [Настройка приложений Check Point SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)
