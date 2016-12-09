---
title: "Портал Azure для политик управления мобильными приложениями | Microsoft Intune"
description: "Создание политик управления мобильными приложениями на портале Azure. Создаваемые на портале политики могут применяться к устройствам с регистрацией в Intune или без нее."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: b377d527621693f4c231f6f8b16cab277853cdf7


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Портал Azure для политик управления мобильными приложениями Microsoft Intune

## <a name="use-the-azure-portal"></a>Использование портала Azure
Портал Azure позволяет создавать политики управления мобильными приложениями (MAM) и управлять ими.

Портал Azure поддерживает создание политик MAM для следующих приложений:
- приложения, работающие на устройствах, **зарегистрированных в службе Intune и управляемых ею**;

- приложения, работающие на устройствах, которые **не зарегистрированы** в каком-либо решении для управления мобильными устройствами;
- приложения, работающие на устройствах, которые **зарегистрированы в решении для управления мобильными устройствами стороннего производителя**.

>[!IMPORTANT]


> При использовании консоли администрирования Intune для управления устройствами можно создать политику MAM, поддерживающую приложения на устройствах, зарегистрированных в Intune, с помощью [этой консоли](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> В консоли администрирования Intune могут отображаться не все параметры политики MAM. Портал Azure — это новая консоль администрирования для создания политик MAM. При создании политик MAM в консоли администрирования Intune и на портале Azure политики, созданные на портале Azure, применяются к приложениям и развертываются для пользователей.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Вход на портал Azure и настройка начальной страницы

1.  Перейдите на [портал Azure](https://portal.azure.com) и выполните вход с помощью своих учетных данных [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Снимок экрана со страницей входа на портал Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  После успешного входа вы увидите **панель мониторинга**. Страница **панели мониторинга** является настраиваемой.

    ![Снимок экрана с панелью мониторинга на портале Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  В меню **Обзор** найдите пункт **Intune**.![Снимок экрана меню "Обзор" с выделенным пунктом "Intune"](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Выберите **Intune** > **Управление мобильными приложениями Intune** > **Параметры**.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune"](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]

    > Чтобы закрепить колонку на **начальной** странице, можно использовать параметр **закрепить** в этой колонке. Щелкните значок закрепления в **колонке управления мобильными приложениями Intune**, чтобы закрепить ее на **начальной** странице.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune" и выделенным значком закрепления](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Снимок экрана: панель мониторинга с закрепленным элементом "Intune"](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## <a name="next-steps"></a>Дальнейшие действия
[Подготовка к настройке политик управления мобильными приложениями](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


