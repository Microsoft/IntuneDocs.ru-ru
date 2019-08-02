---
title: Шифрование устройств в Microsoft Intune с помощью методов шифрования, поддерживаемых платформами
titleSuffix: Microsoft Intune
description: Шифрование устройств с помощью встроенных методов шифрования, таких как BitLocker или FileVault, и управление ключами восстановления для этих зашифрованных устройств с помощью портала Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3f37b9b0bc16572cc86cbf79be616c7f395aa784
ms.sourcegitcommit: 2bce5e43956b6a5244a518caa618f97f93b4f727
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68467469"
---
# <a name="use-device-encryption-with-intune"></a>Использование шифрования устройств в Intune  

Используйте Intune для управления встроенными дисками или шифрованием дисков для защиты данных на устройствах.  

Настройте шифрование дисков в составе профиля конфигурации устройства для Endpoint Protection. Intune поддерживает следующие платформы и технологии шифрования:  
- macOS: FileVault   
- Windows 10 и более поздних версий: BitLocker  

Intune также предоставляет встроенный [отчет](encryption-monitor.md) о шифровании, который содержит подробные сведения о состоянии шифрования на всех управляемых устройствах.  

## <a name="filevault-encryption-for-macos"></a>Шифрование FileVault для macOS  

Используйте Intune для настройки шифрования дисков FileVault на устройствах под управлением macOS. Затем используйте отчет о шифровании Intune, чтобы просмотреть сведения о шифровании этих устройств и управлять ключами восстановления для устройств, зашифрованных с помощью FileVault.  

FileVault — это программа шифрования всего диска, входящая в состав macOS. Вы можете использовать Intune для настройки FileVault на устройствах под управлением **macOS 10.13 или более поздней версии**.  

Чтобы настроить FileVault, создайте [профиль](device-profile-create.md) конфигурации устройства Endpoint Protection для платформы macOS. Параметры FileVault — это одна из категорий доступных параметров для macOS в Endpoint Protection.  

После создания политики шифрования устройств с помощью FileVault она применяется к устройствам в два этапа. Во-первых, устройство готовится к тому, что Intune будет разрешено получить и сохранить ключ восстановления. Название такого поведения — эскроу. Когда ключ попал в эскроу, можно начинать шифрование диска.

![Параметры FileVault](./media/encrypt-devices/filevault-settings.png)

Дополнительные сведения о параметре FileVault, которым можно управлять с помощью Intune, см. в разделе [FileVault](endpoint-protection-macos.md#filevault) статьи из раздела Intune о параметрах Endpoint Protection для macOS.  

### <a name="how-to-configure-macos-filevault"></a>Настройка FileVault в macOS 

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) и перейдите в раздел **Конфигурация устройства** > **Профили** > **Создать профиль**.  

2. Настройте следующие параметры:  

   - Платформа: macOS  
   - Тип профиля: Защита конечных точек  

3. Выберите **Параметры** > **FileVault**.  

4. В разделе *FileVault* выберите **Включить**.  

5. В качестве *типа ключа восстановления* поддерживается только **личный ключ**.  

   Рекомендуется добавить сообщение, помогающее конечным пользователям получить ключ восстановления для своего устройства. Эти сведения могут оказаться полезными для конечных пользователей, если вы используете параметр для смены ключа восстановления, который может время от времени автоматически создавать новый ключ восстановления для устройства.  

   Пример. Чтобы получить потерянный или недавно измененный ключ восстановления, войдите на веб-сайт корпоративного портала Intune с любого устройства. На портале перейдите на вкладку *Устройства* и выберите устройство с включенным FileVault, а затем выберите команду *Получить ключ восстановления*. Отобразится текущий ключ восстановления.  

6. Настройте остальные [параметры FileVault](endpoint-protection-macos.md#filevault) в соответствии с бизнес-потребностями, а затем нажмите кнопку **ОК**.  

7. Завершите настройку дополнительных параметров, а затем сохраните профиль.  

### <a name="manage-filevault"></a>Управление FileVault  

После того как Intune зашифрует устройство под управлением macOS с помощью FileVault, вы можете просматривать ключи восстановления FileVault и управлять ими при просмотре [отчета о шифровании](encryption-monitor.md) Intune.  

## <a name="bitlocker-encryption-for-windows-10"></a>Шифрование BitLocker для Windows 10  

Используйте Intune для настройки шифрования дисков BitLocker на устройствах под управлением Windows 10. Затем используйте отчет о шифровании Intune, чтобы просмотреть сведения о шифровании для этих устройств. Вы также можете получить доступ к важной информации для BitLocker с ваших устройств, которую можно найти в Azure Active Directory (Azure AD).  

BitLocker доступен на устройствах под управлением **Windows 10 или более поздней версии**.  

Чтобы настроить BitLocker, создайте [профиль конфигурации устройства](device-profile-create.md) Endpoint Protection для платформы Windows 10 или более поздней версии. Параметры BitLocker находятся в категории параметров шифрования Windows для Endpoint Protection в Windows 10.    

![Параметры BitLocker](./media/encrypt-devices/bitlocker-settings.png) 

### <a name="how-to-configure-windows-10-bitlocker"></a>Настройка BitLocker в Windows 10  

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) и перейдите в раздел "Конфигурация устройства" > "Профили" > "Создать профиль".  

2. Настройте следующие параметры:  
   - Платформа: Windows 10 и более поздней версии  
   - Тип профиля: Защита конечных точек  

3. Выберите **Параметры** > **Шифрование Windows**.

4. Настройте параметры BitLocker в соответствии с потребностями бизнеса, а затем нажмите кнопку **ОК**.  

5. Завершите настройку дополнительных параметров, а затем сохраните профиль.  

### <a name="manage-bitlocker"></a>Управление BitLocker  

После того как Intune зашифрует устройство под управлением Windows 10 с помощью BitLocker, вы можете просматривать ключи восстановления BitLocker и управлять ими при просмотре [отчета о шифровании](encryption-monitor.md) Intune.  

## <a name="next-steps"></a>Дальнейшие шаги  

Создание [политики соответствия устройств](compliance-policy-create-windows.md).  

Используйте отчет о шифровании для управления:  
- [ключами восстановления BitLocker](encryption-monitor.md#bitlocker-recovery-keys);
- [ключами восстановления FileVault](encryption-monitor.md#filevault-recovery-keys).

Изучите параметры шифрования, которые можно настроить с помощью Intune для:  
- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)  
- [FileVault](endpoint-protection-macos.md#filevault)  
 
 
