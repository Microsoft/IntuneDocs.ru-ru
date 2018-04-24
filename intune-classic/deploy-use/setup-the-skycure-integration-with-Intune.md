---
title: Настройка интеграции Skycure и Intune
description: Настройка интеграции Skycure и Microsoft Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 93722f66-7641-4a3f-b1fb-3a0a58a36675
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 63713cd46da1d1222ec5766a55a7e7344a0a0d26
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Настройка интеграции Skycure и Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Для получения возможности единого входа нужно добавить приложения Skycure в Azure AD.

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Для интеграции Intune и Skycure используется учетная запись Azure AD

-   Перед началом процесса базовой настройки Skycure убедитесь, что у вас есть учетная запись Azure AD, соответствующим образом настроенная в [консоли управления Skycure](https://aad.skycure.com).

### <a name="full-integration-vs-read-only"></a>Полная интеграция и интеграция Только чтение

Skycure поддерживает два режима интеграции с Intune.

-   **Интеграция только для чтения (базовая настройка)**: выполняется лишь инвентаризация устройств из Azure Active Directory и их внесение в консоль Skycure.
<br>
    -   Если в панели управления Skycure не выбраны параметры **Сообщать о работоспособности и рисках устройств в Intune** и **Также передавать инциденты безопасности в Intune**, то интеграция рассматривается в режиме "только для чтения" и не позволит изменять состояние устройств (соответствующих или не соответствующих требованиям) в Intune.
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

    ![Консоль управления приложениями для iOS в Skycure](../media/mtp/skycure-setup-1.png)

5.  Откроется страница входа. Введите учетные данные Intune, а затем нажмите кнопку **Принять**.

    ![Окно входа приложений для iOS в Intune](../media/mtp/skycure-setup-2.png)

6.  После добавления приложения в Azure AD отметка успешного добавления показывается в консоли управления Skycure.

    ![Экран завершения для приложения для iOS](../media/mtp/skycure-setup-3.png)

> [!NOTE]
> Повторите те же действия для приложений **Skycure Android** и **Управление**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Добавление группы безопасности Azure AD в Skycure

Необходимо добавить группу безопасности Azure AD со всеми устройствами, на которых работает Skycure.

1.  Введите и выберите все группы безопасности с устройствами, на которых работает Skycure, а затем нажмите кнопку **Применить изменения**.

    ![Настройка групп безопасности, консоль управления Skycure](../media/mtp/skycure-setup-4.png)

Skycure синхронизирует устройства, на которых работает служба защиты мобильных устройств от угроз, с группами безопасности Azure AD.

![Завершение настройки групп безопасности в консоли управления Skycure](../media/mtp/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Настройка полной интеграции между Intune и Skycure

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

3.  Перейдите в раздел **Параметры** и выберите пункт **Полная интеграция** в разделе **Интеграция Intune**.

4.  Проверьте следующие настройки.

    a.  Сообщать в Intune о работоспособности и рисках устройств

    b.  Также передавать в Intune инциденты безопасности

5.  Нажмите кнопку **Применить изменения**.

    ![Полная интеграция Skycure завершена](../media/mtp/skycure-setup-6.png)

## <a name="next-steps"></a>Дальнейшие шаги

[Включение службы защиты мобильных устройств от угроз Skycure в Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)
