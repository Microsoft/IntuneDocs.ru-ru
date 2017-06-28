---
title: "Портал Azure для политик управления мобильными приложениями"
description: "Создание политик управления мобильными приложениями на портале Azure. Создаваемые на портале политики могут применяться к устройствам с регистрацией в Intune или без нее."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 00328885d7fb5e75ffe894326591c0225f4b07ab
ms.contentlocale: ru-ru
ms.lasthandoff: 06/08/2017


---

# <a name="azure-portal-for-intune-app-protection-policies"></a>Портал Azure для политик защиты приложений Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

На портале Azure можно создавать политики защиты приложений и управлять ими для следующих приложений:

- приложения, работающие на устройствах, **зарегистрированных в службе Intune и управляемых ею**;

- приложения, работающие на устройствах, которые **не зарегистрированы** в каком-либо решении для управления мобильными устройствами;
- приложения, работающие на устройствах, которые **зарегистрированы в решении для управления мобильными устройствами стороннего производителя**.

>[!IMPORTANT]
> Портал Azure — это новая консоль администрирования для создания политик защиты приложений. Вы можете также создать политику защиты приложений, которая поддерживает приложения для устройств, зарегистрированных в Intune, при помощи [консоли администрирования Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) для сценариев MDM.

> В консоли администрирования Intune могут отображаться не все доступные параметры политики защиты приложений. Кроме того, при создании политик защиты приложений как в консоли администрирования Intune, так и на портале Azure, политики, созданные на портале Azure, имеют приоритет над созданными в консоли администрирования Intune. В этом случае политики защиты приложений с портала Azure будут применены к приложениям и развернуты пользователям.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Вход на портал Azure и настройка начальной страницы

1.  Перейдите на [портал Azure](https://portal.azure.com) и войдите в систему с помощью своих учетных данных Intune.

    ![Снимок экрана со страницей входа на портал Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  После успешного входа вы увидите **панель мониторинга**. Страница **панели мониторинга** является настраиваемой.

    ![Снимок экрана с панелью мониторинга на портале Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Выберите пункт **Другие службы** в меню слева и введите **Intune** в текстовом поле фильтра.

    ![Снимок экрана меню "Обзор" с выделенным пунктом "Intune"](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Выберите пункты **Защита приложений Intune** > **Управление мобильными приложениями Intune** > **Все параметры**.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune"](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Необязательно): чтобы закрепить колонку на **начальной** странице, выберите **закрепить**. Щелкните значок закрепления в **колонке управления мобильными приложениями Intune**, чтобы закрепить ее на **начальной** странице.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune" и выделенным значком закрепления](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Снимок экрана: панель мониторинга с закрепленным элементом "Intune"](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Дальнейшие шаги
[Подготовка к настройке политик защиты приложений](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

