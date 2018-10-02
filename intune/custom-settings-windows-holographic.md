---
title: Настраиваемые параметры устройств для Windows Holographic for Business в Microsoft Intune в Azure | Документы Майкрософт
description: Создайте настраиваемый профиль для использования параметров OMA-URI для устройств под управлением Windows Holographic for Business в Microsoft Intune. Можно задать параметры AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates и ApplicationLaunchRestrictions политики поставщика CSP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.topic: article
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b8ba5078d304c0e9d6b10e4efb868642323c901c
ms.sourcegitcommit: 2795255e89cbe97d0b17383d446cca57c7335016
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47403584"
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Настраиваемые параметры для устройств с Windows Holographic for Business в Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 **Пользовательский** профиль Microsoft Intune для Windows Holographic for Business позволяет развертывать параметры универсального кода ресурса Open Mobile Alliance (OMA-URI) для управления функциями устройств. Windows Holographic for Business открывает доступ ко множеству параметров поставщиков служб конфигурации (CSP). Обзор CSP см. в разделе [Введение в поставщики служб конфигурации (CSP) для ИТ-специалистов](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Также см. [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Если вам нужен какой-то конкретный параметр, не забывайте, что [профиль ограничения устройств с Windows Holographic for Business](device-restrictions-windows-holographic.md) содержит множество встроенных параметров и не требует указывать ваши собственные значения.

## <a name="create-the-custom-oma-uri-profile"></a>Создание настраиваемого профиля OMA-URI

1. Для начала выполните инструкции из статьи о [настройке пользовательских параметров устройств в Microsoft Intune](custom-settings-configure.md).
2. В колонке **Создать профиль** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Настраиваемые параметры OMA URI** выберите **Добавить**, чтобы добавить новое значение. Можно также щелкнуть **Экспорт**, чтобы создать список всех настроенных значений в файле с разделителями-запятыми (CSV).
4. Для каждого добавляемого параметра OMA-URI укажите следующее:
  - **Имя параметра** — введите уникальное название параметра OMA-URI, чтобы его было проще найти в списке параметров.
  - **Описание параметра** — введите необязательное описание параметра.
  - **Тип данных** — выберите одно из значений:
    - **Строка**
    - **Строка (XML)**
    - **Дата и время**
    - **Целое число**
    - **Число с плавающей запятой**
    - **Логическое значение**
  - **OMA-URI (с учетом регистра)** — укажите OMA-URI, для которого необходимо указать параметр.
  - **Значение** — укажите значение, которое нужно сопоставить с указанным OMA-URI.
5. По завершении вернитесь в колонку **Создать профиль** и щелкните **Создать**. Созданный профиль отобразится в списке профилей.

## <a name="recommended-custom-settings"></a>Рекомендованные пользовательские параметры

Следующие параметры также применимы к устройствам с Windows Holographic for Business.

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Целое число<br/>0 — запрещено<br/>1 — разрешено (по умолчанию)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Целое число<br/>0 — обновление службы запрещено <br/>1 — обновление службы разрешено (по умолчанию).|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Целое число<br/>0 — запрещено<br/>1 — разрешено (по умолчанию)|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Целое число<br/>0 — не настроено. Устройство устанавливает все доступные обновления.<br/>1 — устройство устанавливает только обновления, которые применимы и при этом находятся в списке разрешенных обновлений. Установите значение 1 для этой политики, если отдел ИТ хочет контролировать развертывание обновлений на устройствах, например, когда требуется предварительное тестирование.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Целое число от 0 до 23, где 0 соответствует 00:00, а 23 — 23:00<br/>Значение по умолчанию — 3.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Строка<br/>URL-адрес — устройство будет проверять наличие обновлений на сервере WSUS по указанному URL-адресу.<br/>Не настроено — устройство будет проверять наличие обновлений в центре обновления Майкрософт.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Важно**<br/>Необходимо прочитать и принять лицензионные соглашения обновлений от имени конечных пользователей. Несоблюдение этого правила является нарушением юридических или договорных обязательств.|Узел для утверждения обновлений и принятия лицензионного соглашения от имени конечного пользователя.<br/><br/>Дополнительные сведения см. в статье [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) (Обновление поставщика службы шифрования).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Важно**<br/>В статье о поставщике служб конфигурации AppLocker содержатся примеры с экранированным языком XML. Для настройки этих параметров в пользовательских профилях Intune необходимо использовать обычный XML.|Строка<br/>Дополнительные сведения см. в статье [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) (Поставщик служб конфигурации AppLocker).|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Целое число<br/>0 — удалить немедленно, когда устройство возвращается в состояние без активных пользователей<br/>1 — удалить при достижении порога емкости хранилища (по умолчанию)<br/>2 — удалить при достижении порога емкости хранилища и порога бездействия профиля|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Логическое значение<br/>True — включить<br/>False — отключить (по умолчанию)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Целое число<br/>Значение по умолчанию — 30.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Целое число<br/>Значение по умолчанию — 25.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Тип данных|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Целое число<br/>Значение по умолчанию — 50.|

## <a name="find-the-policies-you-can-configure"></a>Поиск настраиваемых политик

Полный список поставщиков служб конфигурации (CSP), поддерживаемых Windows Holographic, приведен в разделе [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Некоторые параметры не совместимы с некоторыми версиями Windows Holographic. Таблица в статье Windows содержит сведения о том, какие версии поддерживаются для каждого поставщика служб конфигурации (CSP).

Кроме того, Intune поддерживает не все параметры, перечисленные в этой статье. Чтобы узнать, поддерживает ли Intune необходимый параметр, откройте соответствующую статью для этого параметра. На странице каждого параметра отображаются сведения о поддерживаемых операциях. Для работы с Intune параметр должен поддерживать операции **добавления** или **замены**.
