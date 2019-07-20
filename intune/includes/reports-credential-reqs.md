---
ms.openlocfilehash: 6ec8f8a613d3b0a0b17f2615de634e70fa282fd7
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2019
ms.locfileid: "68229170"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Требования к учетным данным Azure AD и Intune

Проверка подлинности и авторизация основаны на учетных данных Azure AD и управлении доступом на основе ролей (RBAC) Intune. Все глобальные администраторы и администраторы служб Intune для вашего клиента по умолчанию имеют доступ к хранилищу данных. Используйте роли Intune, чтобы предоставить доступ к **хранилищу данных Intune** другим пользователям.

Для доступа к хранилищу данных Intune (включая API) должны выполняться указанные ниже требования.

- Пользователь должен иметь разрешения одного из следующих уровней:
  - Глобальный администратор Azure AD
  - Администратор служб Intune
  - Пользователь с доступом к **хранилищу данных Intune** на основе ролей
  - Проверка подлинности без учета пользователя с [проверкой подлинности только приложения](../data-warehouse-app-only-auth.md) 
