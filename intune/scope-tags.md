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
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9441f1c69e3d445d6174521ad2c9ef5c7a6db2be
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835543"
---
# <a name="use-scope-tags-to-filter-policies"></a>Используйте теги области для фильтрации политик

Теги области позволяют фильтровать политики с помощью настраиваемых тегов, самостоятельно создаваемых вами. Можно применить теги области для ролей и приложений.

Например, создайте тег области "Инженерный отдел" и назначьте его профилям конфигурации, связанным с инженерным отделом. Назначьте тот же тег роли "Инженеры-администраторы". Они будут видеть только политики с тегом "Инженерный отдел".

## <a name="to-create-a-scope-tag"></a>Создание тега области

Выберите **Роли** > **Область (теги)** > **Создать**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Добавление тега области в профиль конфигурации

Выберите пункты **Конфигурация устройств** > **Профили** > выберите профиль > **Свойства** > **Область (теги)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Назначение тега области для роли

Выберите **Роли** > **Все роли** > **Диспетчер политик и профилей** > **Назначения**  >  **Область (теги)**.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Назначение тега области для приложения

Выберите пункты **Клиентские приложения** > **Приложения** > выберите нужное приложение > **Свойства** > **Область (теги)**  >  **Добавить** > выберите теги > **Выбрать** > **ОК** > **Сохранить**.


## <a name="next-steps"></a>Дальнейшие шаги

Управление вашими [ролями](role-based-access-control.md) и [профилями](device-profile-assign.md).

