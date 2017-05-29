---
title: "Подготовка к настройке политик защиты приложений для Windows 10 | Документация Майкрософт"
titleSuffix: Intune Azure preview
description: "Настройка поставщика управления мобильными приложениями (MAM) в Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e179f72e4cd99a8cd1bdc017e9965f7d1eb608bf
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Подготовка к настройке политик защиты приложений для Windows 10

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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

[Создание и развертывание политики защиты приложений Windows Information Protection (WIP) с помощью Intune](https://docs.microsoft.comwindows-information-protection-policy-create.md)

