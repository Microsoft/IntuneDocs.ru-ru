---
title: Разрешение конфликтов GPO и политик Intune
titlesuffix: Microsoft Intune
description: Сведения об устранении конфликтов между групповой политикой и политиками конфигурации Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7024d2c5f9e6b5ac3f844a2f974d2a1d5a0444b0
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57459940"
---
# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a>Разрешение конфликтов объектов групповой политики (GPO) и политик Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Intune использует политики, упрощающие работу с настройками на компьютерах Windows. Например, с помощью политики можно управлять настройками брандмауэра Windows на компьютерах. Многие настройки Intune совпадают с настройками, задаваемыми с помощью групповой политики Windows. Но иногда между двумя методами могут возникать конфликты.

При возникновении конфликта групповая политика уровня домена имеет более высокий приоритет по сравнению с политикой Intune, за исключением той ситуации, когда компьютер не может подключиться к домену. В этом случае к клиентскому компьютеру применяется политика Intune.

## <a name="what-to-do-if-you-are-using-group-policy"></a>Действия, выполняемые в случае использования групповой политики
Убедитесь, что применяемые политики не находятся под управлением групповой политики. Существует несколько способов предотвращения конфликтов.

-   Перемещение компьютеров в подразделение Active Directory, к которому не применены параметры групповой политики, до установки клиента Intune. Блокировка наследования групповой политики для подразделений с компьютерами, зарегистрированными в Intune, к которым не нужно применять параметры групповой политики.

-   Использование фильтра групп безопасности для применения объектов групповой политики только к компьютерам, не находящимся под управлением Intune.

-   Отключение или удаление объектов групповой политики, которые конфликтуют с политиками Intune.

Дополнительные сведения об Active Directory и групповой политике Windows см. в документации к Windows Server.

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a>Фильтрация существующих GPO для предотвращения конфликтов с политикой Intune
Определив объекты групповой политики с настройками, которые конфликтуют с политиками Intune, можно сделать так, чтобы эти объекты применялись только к компьютерам, не находящимся под управлением Intune, с помощью фильтров групп безопасности.

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


Вы можете применять объекты групповой политики только к группам безопасности, указанным в разделе **Фильтры безопасности** консоли управления групповыми политиками для конкретного объекта. По умолчанию объекты групповой политики применяются к пользователям, входящим в группу *Прошедшие проверку*.

-   В оснастке **Пользователи и компьютеры Active Directory** создайте новую группу безопасности, содержащую компьютеры и учетные записи пользователей, которыми Intune не следует управлять. Группу можно назвать *Отсутствующие в Microsoft Intune*.

-   На консоли управления групповыми политиками, на вкладке **Делегирование** для выбранного объекта групповой политики, щелкните правой кнопкой мыши новую группу безопасности, чтобы делегировать входящим в нее пользователям и компьютерам соответствующие разрешения **Чтение** и **Применить групповую политику**. (разрешения**Применить групповую политику** доступны в диалоговом окне **Дополнительно** ).

-   Затем примените фильтр новой группы безопасности к выбранному объекту групповой политики и удалите фильтр по умолчанию, **Прошедшие проверку**.

Новая группа безопасности должна поддерживаться на основе соглашения о регистрации изменений в службе Intune.

### <a name="see-also"></a>См. также
[Управление ПК под управлением Windows с помощью Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
