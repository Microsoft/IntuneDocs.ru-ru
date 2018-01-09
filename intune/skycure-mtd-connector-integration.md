---
title: "Настройка интеграции Skycure и Intune"
titlesuffix: Azure portal
description: "Настройка интеграции Skycure и Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5662d1add7d5b35f3c2c8cd7a8f9900d197a3548
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/30/2017
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Настройка интеграции Skycure и Intune

Для получения возможности единого входа нужно добавить приложения Skycure в Azure AD.

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Для интеграции Intune и Skycure используется учетная запись Azure AD

-   Перед началом процесса базовой настройки Skycure убедитесь, что у вас есть учетная запись Azure AD, соответствующим образом настроенная в [консоли управления Skycure](https://aad.skycure.com).

### <a name="full-integration-vs-read-only"></a>Полная интеграция и интеграция Только чтение

Skycure поддерживает два режима интеграции с Intune.

-   **Интеграция только для чтения (базовая настройка)**: выполняется лишь инвентаризация устройств из Azure Active Directory и их внесение в консоль Skycure.
<br>
    -   Если в панели управления Skycure не выбраны параметры **Сообщать о работоспособности и рисках устройств в Intune** и **Также передавать инциденты безопасности в Intune**, то интеграция рассматривается как "только для чтения" и никогда не будет менять состояние устройств (соответствующих или не соответствующих требованиям) в Intune.
<br></br>
-   **Полная интеграция**: Skycure может сообщать в Intune об устройствах с рисками и об инцидентах безопасности, что создает двунаправленное взаимодействие между обоими облачными службами.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Как приложения Skycure используются с Azure AD и Intune?

-   **Приложение для iOS**: позволяет конечным пользователям входить в Azure AD с помощью приложения для iOS.

-   **Приложение для Android**: позволяет конечным пользователям входить в Azure AD с помощью приложения Android.

-   **Приложение управления**: это мультитенантное приложение Skycure для Azure AD, которое обеспечивает взаимодействие типа "служба-служба" с Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Настройка интеграции между Intune и Skycure только для чтения

> [!IMPORTANT]
> Учетные данные администратора Skycure — это адрес электронной почты, который должен принадлежать действительному пользователю в Azure Active Directory; в противном случае войти не удастся. Skycure использует Azure Active Directory для проверки подлинности администратора с помощью единого входа (SSO).

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

3.  Перейдите в раздел **Параметры** и выберите пункт **Базовая настройка** в разделе **Интеграция Intune**.

4.  В разделе **Приложение iOS** выберите команду **Добавить в Active Directory**.

    ![Консоль управления приложениями для iOS в Skycure](./media/skycure-setup-1.png)

5.  Откроется страница входа. Введите учетные данные Intune, а затем нажмите кнопку **Принять**.

    ![Окно входа приложений для iOS в Intune](./media/skycure-setup-2.png)

6.  После добавления приложения в Azure AD отметка успешного добавления показывается в консоли управления Skycure.

    ![Экран завершения для приложения для iOS](./media/skycure-setup-3.png)

> [!NOTE]
> Повторите те же действия для приложений **Skycure Android** и **Управление**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Добавление группы безопасности Azure AD в Skycure

Необходимо добавить группу безопасности Azure AD со всеми устройствами, на которых работает Skycure.

1.  Введите и выберите все группы безопасности с устройствами, на которых работает Skycure, а затем нажмите кнопку **Применить изменения**.

    ![Настройка групп безопасности, консоль управления Skycure](./media/skycure-setup-4.png)

Skycure синхронизирует устройства, на которых работает служба защиты мобильных устройств от угроз, с группами безопасности Azure AD.

![Завершение настройки групп безопасности в консоли управления Skycure](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Настройка полной интеграции между Intune и Skycure

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

3.  Перейдите в раздел **Параметры** и выберите пункт **Полная интеграция** в разделе **Интеграция Intune**.

4.  Проверьте следующие настройки.

    a.  Сообщать в Intune о работоспособности и рисках устройств

    b.  Также передавать в Intune инциденты безопасности

5.  Нажмите кнопку **Применить изменения**.

    ![Полная интеграция Skycure завершена](./media/skycure-setup-6.png)

## <a name="next-steps"></a>Дальнейшие шаги

[Настройка приложений Skycure](mtd-apps-ios-app-configuration-policy-add-assign.md)
