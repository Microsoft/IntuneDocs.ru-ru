---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71830511"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Требования к учетным данным Azure AD и Intune

Проверка подлинности и авторизация основаны на учетных данных Azure AD и управлении доступом на основе ролей (RBAC) Intune. Все глобальные администраторы и администраторы служб Intune для вашего клиента по умолчанию имеют доступ к хранилищу данных. Используйте роли Intune, чтобы предоставить доступ к **хранилищу данных Intune** другим пользователям.

Для доступа к хранилищу данных Intune (включая API) должны выполняться указанные ниже требования.

- Пользователь должен иметь разрешения одного из следующих уровней:
  - Глобальный администратор Azure AD
  - Администратор служб Intune
  - Пользователь с доступом к **хранилищу данных Intune** на основе ролей
  - Проверка подлинности без учета пользователя с [проверкой подлинности только приложения](../developer/data-warehouse-app-only-auth.md) 
