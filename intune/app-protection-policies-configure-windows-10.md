---
title: Настройка политик защиты приложений для Windows 10
titleSuffix: Microsoft Intune
description: В этом разделе описывается настройка политик защиты приложений (APP) для устройств с Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f7bff9fa319f8df1abc4622237d1f9b98b9a685
ms.sourcegitcommit: 617bd653c34c1e6a4e2ad61811c5912f8dab775c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2019
ms.locfileid: "59570719"
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
