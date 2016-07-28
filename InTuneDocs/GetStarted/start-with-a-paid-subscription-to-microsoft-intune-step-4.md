---
title: "Управление лицензиями Intune | Microsoft Intune"
description: "Объясняется, как назначать лицензии пользователям для подписки Intune."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: c86cbb42554d388c943faa37a7c59b376fdaf287


---

# Управление лицензиями Intune
Чтобы пользователи могли войти в систему и получить доступ к службам Intune или зарегистрировать свои устройства для управления, нужно назначить каждому пользователю лицензию на вашу подписку Intune на [портале Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). После назначения лицензии имена пользователей будут отображаться в консоли администрирования Intune. После этого каждый пользователь сможет зарегистрировать до пяти устройств.

Организации, использующие Microsoft Enterprise Mobility Suite (EMS), могут иметь пользователей, которым в пакете EMS нужны только службы Azure Active Directory Premium или Intune. С помощью [командлетов PowerShell для Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx) можно назначить одну службу или подмножество служб. Дополнительные сведения см. в разделе [Управление лицензиями Intune с помощью PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## Назначение лицензий Intune
Когда учетные записи синхронизируются из локальной службы Active Directory или вручную добавляются в подписку облачных служб на [портале Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), лицензия Intune не назначается им автоматически. Вы как администратор клиента Intune должны изменить учетную запись пользователя на портале Office 365, назначив лицензию этому пользователю.

Если подписка использует Azure AD совместно с другими облачными службами в вашей подписке, вы получаете доступ к пользователям, которые были добавлены для этих служб. У этих пользователей не будет лицензии на [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] до тех пор, пока вы не назначите ее каждому из них.

> [!TIP]
> Если параметр назначения или отзыва лицензии [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] недоступен, ваша подписка должна включать варианты корпоративного лицензирования, например доступные при использовании [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Дополнительные сведения о назначении или отзыве лицензий см. в документации к вариантам лицензирования.

## Назначение лицензии пользователя Intune

Используйте [портал Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), чтобы вручную добавить облачных пользователей и назначить лицензии облачным учетным записям пользователей, а также учетным записям, синхронизированным из локальной службы Active Directory в Azure AD.

1.  Войдите на [портал Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) с использованием учетных данных администратора клиента и последовательно выберите пункты **Люди**  >  **Все пользователи**.

2.  Выберите учетную запись, которой требуется назначить лицензию пользователя Intune, а затем щелкните **Microsoft Intune** (автономный) или **Enterprise Mobility Suite**.

3.  Теперь учетная запись пользователя имеет необходимые разрешения на использование службы и регистрацию устройств для управления.

### Использование PowerShell для избирательного управления пользовательскими лицензиями EMS
Организации, использующие Microsoft Enterprise Mobility Suite (EMS), могут иметь пользователей, которым в пакете EMS нужны только службы Azure Active Directory Premium или Intune. С помощью [командлетов PowerShell для Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx) можно назначить одну службу или подмножество служб. 

Чтобы выборочно назначить лицензии пользователя для служб EMS, откройте PowerShell с правами администратора на компьютере с установленным [модулем Azure Active Directory для Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). PowerShell можно установить на локальном компьютере или на сервере ADFS.

Необходимо создать новое определение SKU для лицензии, которое применяется только к нужным планам обслуживания. Чтобы сделать это, отключите планы, которые не нужно применять. Например, можно создать определение SKU лицензии, не назначающее лицензию Intune. Чтобы просмотреть список доступных служб, введите:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Можно выполнить следующую команду, чтобы исключить план обслуживания Intune. Вы можете воспользоваться тем же методом для работы со всей группой безопасности или применить более детализированные фильтры. 

**Пример 1**. Создайте нового пользователя в командной строке и назначьте ему лицензию EMS, не включая ту ее часть, которая относится к Intune:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Проверьте:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Пример 2**. Отключите связанную с Intune часть лицензии EMS для пользователя, которому уже назначена лицензия:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Проверьте:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Дальнейшие действия
Поздравляем! Вы завершили шаг 4 *краткого руководства по началу работы с Intune*.
>[!div class="step-by-step"]

>[&larr; **Синхронизация пользователей с Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Организация пользователей и устройств** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Jul16_HO3-->


