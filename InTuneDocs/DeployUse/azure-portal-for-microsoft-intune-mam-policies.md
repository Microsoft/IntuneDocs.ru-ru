---
title: "Портал Azure для политик управления мобильными приложениями | Microsoft Intune"
description: "Создание политик управления мобильными приложениями на портале Azure. Создаваемые на портале политики могут применяться к устройствам с регистрацией в Intune или без нее."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Портал Azure для политик управления мобильными приложениями Microsoft Intune
## Использование портала Azure
Портал Azure позволяет создавать политики управления мобильными приложениями (MAM) и управлять ими.

Портал Azure поддерживает создание политик MAM для следующих приложений:
- приложения, работающие на устройствах, **зарегистрированных в службе Intune и управляемых ей**;
- приложения, работающие на устройствах, которые **не зарегистрированы** в каком-либо решении для управления мобильными устройствами;
- приложения, работающие на устройствах, которые **зарегистрированы в решении для управления мобильными устройствами стороннего производителя**.

>[!IMPORTANT]

> При использовании консоли администрирования Intune для управления устройствами можно создать политику MAM, поддерживающую приложения на устройствах, зарегистрированных в Intune, с помощью [этой консоли](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> В консоли администрирования Intune могут отображаться не все параметры политики MAM. Портал Azure — это новая консоль администрирования для создания политик MAM. При создании политик MAM в консоли администрирования Intune и на портале Azure политики, созданные на портале Azure, применяются к приложениям и развертываются для пользователей.

## Вход на портал Azure и настройка начальной страницы

1.  Перейдите на [портал Azure](https://portal.azure.com) и выполните вход с помощью своих учетных данных [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Снимок экрана со страницей входа на портал Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  После входа вы увидите страницу **панели мониторинга**. Страница **панели мониторинга** является настраиваемой.

    ![Снимок экрана с панелью мониторинга на портале Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  В меню **Обзор** найдите пункт **Intune**.![Снимок экрана меню "Обзор" с выделенным пунктом "Intune".](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Выберите **Intune** > **Управление мобильными приложениями Intune** > **Параметры**.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune"](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Чтобы закрепить колонку **управления мобильными приложениями Intune** на **начальной** странице, щелкните значок закрепления в ней.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune" и выделенным значком закрепления](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Снимок экрана: панель мониторинга с закрепленным элементом "Intune"](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Дальнейшие действия
[Подготовка к настройке политик управления мобильными приложениями](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


