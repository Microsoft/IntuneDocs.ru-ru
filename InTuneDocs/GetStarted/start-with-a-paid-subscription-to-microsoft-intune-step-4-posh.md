---
# required metadata

title: Управление лицензиями Intune с помощью PowerShell | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Управление лицензиями Intune с помощью PowerShell
Перед тем как пользователи смогут выполнять вход для использования службы Intune или регистрировать свои устройства для управления, вы должны назначить каждому пользователю лицензию на вашу подписку Intune, как описано в статье [Управление лицензиями Intune](start-with-a-paid-subscription-to-microsoft-intune-step-4.md). Однако организации, использующие Microsoft Enterprise Mobility Suite (EMS), могут иметь пользователей, которым в пакете EMS нужны только службы Azure Active Directory Premium или Intune. Можно назначить одну службу или подмножество служб с помощью [командлетов PowerShell для Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx). 

Чтобы выборочно назначить лицензии пользователя для служб EMS, откройте PowerShell с правами администратора на компьютере с установленным [модулем Azure Active Directory для Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). PowerShell можно установить на локальном компьютере или на сервере ADFS.

Необходимо создать новое определение SKU для лицензии, которое применяется только к нужным планам обслуживания. Чтобы сделать это, отключите планы, которые не нужно применять. Например, можно создать определение SKU лицензии, не назначающее лицензию Intune. Чтобы просмотреть список доступных служб, введите:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Можно выполнить следующую команду, чтобы исключить план обслуживания Intune. Вы можете воспользоваться тем же методом для работы со всей группой безопасности или применить более детализированные фильтры. 

**Пример 1** Создайте нового пользователя в командной строке и назначьте лицензию EMS, не включая ту ее часть, которая относится к Intune:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Проверьте:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Пример 2** Отключите связанную с Intune часть лицензии EMS для пользователя, которому уже назначена лицензия:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Проверьте:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Дальнейшие действия
Поздравляем! Вы завершили шаг 4 *краткого руководства по Intune*.
>[!div class="step-by-step"]

>[&larr; **Синхронизация пользователей с Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Организация пользователей и устройств** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=Jun16_HO3-->


