---
title: "Подготовка к настройке политик защиты приложений для Windows 10"
titlesuffix: Azure portal
description: "Настройка поставщика управления мобильными приложениями (MAM) в Azure AD"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 52b273532935184918e65d25a37ca3d03e76680c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Подготовка к настройке политик защиты приложений для Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Прежде чем создавать политику защиты приложений Windows 10, необходимо включить управление мобильными приложениями (MAM) для Windows 10 с поставщиком MAM в Azure AD. Благодаря этой конфигурации можно определять состояние регистрации при создании новой политики Windows Information Protection (WIP) с помощью Intune.

> [!NOTE]
> Есть два состояния регистрации — MAM и управление мобильными устройствами (MDM).

## <a name="to-configure-the-mam-provider"></a>Настройка поставщика MAM

1.  Перейдите на [портал Azure](https://portal.azure.com/) и войдите в систему с помощью своих учетных данных Intune.

2.  В меню слева выберите **Azure Active Directory**.

    ![Конфигурация поставщика MAM](./media/mam-provider-sc-1.png)

3.  Когда откроется колонка**Azure AD**, выберите **Мобильность (MDM и MAM)**, затем щелкните **Microsoft Intune**.

    ![Мобильность (MDM и MAM)](./media/mam-provider-sc-1.png)

4.  Когда откроется колонка настройки, сначала выберите **Восстановить URL-адреса MAM по умолчанию**, а затем настройте следующие параметры.

    а.  Область пользователей MAM: MAM можно использовать для защиты корпоративных данных определенной группы пользователей, использующих устройства Windows 10, или всех пользователей.

    b.  URL-адрес условий использования MAM: URL-адрес конечной точки условий использования службы MAM. Используется для отображения условий службы MAM конечным пользователям.

    в.  URL-адрес обнаружения MAM: это URL-адрес, который ищут устройства, если необходимо применить политики защиты приложений.

    г.  URL-адрес соответствия требованиям MAM:

5.  Настроив эти параметры, нажмите кнопку **Сохранить**.

## <a name="next-steps"></a>Дальнейшие действия

[Создание и развертывание политики защиты приложений Windows Information Protection (WIP) с помощью Intune](windows-information-protection-policy-create.md)
