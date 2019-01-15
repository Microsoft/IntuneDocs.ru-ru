---
title: Настройка политик защиты приложений для Windows 10
titleSuffix: Microsoft Intune
description: Настройте поставщик управления мобильными приложениями (MAM) в Azure AD.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 189afded0674958720234df86ed5d09c5cb8193d
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297343"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Подготовка к настройке политик защиты приложений для Windows 10 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Включите управление мобильными приложениями (MAM) для Windows 10, указав поставщик MAM в Azure AD. После этого можно определять состояние регистрации при создании новой политики Windows Information Protection (WIP) с помощью Intune. Есть два состояния регистрации — MAM и управление мобильными устройствами (MDM).

## <a name="to-configure-the-mam-provider"></a>Настройка поставщика MAM

1. Войдите на портал Azure и выберите **Azure Active Directory**.

2. Выберите **Мобильность (MDM и MAM)** в группе **Управление**.

3. Выберите **Microsoft Intune**.

4. Настройте параметры в группе **Восстановить URL-адреса MAM по умолчанию**  в колонке **Настройка**.

   **Область пользователя MAM**  
   Используйте автоматическую регистрацию MAM для управления корпоративными данными на устройствах Windows сотрудников вашей компании. Автоматическая регистрация MAM будет настроена для сценариев с использованием собственного устройства.<ul><li>**Нет**<br>Укажите, если никто из пользователей не может зарегистрироваться в MAM.</li><li>**Некоторые**<br>Выберите группы Azure AD, которые содержат пользователей для регистрации в MAM.</li><li>**Все**<br>Укажите, могут ли все пользователи зарегистрироваться в MAM.</li></ul>

   **URL-адрес условий использования MAM**  
   URL-адрес условий использования MAM не поддерживается в Microsoft Intune. Для применения политик защиты это поле ввода следует оставить пустым.

   **URL-адрес обнаружения MAM**  
   URL-адрес конечной точки регистрации службы MAM. Конечная точка регистрации используется для регистрации устройств для управления с помощью службы MAM.

   **URL-адрес соответствия требованиям MAM**  
   URL-адрес соответствия требованиям MAM не поддерживается в Microsoft Intune. Для применения политик защиты это поле ввода следует оставить пустым. 

5.  Нажмите кнопку **Сохранить**.

## <a name="next-steps"></a>Дальнейшие шаги

[Создание и развертывание политики защиты приложений Windows Information Protection (WIP) с помощью Intune](windows-information-protection-policy-create.md)
