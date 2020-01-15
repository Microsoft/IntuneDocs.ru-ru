---
title: Назначение роли пользователю Intune
description: Узнайте, как назначить встроенную или пользовательскую роль пользователю в Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c82805bf70259d43d738644e5663b93533bcb56a
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207168"
---
# <a name="assign-a-role-to-an-intune-user"></a>Назначение роли пользователю Intune

Вы можете назначить [встроенную](role-based-access-control.md#built-in-roles) или [пользовательскую](create-custom-role.md) роль пользователю Intune.

Для создания, изменения и назначения ролей учетная запись должна иметь одно из следующих разрешений в Azure AD:
- **Глобальный администратор**
- **Администратор службы Intune**

1. В [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) щелкните **Роли** > **Все роли**.

2. В колонке **"Все роли" в разделе ролей Intune** выберите встроенную роль, которую требуется назначить.

3. В колонке **Обзор** <*имя_роли*> выберите **Управление** > **Назначения**.

4. В колонке настраиваемой роли выберите **Назначить**.

5. В колонке **Назначения ролей** введите **имя назначения** и необязательное **описание назначения**.

6. Для параметра **Участники (группы)** выберите группу, содержащую пользователя, которому необходимо предоставить разрешения.

7. Для параметра **Область (группы)** выберите группу, содержащую пользователей или устройства, которыми сможет управлять вышеуказанный участник.

8. Для параметра **Область (теги)** выберите теги областей, в которых будет применяться это назначение роли.

9. По окончании нажмите кнопку **ОК**. Новое назначение отобразится в списке назначений.


## <a name="next-steps"></a>Дальнейшие шаги
- [Дополнительные сведения об управлении доступом на основе ролей в Intune](role-based-access-control.md)
- [Создание пользовательской роли](create-custom-role.md)
