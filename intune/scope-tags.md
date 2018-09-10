---
title: Фильтрация политик по тегам области в Microsoft Intune — Azure | Документы Майкрософт
description: Используйте теги области для фильтрации профилей конфигурации по определенным ролям.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329433"
---
# <a name="use-scope-tags-to-filter-policies"></a>Используйте теги области для фильтрации политик

Теги области позволяют фильтровать политики с помощью настраиваемых тегов, самостоятельно создаваемых вами.

Например, создайте тег области "Инженерный отдел" и назначьте его профилям конфигурации, связанным с инженерным отделом. Назначьте тот же тег роли "Инженеры-администраторы". Они будут видеть только политики с тегом "Инженерный отдел".

## <a name="to-create-a-scope-tag"></a>Создание тега области

Выберите **Роли** > **Область (теги)** > **Создать**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Добавление тега области в профиль конфигурации

Выберите пункты **Конфигурация устройств** > **Профили** > выберите профиль > **Свойства** > **Область (теги)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Назначение тега области для роли

Выберите **Роли** > **Все роли** > **Диспетчер политик и профилей** > **Назначения**  >  **Область (теги)**.

## <a name="next-steps"></a>Дальнейшие шаги

Управление вашими [ролями](role-based-access-control.md) и [профилями](device-profile-assign.md).

