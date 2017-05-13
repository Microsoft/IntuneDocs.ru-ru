---
title: "Подготовка к настройке политик защиты приложений для Windows 10 | Документация Майкрософт"
description: "Настройка поставщика управления мобильными приложениями (MAM) в Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 86a59771fc57971a626f71083e81cd4b7d858cfa
ms.contentlocale: ru-ru
ms.lasthandoff: 04/25/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Подготовка к настройке политик защиты приложений для Windows 10

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Прежде чем создавать политику защиты приложений Windows 10, необходимо включить управление мобильными приложениями (MAM) для Windows 10 с поставщиком MAM в Azure AD. Благодаря этой конфигурации можно определять состояние регистрации при создании новой политики Windows Information Protection (WIP) с помощью Intune.

> [!NOTE]
> Есть два состояния регистрации — MAM и управление мобильными устройствами (MDM).

## <a name="to-configure-the-mam-provider"></a>Настройка поставщика MAM

1.  Перейдите на [портал Azure](https://portal.azure.com/) и войдите в систему с помощью своих учетных данных Intune.

2.  В меню слева выберите **Azure Active Directory**.

    ![Конфигурация поставщика MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  Когда откроется колонка**Azure AD**, выберите **Мобильность (MDM и MAM)**, затем щелкните **Microsoft Intune**.

    ![Мобильность (MDM и MAM)](../media/AppManagement/mam-provider-sc-2.png)

4.  Когда откроется колонка настройки, сначала выберите **Восстановить URL-адреса MAM по умолчанию**, а затем настройте следующие параметры.

    а.  Область пользователей MAM: MAM можно использовать для защиты корпоративных данных определенной группы пользователей, использующих устройства Windows 10, или всех пользователей.

    b.  URL-адрес условий использования MAM: URL-адрес конечной точки условий использования службы MAM. Используется для отображения условий службы MAM конечным пользователям.

    в.  URL-адрес обнаружения MAM: это URL-адрес, который ищут устройства, если необходимо применить политики защиты приложений.

    г.  URL-адрес соответствия требованиям MAM:

5.  Настроив эти параметры, нажмите кнопку **Сохранить**.

## <a name="next-steps"></a>Дальнейшие действия

[Создание и развертывание политики защиты приложений Windows Information Protection (WIP) с помощью Intune](https://docs.microsoft.com/intune/deploy-use/create-windows-information-protection-policy-with-intune)

