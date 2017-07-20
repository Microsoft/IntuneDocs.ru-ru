---
title: "Настройка интеграции Check Point SandBlast Mobile с Intune"
titleSuffix: Intune on Azure
description: "Настройка интеграции Check Point SandBlast Mobile с Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaeaa7eef50b24a1d0b8cc104a673b8676bb7734
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2017
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

    ![Проверка конфигурации точки MTD Intune](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Чтобы перейти к следующему шагу, необходимо добавить все платформы устройств.

6.  Нажмите кнопку **Принять**, чтобы разрешить приложению Check Point SandBlast Mobile взаимодействовать с Intune и Azure Active Directory.

7.  После того, как все платформы устройств будут включены, необходимо указать группу безопасности Azure AD.

8.  Выберите пункт **Проверка**, а после успешной проверки группы безопасности Azure AD нажмите кнопку **Сохранить**.

## <a name="next-steps"></a>Дальнейшие действия

- [Включение соединителя Check Point SandBlast Mobile для Intune](mtd-connector-enable.md)