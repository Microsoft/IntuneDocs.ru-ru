---
title: Портал Azure для политик управления мобильными приложениями
description: Создание политик управления мобильными приложениями на портале Azure. Создаваемые на портале политики могут применяться к устройствам с регистрацией в Intune или без нее.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 10/22/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e3e71f52979f6285a14c5cc4fe26ea912cb3a42
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="azure-portal-for-intune-app-protection-policies"></a>Портал Azure для политик защиты приложений Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

На портале Azure можно создавать политики защиты приложений и управлять ими для следующих приложений:

- приложения, работающие на устройствах, **зарегистрированных в службе Intune и управляемых ею**;

- приложения, работающие на устройствах, которые **не зарегистрированы** в каком-либо решении для управления мобильными устройствами;
- приложения, работающие на устройствах, которые **зарегистрированы в решении для управления мобильными устройствами стороннего производителя**.

> [!IMPORTANT]
> Портал Azure — это новая консоль администрирования для создания политик защиты приложений. Вы можете также создать политику защиты приложений, которая поддерживает приложения для устройств, зарегистрированных в Intune, при помощи [консоли администрирования Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) для сценариев MDM.
> 
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
