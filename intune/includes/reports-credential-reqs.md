---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511348"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Требования к учетным данным Azure AD и Intune

Проверка подлинности и авторизация основаны на учетных данных Azure AD и управлении доступом на основе ролей (RBAC) Intune. Все глобальные администраторы и администраторы служб Intune для вашего клиента по умолчанию имеют доступ к хранилищу данных. Используйте роли Intune, чтобы предоставить доступ к **хранилищу данных Intune** другим пользователям.

Для доступа к хранилищу данных Intune (включая API) должны выполняться указанные ниже требования.

  -  Пользователь должен иметь разрешения одного из следующих уровней:
      -  Глобальный администратор Azure AD
      -  Администратор служб Intune
      -  Пользователь с доступом к **хранилищу данных Intune** на основе ролей
      -  Проверка подлинности без учета пользователя с [проверкой подлинности только приложения](../data-warehouse-app-only-auth.md) 
