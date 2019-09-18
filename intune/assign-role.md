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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0539e4d12173ba2c7ba8d3af3364daf69ddbbf34
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071534"
---
# <a name="assign-a-role-to-an-intune-user"></a>Назначение роли пользователю Intune

Вы можете назначить [встроенную](role-based-access-control.md#built-in-roles) или [пользовательскую](create-custom-role.md) роль пользователю Intune.

Для создания, изменения и назначения ролей учетная запись должна иметь одно из следующих разрешений в Azure AD:
- **Глобальный администратор**
- **Администратор службы Intune**

Полный список разрешений для каждой встроенной роли см. в [таблице RBAC Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. Войдите на [портал Azure](https://portal.azure.com).

2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.

3. В колонке **Intune** последовательно выберите **Роли** > **Все роли**.

4. В колонке **"Все роли" в разделе ролей Intune** выберите встроенную роль, которую требуется назначить.

5. В колонке **Обзор** <*имя_роли*> выберите **Управление** > **Назначения**.

6. В колонке настраиваемой роли выберите **Назначить**.

7. В колонке **Назначения ролей** введите **имя назначения** и необязательное **описание назначения**.

8. Для параметра **Участники (группы)** выберите группу, содержащую пользователя, которому необходимо предоставить разрешения.

9. Для параметра **Область (группы)** выберите группу, содержащую пользователей или устройства, которыми сможет управлять вышеуказанный участник.

10. Для параметра **Область (теги)** выберите теги областей, в которых будет применяться это назначение роли.

11. По окончании нажмите кнопку **ОК**. Новое назначение отобразится в списке назначений.


## <a name="next-steps"></a>Дальнейшие шаги
- [Дополнительные сведения об управлении доступом на основе ролей в Intune](role-based-access-control.md)
- [Создание пользовательской роли](create-custom-role.md)
