---
title: "Параметры политики Windows 10 | Документы Майкрософт"
description: "Здесь приведены параметры политики, с помощью которых можно настроить стандартные и пользовательские параметры для зарегистрированных устройств на базе ОС Windows 10 Desktop и Windows 10 Mobile."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5a1a861096bdfae461b6ad05e424f770796279a2


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Параметры политики Intune для устройств на базе Windows 10 в Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Сведения в этом разделе помогут вам разобраться в параметрах политик Intune, которые можно использовать для управления устройствами на базе ОС Windows 10. Ознакомьтесь с этим разделом и процедурами из раздела [Управление настройками и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), чтобы настроить стандартные и пользовательские параметры для зарегистрированных устройств на базе ОС Windows 10 Desktop и Windows 10 Mobile. Эти политики нельзя использовать на компьютерах под управлением [клиентского программного обеспечения Intune](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Можно выбрать один из двух типов политик:

- **Настраиваемая политика** — используйте **настраиваемую политику** Microsoft Intune для Windows 10 и Windows 10 Mobile, чтобы развернуть параметры OMA-URI (универсальный код ресурса Open Mobile Alliance), которые могут применяться для управления функциями на устройствах. Windows 10 предоставляет множество параметров через [поставщика службы конфигурации (CSP) политик](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Общая политика конфигурации** — используйте этот тип политики, если хотите выбрать параметры из встроенного списка, поставляемого вместе с Microsoft Intune.

## <a name="custom-policy-settings"></a>Параметры настраиваемой политики

Укажите следующие параметры в настраиваемой политике.

### <a name="general"></a>Общие

Введите имя и при необходимости описание политики для идентификации ее в консоли Intune.

### <a name="oma-uri-settings"></a>Параметры OMA-URI

Для каждого добавляемого параметра OMA-URI введите указанные ниже сведения. Сведения о параметрах, которые можно использовать, см. в [справочнике по настройкам URI для Windows 10](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) в этом разделе.

- **Имя параметра** — введите уникальное название параметра OMA-URI, чтобы его было проще найти в списке параметров.
- **Описание параметра** — введите необязательное описание параметра.
- **Тип данных** — выберите один из следующих типов данных:
    - **Строка**
    - **Строка (XML)**
    - **Дата и время**
    - **Целое число**
    - **Число с плавающей запятой**
    - **Логическое значение**
- **OMA-URI (с учетом регистра)** — задайте OMA-URI, для которого необходимо указать параметр.
- **Значение** — укажите значение, которое требуется связать с заданным OMA-URI.

### <a name="example"></a>Пример
На следующем снимке экрана параметр **Connectivity/AllowVPNOverCellular** был включен. Это позволяет устройству с Windows 10 открыть VPN-подключение по сети мобильной связи.

> ![Пример настраиваемой политики, содержащей параметры VPN](./media/custom-policy-example.png)

## <a name="windows-10-uri-settings"></a>Настройки URI Windows 10
Этот раздел содержит сведения о параметрах OMA-URI, которые можно настроить с помощью **настраиваемой политики Windows 10**.

### <a name="policy"></a>Политика

|Имя политики и URI|Подробные сведения|
|---------------|------------|-----------|
|**Разрешить автоматическое обновление**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Только для настольных компьютеров<br>**Тип данных:** целочисленный<br />**Значения:** **0** - **5** (по умолчанию: **1**)|
|**День установки по расписанию**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Только для мобильных устройств<br>**Тип данных:** целочисленный<br />**Значения:**<br>**0** — каждый день (по умолчанию)<br>**1** — воскресенье<br>**2** — понедельник<br>**3** — вторник<br>**4** — среда<br>**5** — четверг<br>**6** — пятница<br>**7** — суббота|
|**Время установки по расписанию**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** – **23** часов (**0** — полночь) (по умолчанию: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — пользователь не может установить таймер периода отсрочки пароля, и задано значение "каждый раз".<br>**1** — пользователь может установить таймер периода отсрочки пароля (по умолчанию)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — запретить **использовать подключения Wi-Fi**.<br>**1** — разрешить **использовать подключения Wi-Fi** (значение по умолчанию).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Для настольных компьютеров и мобильных устройств<br>**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запретить общий Интернет. <br> **1** — разрешить общий Интернет (значение по умолчанию).|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — разрешить только подключения Wi-Fi, настроенные при помощи MDM.<br>**1** — разрешить добавление идентификаторов SSID новой сети помимо идентификаторов SSID, которые уже были созданы MDM (значение по умолчанию).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Для настольных компьютеров и мобильных устройств<br>**Тип данных:** целочисленный<br />**Значения:**<br>**0** — запрещено (параметр только для выпуска Корпоративная)<br>**1** — ограничено<br>**2** — полностью (по умолчанию)<br>**3** — полностью и диагностическая информация|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — запрещено<br>**1** — только параметры (по умолчанию)<br>**2** — параметры и эксперименты|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — запретить режим защиты от краж<br>**1** — по усмотрению пользователя (значение по умолчанию).|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br>**1** — разрешено (значение по умолчанию).|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — VPN через сотовую сеть запрещена<br>**1** — VPN может использовать любые соединения, включая сотовые сети (по умолчанию)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — пользователю запрещено включить Bluetooth.<br>**1** — зарезервировано. Пользователь может включить и настроить Bluetooth (не поддерживается в Windows Phone 8.1 для MDM, EAS Windows 10 Desktop или Windows 10 Mobile).<br>**2** — разрешено. Пользователь может включить и настроить Bluetooth (значение по умолчанию).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запретить роуминг.<br> **1** — разрешить роуминг (по умолчанию)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** — запрещено<br> **1** — разрешено (значение по умолчанию).|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** — запрещено<br> **1** — разрешено (значение по умолчанию).|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** (по умолчанию)<br> **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0**<br> **1** (по умолчанию)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** (по умолчанию)<br> **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** (по умолчанию)<br> **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** (значение по умолчанию).<br> **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0**<br> **1** (по умолчанию)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** (по умолчанию)<br> **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** (значение по умолчанию).<br> **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — запретить.<br>Словарь Open Extended Dictionary отключен.<br>Пользователь не может выполнять следующие действия:<br>— Добавление нового словаря Open Extended Dictionary.<br />— Добавление нового файла конфигурации интеграции поиска.<br>– Использование подбора кандидатов в облаке.<br>— Отправка зарегистрированного пользователем слова<br>**1** — разрешить<br>По умолчанию словарь Open Extended Dictionary можно добавлять и использовать. Кроме того, по умолчанию можно применить функцию интеграции поиска.<br>Пользователь может выполнять следующие действия:<br>– Использование подбора кандидатов в облаке.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — ведение журнала ошибок преобразования отключено<br>**1** — ведение журнала ошибок преобразования включено (по умолчанию)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено. <br>**1** — разрешено (значение по умолчанию).|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — никакие символы не фильтруются (по умолчанию)<br>**1** — фильтруется все, за исключением символов Shift JIS|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br />**0** — никакие символы не фильтруются (по умолчанию)<br>**1** — фильтруется все, за исключением символов JIS0208|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — никакие символы не фильтруются (по умолчанию)<br>**1** — фильтруется все, за исключением символов JIS0208 и EUDC|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — строгий режим: наибольшая фильтрация содержимого для взрослых<br>**1** — умеренный режим: умеренная фильтрация содержимого для взрослых (допустимые результаты поиска не будут фильтроваться — по умолчанию)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**Размер принудительного запуска**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — разрешить пользователю изменять размер (по умолчанию)<br>**1** — принудительно использовать неполноэкранный режим.<br>**2** — принудительно использовать полноэкранный режим.|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — не откладывать обновление (остаться в текущей ветви, CB — значение по умолчанию).<br>**1** — разрешить откладывать обновления и установку новых версий (устройство следует правилам Current Branch for Business, CBB).<br />Дополнительные сведения см. в разделе:<br>[Общие сведения об обслуживании Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Планирование развертывания Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Для настольных компьютеров и мобильных устройств<br>**Описание**: политика отсрочки обновлений программного обеспечения на период до четырех недель.<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** — немедленное применение обновлений (значение по умолчанию).<br>**1**-**4** — число недель, на которое откладываются обновления программного обеспечения.<br />Дополнительные сведения см. в разделе:<br>[Общие сведения об обслуживании Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Планирование развертывания Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Для настольных компьютеров и мобильных устройств<br>**Описание**: политика отсрочки обновлений компонентов на период до восьми месяцев<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — немедленное применение обновлений (значение по умолчанию).<br>**1**-**8** — число месяцев, на которое откладывается установка новых версий компонентов.<br />Дополнительные сведения см. в разделе:<br>[Общие сведения об обслуживании Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Планирование развертывания Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Для настольных компьютеров и мобильных устройств<br>**Описание:** позволяет устройству прекратить получение обновлений в течение 5 недель.<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — немедленное применение обновлений (значение по умолчанию).<br>**1** — приостановка обновлений и установки новых версий (срок действия — пять недель)|

### <a name="windows-defender"></a>Защитник Windows

|Имя политики и URI|Подробные сведения|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br> **0** — запрещено<br> **1** — разрешено (значение по умолчанию).|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — мониторинг всех файлов (по умолчанию)<br>**1** — мониторинг входящих файлов<br>**2** — мониторинг исходящих файлов|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** - **90** — представляет время хранения вредоносных программ<br>**0** — вечное хранение вредоносных программ в папке карантина без автоматического удаления (значение по умолчанию).|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**1** — быстрая проверка (по умолчанию)<br>**2** — полная проверка|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — каждый день (по умолчанию)<br>**1** — понедельник<br>**2** — вторник<br>**3** — среда<br>**4** — четверг<br>**5** — пятница<br>**6** — суббота<br>**7** — воскресенье<br>**8** — нет запланированной проверки|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — 12:00<br>**60** — 01:00<br>**120** — 02:00 (по умолчанию)<br>**180** — 03:00<br>**240** — 04:00<br>**300** — 05:00<br>**360** — 06:00<br>**420** — 07:00<br>**480** — 08:00<br>**540** — 09:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1381** — период обслуживания|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Только для настольных компьютеров<br>**Тип данных:** целочисленный<br />**Значения:**<br>**0** — 12:00<br>**60** — 01:00<br>**120** — 02:00 (по умолчанию)<br>**180** — 03:00<br>**240** — 04:00<br>**300** — 05:00<br>**360** — 06:00<br>**420** — 07:00<br>**480** — 08:00<br>**540** — 09:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1380** — 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** - **100** (значение по умолчанию — **50**).|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br>**Значения:<br>** **0** — запрещено (значение по умолчанию).<br> **1** — разрешено.|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено (значение по умолчанию).<br> **1** — разрешено.|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию) — также выполняется, когда RTP включен и разрешен.|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — не проверять подписи с определенным интервалом<br>**1** — проверять подписи каждый час<br>**2** — проверять каждые два часа <br>**24** — проверять каждый день.<br>**8** — проверять каждые восемь часов (значение по умолчанию).|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запрещено.<br> **1** — разрешено (значение по умолчанию).|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — всегда запрашивать (по умолчанию)<br>**1** — автоматически отправлять безопасные образцы<br>**2** — никогда не отправлять<br>**3** — автоматически отправлять все образцы|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Только для настольных компьютеров<br />**Тип данных:** строковый<br />**Значения:**<br>*&lt;Список расширений, разделенных точкой с запятой&gt;*, например **obj;lib**<br>**По умолчанию** — никакие расширения не исключаются.|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Только для настольных компьютеров<br />**Тип данных:** строковый<br />**Значения:**<br />*&lt;Список путей, разделенных точкой с запятой&gt;*<br />Например, **c:\test;c:\test1.exe**<br />**По умолчанию** — никакие пути не исключаются.|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Только для настольных компьютеров<br />**Тип данных:** строковый<br />**Значения:**<br>*&lt;Список путей, разделенных точкой с запятой&gt;*<br>Например, **c:\test.exe;c:\test1.exe**<br>**По умолчанию** — никакие процессы не исключаются.|

### <a name="edge-browser"></a>Браузер Edge

|Имя политики и URI|Подробные сведения|
|---------------|------------|-----------|
|**Разрешить браузер**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Только для мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — просмотр веб-страниц отключен. <br>**1** — просмотр веб-страниц включен (значение по умолчанию).|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — не показывать предложения.<br> **1** — показывать предложения (значение по умолчанию).|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — отключено (открывать сайты интрасети в браузере Edge — значение по умолчанию).<br>**1** — включено (открывать сайты интрасети в Internet Explorer)|
|**Разрешить Do Not Track**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Для настольных систем и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — отключено (не отправлять DNT — значение по умолчанию).<br> **1** — включено (отправлять DNT)|
|**Настройка SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — запретить.<br> **1** — разрешить (по умолчанию)|
|**Разрешить всплывающие окна**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения:<br>** **0** — блокировать всплывающие окна (значение по умолчанию).<br> **1** — разрешить всплывающие окна.|
|**Разрешить файлы cookie**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — разрешить использование файлов cookie со всех веб-сайтов (по умолчанию)<br>**1** — блокировать только сторонние файлы cookie<br>**2** — блокировать все файлы cookie|
|**Разрешить сохранение пароля**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Для настольных компьютеров и мобильных устройств<br />**Тип данных:** целочисленный<br />**Значения:**<br>**0** — диспетчер паролей отключен <br>**1** — диспетчер паролей включен (по умолчанию).|
|**Разрешить автозаполнение**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Только для настольных компьютеров<br />**Тип данных:** целочисленный<br />**Значения**:<br> **0** — отключено (по умолчанию)<br> **1** — включено|
|**Настройка списка корпоративных сайтов**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Только для настольных компьютеров<br />**Тип данных:** строковый<br />**Значения:**<br>**0** — не настроено.<br>**1** — использовать список сайтов в режиме предприятия Internet Explorer, если он настроен (по умолчанию)<br>**2** — укажите расположение списка сайтов предприятия|

## <a name="general-configuration-policy-settings"></a>Параметры общей политики конфигурации

Используйте **общую политику конфигурации** Microsoft Intune для Windows 10, чтобы настроить встроенные параметры для зарегистрированных устройств на базе Windows 10 Mobile и Windows 10 Desktop.

### <a name="password"></a>Пароль

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Требовать пароль для разблокировки устройств**|-|
|**Требуемый тип пароля**|Указывает, должен ли пароль содержать буквы и цифры или только цифры|
|**Требуемый тип пароля** - **Минимальное число наборов символов**| Указывает, сколько наборов символов (строчных и прописных букв, цифр и символов) должно быть в пароле.|
|**Минимальная длина пароля**|Применяется только для Windows 10 Mobile|
|**Число разрешенных неудачных попыток входа перед очисткой устройства**.|Для устройств под управлением Windows 10: если для устройства включен BitLocker, после указанного числа неудачных попыток входа оно переключается в режим восстановления BitLocker. Если BitLocker для устройства не включен, этот параметр не применяется.<br>Для устройств под управлением Windows 10 Mobile: после указанного числа неудачных попыток входа устройство будет очищено.|
|**Период бездействия до отключения экрана (в минутах)**|Указывает период бездействия устройства, по истечении которого экран блокируется.|
|**Срок действия пароля (дней)**|Указывает время, по истечении которого требуется сменить пароль устройства.|
|**Запоминать историю паролей**|Указывает, следует ли запретить пользователю применять использованные ранее пароли.|
|**Вести журнал паролей** - **Запретить использование предыдущих паролей**|Указывает число предыдущих паролей устройства, которые нельзя использовать.|
|**Требовать пароль при возвращении устройства из состояния простоя**|Указывает, что пользователь должен ввести пароль для разблокировки устройства (только Windows 10 Mobile).|

### <a name="encryption"></a>Encryption

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Требовать шифрование на мобильном устройстве**|Включает шифрование на целевых устройствах.<br>(только для Windows 10 Mobile)|

### <a name="system"></a>System (система)

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить снимок экрана**|Позволяет пользователю сохранять содержимое экрана устройства в виде изображения (только Windows 10 Mobile).|
|**Разрешить регистрацию вручную**|Позволяет пользователю вручную удалить рабочую учетную запись с устройства.|
|**Разрешить установку корневого сертификата вручную**|Применяется к Windows 10 Mobile|
|**Разрешить отправку диагностических данных и данных об использовании в Майкрософт**|Возможные значения:<br><br>**Нет** — данные не передаются в корпорацию Майкрософт.<br>**Основные** — в Майкрософт отправляются ограниченные сведения.<br>**Расширенный** — в Майкрософт отправляются расширенные диагностические сведения.<br>**Полный (рекомендуется)** — отправляются те же данные, что и в режиме **Расширенный**, а также дополнительные сведения о состоянии устройства.|


### <a name="account-and-synchronization"></a>Учетная запись и синхронизация

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить использование учетной записи Майкрософт**|Позволяет пользователю сопоставить учетную запись Майкрософт с устройством.|
|**Разрешить добавление учетных записей сторонних производителей вручную**|Позволяет пользователю добавлять на устройство учетные записи электронной почты, которые не сопоставлены с учетной записью Майкрософт.|
|**Разрешить синхронизацию настроек для учетных записей Майкрософт**|Разрешает синхронизацию параметров устройств и приложений, связанных с учетной записью Майкрософт, между устройствами.|

### <a name="microsoft-edge"></a>Microsoft Edge

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить веб-браузер**|Разрешает использовать браузер Edge на устройстве.<br>(только для Windows 10 Mobile)|
|**Разрешить варианты поиска в адресной строке**|Позволяет поисковой системе предлагать сайты при вводе фраз для поиска.|
|**Разрешить отправку трафика интрасети в Internet Explorer**|Позволяет пользователям открывать сайты интрасети в Internet Explorer.<br>(только для Windows 10 Desktop)|
|**Разрешить Do Not Track**|Настраивает в браузере Edge отправку заголовков Do Not Track на посещаемые веб-сайты.|
|**Включить SmartScreen**||
|**Разрешить выполнение активных сценариев**|Разрешает выполнять скрипты, такие как JavaScript, в браузере Edge.|
|**Разрешить всплывающие окна**|Применяется только для Windows 10 Desktop.|
|**Разрешить файлы cookie**||
|**Разрешить автозаполнение**|Разрешает пользователям изменять параметры автозаполнения в браузере.<br>(только для Windows 10 Desktop)|
|**Разрешить диспетчер паролей**|Включает или отключает функцию диспетчера паролей в Edge.|
|**Расположение списка сайтов режима предприятия**|Указывает, где можно найти список веб-сайтов, которые будут открываться в режиме предприятия. Пользователи не могут изменять этот список.<br>(только для Windows 10 Desktop)|

### <a name="apps"></a>Приложения

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить Магазин приложений**|Применяется только для Windows 10 Mobile|



### <a name="cellular"></a>Сотовая сеть

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить передачу данных в роуминге**|Разрешает роуминг между сетями при доступе к данным.|
|**Разрешить VPN через сеть мобильной связи**|Определяет, может ли устройство получить доступ к VPN-подключениям при подключении к сети мобильной связи.|
|**Разрешить передачу данных VPN в роуминге через сеть мобильной связи**|Определяет, может ли устройство получить доступ к VPN-подключениям при роуминге в сети мобильной связи.|

### <a name="hardware"></a>Оборудование

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить камеру**|-|
|**Разрешить съемные носители**|Указывает, можно ли использовать на устройстве внешние запоминающие устройства, например SD-карты.|
|**Разрешить Wi-Fi**|Применяется только для Windows 10 Mobile|
|**Разрешить общий Интернет**|Разрешает использовать на устройстве общий доступ к интернет-подключению.|
|**Разрешить настройку Wi-Fi вручную**|Указывает, может ли пользователь настраивать подключения Wi-Fi либо использовать только подключения на базе профиля Wi-Fi.<br>(только для Windows 10 Mobile)|
|**Разрешить автоматическое подключение к свободным хот-спотам Wi-Fi**|Позволяет устройству автоматически подключаться к хот-спотам Wi-Fi и автоматически принимать любые условия, действующие для такого соединения.|
|**Разрешить геолокацию**|Указывает, может ли устройство использовать сведения о службах определения местоположения.|
|**Разрешить NFC**|Разрешает устройству использовать функции радиочастотной связи ближнего действия (NFC).|
|**Разрешить Bluetooth**|-|
|**Разрешить режим обнаружения Bluetooth**|Разрешает обнаружение устройства другими устройствами, поддерживающими Bluetooth.|
|**Разрешить рекламу по Bluetooth**|Позволяет устройствам получать объявления через Bluetooth.|
|**Разрешить сброс по телефону**|Управляет возможностью сброса пользователем параметров устройства до заводских.|
|**Разрешить USB-подключение**|Указывает, разрешен ли доступ устройства к внешним запоминающим устройствам через USB-подключение.|
|**Разрешить режим защиты от кражи**|Укажите, включен ли режим защиты от кражи Windows.|

### <a name="features"></a>Функции

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить копирование и вставку**|Применяется только для Windows 10 Mobile|
|**Разрешить запись голоса**|Применяется только для Windows 10 Mobile|
|**Разрешить использование Кортаны**|Включает или отключает голосовой помощник — Кортану|
|**Разрешить уведомления центра уведомлений**|Включает или отключает отображение уведомлений из центра уведомлений на экране блокировки устройства<br>(только для Windows 10 Mobile)|

### <a name="windows-defender"></a>Защитник Windows

Все параметры относятся только к Windows 10 Desktop.

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить мониторинг в режиме реального времени**|Позволяет в режиме реального времени проверять наличие вредоносных программ, шпионского ПО и другого нежелательного программного обеспечения.|
|**Разрешить мониторинг поведения**|Позволяет Защитнику отслеживать наличие определенных типичных подозрительных действий на устройствах.|
|**Включить систему проверки сети**|Система проверки сети (NIS) помогает защитить устройства от сетевых эксплойтов, используя сигнатуры известных уязвимостей из Microsoft Endpoint Protection Center для обнаружения и блокировки вредоносного трафика.|
|**Проверять все скачиваемые файлы**|Указывает, проверяет ли Защитник все файлы, загруженные из Интернета.|
|**Разрешить сканирование сценариев**|Позволяет Защитнику проверять скрипты, используемые в Internet Explorer.|
|**Мониторинг действий файлов и программ**|Разрешает Защитнику отслеживать действия, выполняемые с файлами и программами на устройствах.|
|**Дни отслеживания устраненной вредоносной программы**|Позволяет Защитнику продолжить отслеживание устраненной вредоносной программы определенное число дней, чтобы можно было вручную проверить затронутые ранее устройства. Если задать число дней равным **0**, вредоносная программа остается в папке карантина и не удаляется автоматически. |
|**Разрешить доступ к пользовательскому интерфейсу клиента**|Определяет, скрыт ли пользовательский интерфейс Защитника Windows от пользователей.<br>Изменение этого параметра вступает в силу при следующей перезагрузке компьютера.|
|**Запланировать ежедневную быструю проверку**|Позволяет запланировать ежедневную быструю проверку в заданное время.|
|**Запланировать проверку системы**|Позволяет запланировать регулярную полную или быструю проверку системы, указав день и время.|
|**Ограничить загрузку ЦП при проверке**|Позволяет ограничить объем ресурсов ЦП, который может использовать проверка (от **1** до **100**).|
|**Проверять архивные файлы**|Разрешает Защитнику проверять архивные файлы, например ZIP или CAB.|
|**Проверять сообщения электронной почты**|Позволяет Защитнику проверять электронные письма при их поступлении на устройство.|
|**Проверять съемные носители**|Позволяет Защитнику проверять съемные носители, например USB-накопители.|
|**Проверять подключенные сетевые диски**|Позволяет Защитнику проверять файлы на сопоставленных сетевых дисках.<br>Если файлы на диске доступны только для чтения, Защитник не сможет удалить найденные на нем вредоносные программы.|
|**Проверять файлы, открытые из общих сетевых папок**|Позволяет Защитнику проверять файлы на общих сетевых дисках (например, доступных по UNC-пути).<br>Если файлы на диске доступны только для чтения, Защитник не сможет удалить найденные на нем вредоносные программы.|
|**Интервал обновления сигнатур**|Указывает интервал, с которым Защитник проверяет наличие новых файлов сигнатур.|
|**Разрешить защиту в облаке**|Разрешает или запрещает Microsoft Active Protection Service получать с управляемых устройств сведения об активности вредоносных программ. Эти сведения используются для дальнейшего улучшения службы.|
|**Запрашивать у пользователей примеры отправляемых файлов**|Указывает, следует ли отправлять файлы, для определения вредоносности которых может потребоваться дополнительный анализ, в корпорацию Майкрософт автоматически.|
|**Обнаружение потенциально нежелательных приложений**|Защищает зарегистрированные настольные компьютеры с Windows от программ, которые Защитник Windows определил как потенциально нежелательные. Можно настроить защиту от запуска этих приложений или использовать режим аудита для оповещения об установке потенциально нежелательного приложения.|
|**Файлы и папки, которые следует пропускать при выполнении проверки или использовании защиты в режиме реального времени**|Добавляет один файл или папку либо несколько, такие как **C:\Path** или **%ProgramFiles%\Path\имя_файла.exe**, в список исключений. Эти файлы и папки не учитываются при проверках в режиме реального времени или по расписанию.|
|**Расширения файлов, которые следует пропускать при проверке или использовании защиты в режиме реального времени**|Добавляет одно или несколько расширений файла, например **jpg** или **txt**, в список исключений. Все файлы с такими расширениями не учитываются при проверках в режиме реального времени или по расписанию.|
|**Процессы, которые следует пропускать при проверке или использовании защиты в режиме реального времени**|Добавляет один процесс или несколько типа **.exe**, **.com** или **.scr** в список исключений. Эти процессы не учитываются при проверках в режиме реального времени или по расписанию.|


### <a name="updates"></a>Updates

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|---------------|
|**Разрешить автоматические обновления**|Разрешает автоматические обновления. Настройте один из следующих параметров, чтобы контролировать поведение при обновлении.<br />**Уведомление о загрузке**<br />**Автоматическая установка во время обслуживания**<br />**Автоматическая установка и перезагрузка во время обслуживания**<br />**Автоматическая установка и перезагрузка в запланированное время**. Примечание. При выборе этого параметра можно также настроить следующие параметры: **Не отображать уведомления для конечного пользователя** и **Указать день установки запланированных обновлений**.<br>(только для Windows 10 Desktop)|
|**Разрешить функции предварительной версии**|Позволяет корпорации Майкрософт развертывать на устройствах Windows 10 предварительные версии настроек и компонентов. Вы можете разрешить установку только настроек или всех настроек и компонентов, находящихся на этапе предварительной версии.|

### <a name="see-also"></a>См. также
[Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->


