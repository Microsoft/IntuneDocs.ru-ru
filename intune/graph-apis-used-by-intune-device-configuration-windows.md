---
title: API Graph для настройки устройств в Microsoft Intune в Azure | Документация Майкрософт
titleSuffix: ''
description: Просмотрите список всех API Graph сущностей с соответствующим CSP Windows и URL-адресом смещения на устройствах Windows 10 и более поздней версии, используемой при настройке устройств в Microsoft Intune. См. соответствующий API и CSP для общих компьютеров, Endpoint Protection, Windows Defender Advanced Threat Protection, защиты идентификации, групп Windows 10, киосков и Центр обновления Windows для бизнеса.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3732a4539c13ad05ae8c95621246429b7f38987e
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354422"
---
# <a name="graph-apis-and-matching-windows-10-csps-used-in-intune"></a>API Graph и соответствующие CSP Windows 10, используемые в Intune

Microsoft Intune использует [сущности API Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview) (открывает другой сайт документов) для настройки устройств (**Конфигурация устройства** **Intune** > ) под Windows 10 и более поздних версий. API Graph использует поставщики службы конфигурации (CSP) для чтения, установки, изменения и/или удаления параметров конфигурации на устройствах.

Этот список применим к:

- Windows 10 и более поздней версии

В этой статье перечислены сущности графа и соответствующие поставщики CSP Windows 10 и коды URI смещения.

Эти сведения полезны в различных сценариях. Например, см. сведения об использовании Intune в разделе Параметры для включения в настраиваемые конфигурации OMA-URI и т. д. 

## <a name="windows-10-csps"></a>Поставщики CSP Windows 10

Дополнительные сведения о поставщиках служб конфигурации Windows 10 см. в [справочнике по поставщику службы конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (открывается другой сайт документации).

## <a name="graph-api-properties-to-csp-mapping"></a>API Graph свойств в сопоставление CSP

В следующем списке показаны большинство сущностей API Graph, используемых Microsoft Intune для конфигурации устройств Windows 10. Он также показывает соответствующий CSP Windows 10 и URI смещения.

Чтобы просмотреть версии Windows 10, применимые к следующим API, используйте [ссылку поставщика службы конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) Windows 10 (открывает другой сайт документации).

### <a name="editionupgradeconfigurationlicense"></a>Едитионупградеконфигуратион. License 
**CSP**:./девице/вендор/мсфт/виндовслиценсинг  
**URI смещения**:/упградидитионвислиценсе

### <a name="editionupgradeconfigurationlicensetype"></a>Едитионупградеконфигуратион. LicenseType 
**CSP**:./девице/вендор/мсфт/виндовслиценсинг  
**URI смещения**:/лиценсекэйтипе

### <a name="editionupgradeconfigurationproductkey"></a>Едитионупградеконфигуратион. ProductKey 
**CSP**:./девице/вендор/мсфт/виндовслиценсинг  
**URI смещения**:/упградидитионвиспродукткэй

### <a name="editionupgradeconfigurationwindowssmode"></a>Едитионупградеконфигуратион. Виндовссмоде 
**CSP**:./девице/вендор/мсфт/виндовслиценсинг  
**URI смещения**:/смоде/свитчингполици

### <a name="sharedpcconfigurationaccountmanagerpolicy"></a>Шаредпкконфигуратион. Аккаунтманажерполици 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/Делетионполици,/Дисклевелкачинг,/Инактивесрешолд,/дисклевелделетион

### <a name="sharedpcconfigurationaccountmanagerpolicy-windows-holographic-for-business-edition-targeted-devices"></a>Шаредпкконфигуратион. Аккаунтманажерполици (целевые устройства Windows holographic for Business Edition) 
**CSP**:./вендор/мсфт/аккаунтманажемент  
**URI смещения**:/Делетионполици,/СторажекапаЦитистартделетион,/СторажекапаЦитистопделетион,/профилеинактивитисрешолд

### <a name="sharedpcconfigurationallowedaccounts"></a>Шаредпкконфигуратион. Алловедаккаунтс 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/аккаунтмодел

### <a name="sharedpcconfigurationallowlocalstorage"></a>Шаредпкконфигуратион. Алловлокалстораже 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/рестриктлокалстораже

### <a name="sharedpcconfigurationdisableaccountmanager"></a>Шаредпкконфигуратион. Дисаблеаккаунтманажер 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/енаблеаккаунтманажер

### <a name="sharedpcconfigurationdisableedupolicies"></a>Шаредпкконфигуратион. ДисаблидуполиЦиес 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сетедуполиЦиес

### <a name="sharedpcconfigurationdisablepowerpolicies"></a>Шаредпкконфигуратион. ДисаблеповерполиЦиес 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сетповерполиЦиес

### <a name="sharedpcconfigurationdisablesigninonresume"></a>Шаредпкконфигуратион. Дисаблесигнинонресуме 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сигнинонресуме

### <a name="sharedpcconfigurationenabled"></a>Шаредпкконфигуратион. Enabled 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/енаблешаредпкмоде

### <a name="sharedpcconfigurationidletimebeforesleepinseconds"></a>Шаредпкконфигуратион. Идлетимебефореслипинсекондс 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/инактивесрешолд

### <a name="sharedpcconfigurationkioskappdisplayname"></a>Шаредпкконфигуратион. Киоскаппдисплайнаме 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/киоскмодеусертиледисплайтекст

### <a name="sharedpcconfigurationkioskappusermodelid"></a>Шаредпкконфигуратион. Киоскаппусермоделид 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/киоскмодеаумид

### <a name="sharedpcconfigurationlocalstorage"></a>Шаредпкконфигуратион. LocalStorage 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/рестриктлокалстораже

### <a name="sharedpcconfigurationmaintenancestarttime"></a>Шаредпкконфигуратион. Маинтенанцестарттиме 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/маинтенанцестарттиме

### <a name="sharedpcconfigurationsetaccountmanager"></a>Шаредпкконфигуратион. Сетаккаунтманажер
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/енаблеаккаунтманажер

### <a name="sharedpcconfigurationsetedupolicies"></a>Шаредпкконфигуратион. СетедуполиЦиес 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сетедуполиЦиес

### <a name="sharedpcconfigurationsetpowerpolicies"></a>Шаредпкконфигуратион. СетповерполиЦиес 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сетповерполиЦиес

### <a name="sharedpcconfigurationsigninonresume"></a>Шаредпкконфигуратион. Сигнинонресуме 
**CSP**:./вендор/мсфт/шаредпк  
**URI смещения**:/сигнинонресуме

### <a name="windows10endpointconfigurationsmartscreenblockoverrideforfiles"></a>Windows10endpointconfiguration. Смартскринблокковерридефорфилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/смартскрин/превентоверридефорфилесиншелл

### <a name="windows10endpointprotectionconfigurationapplicationguardallowfilesaveonhost"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловфилесавеонхост 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/савефилестохост

### <a name="windows10endpointprotectionconfigurationapplicationguardallowpersistence"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловперсистенце 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/алловперсистенце

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttolocalprinters"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловпринттолокалпринтерс 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/принтингсеттингс

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttonetworkprinters"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловпринттонетворкпринтерс 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/принтингсеттингс

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttopdf"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловпринттопдф 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/принтингсеттингс

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttoxps"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловпринттокспс 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/принтингсеттингс

### <a name="windows10endpointprotectionconfigurationapplicationguardallowvirtualgpu"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардалловвиртуалгпу 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/алловвиртуалгпу

### <a name="windows10endpointprotectionconfigurationapplicationguardblockclipboardsharing"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардблоккклипбоардшаринг 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/клипбоардсеттингс

### <a name="windows10endpointprotectionconfigurationapplicationguardblockfiletransfer"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардблоккфилетрансфер 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/клипбоардфилетипе

### <a name="windows10endpointprotectionconfigurationapplicationguardblocknonenterprisecontent"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардблоккнонентерприсеконтент 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/блоккнонентерприсеконтент

### <a name="windows10endpointprotectionconfigurationapplicationguardenabled"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуарденаблед 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/Сеттингс/алловвиндовсдефендераппликатионгуард

### <a name="windows10endpointprotectionconfigurationapplicationguardforceauditing"></a>Windows10EndpointProtectionConfiguration. Аппликатионгуардфорцеаудитинг 
**CSP**:./девице/вендор/мсфт/виндовсдефендераппликатионгуард  
**URI смещения**:/аудит/аудитаппликатионгуард

### <a name="windows10endpointprotectionconfigurationbitlockerallowstandarduserencryption"></a>Windows10EndpointProtectionConfiguration. Битлоккералловстандардусеренкриптион 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/алловстандардусеренкриптион

### <a name="windows10endpointprotectionconfigurationbitlockerdisablewarningforotherdiskencryption"></a>Windows10EndpointProtectionConfiguration. Битлоккердисаблеварнингфоросердискенкриптион 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/алловварнингфоросердискенкриптион

### <a name="windows10endpointprotectionconfigurationbitlockerenablestoragecardencryptiononmobile"></a>Windows10EndpointProtectionConfiguration. Битлоккеренаблесторажекарденкриптиононмобиле 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/рекуиресторажекарденкриптион

### <a name="windows10endpointprotectionconfigurationbitlockerencryptdevice"></a>Windows10EndpointProtectionConfiguration. Битлоккеренкриптдевице 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/рекуиредевицеенкриптион

### <a name="windows10endpointprotectionconfigurationbitlockerfixeddrivepolicy"></a>Windows10EndpointProtectionConfiguration. Битлоккерфикседдривеполици 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/Енкриптионмесодбидриветипе,/Фикседдривесрекуиринкриптион,/фикседдривесрековерйоптионс

### <a name="windows10endpointprotectionconfigurationbitlockerremovabledrivepolicy"></a>Windows10EndpointProtectionConfiguration. Битлоккерремовабледривеполици 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/Енкриптионмесодбидриветипе,/ремовабледривесрекуиринкриптион

### <a name="windows10endpointprotectionconfigurationbitlockersystemdrivepolicy"></a>Windows10EndpointProtectionConfiguration. Битлоккерсистемдривеполици 
**CSP**:./девице/вендор/мсфт/битлоккер  
**URI смещения**:/Енкриптионмесодбидриветипе,/Системдривесрекуирестартупаусентикатион,/Системдривесминимумпинленгс,/SystemDrivesRecoveryMessage,/SystemDrivesRecoveryOptions

### <a name="windows10endpointprotectionconfigurationclientconnectionencryptionlevel"></a>windows10endpointprotectionconfiguration. Клиентконнектионенкриптионлевел 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/клиентконнектионенкриптионлевел

### <a name="windows10endpointprotectionconfigurationconfiguresmbv1clientdriver"></a>windows10endpointprotectionconfiguration.configureSMBV1ClientDriver 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/config/MSSecurityGuide/ConfigureSMBV1ClientDriver

### <a name="windows10endpointprotectionconfigurationconnectivitydownloadingofprintdriversoverhttp"></a>Windows10EndpointProtectionConfiguration. Коннективитидовнлоадингофпринтдриверсоверхттп 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/дисабледовнлоадингофпринтдриверсоверхттп

### <a name="windows10endpointprotectionconfigurationconnectivityhardeneduncpaths"></a>Windows10EndpointProtectionConfiguration. Коннективитихарденедункпасс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/харденедункпасс

### <a name="windows10endpointprotectionconfigurationconnectivityinternetdownloadforwebpublishingandonlineorderingwizards"></a>Windows10EndpointProtectionConfiguration. Коннективитинтернетдовнлоадфорвебпублишингандонлинеордерингвизардс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/дисаблеинтернетдовнлоадфорвебпублишингандонлинеордерингвизардс

### <a name="windows10endpointprotectionconfigurationconnectivityprintingoverhttp"></a>Windows10EndpointProtectionConfiguration. Коннективитипринтинговерхттп 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/диаблепринтинговерхттп

### <a name="windows10endpointprotectionconfigurationcredentialsuienumerateadministrators"></a>Windows10EndpointProtectionConfiguration. Кредентиалсуиенумератеадминистраторс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/кредентиалсуи/енумератеадминистраторс

### <a name="windows10endpointprotectionconfigurationdefenderadditionalguardedfolders"></a>Windows10EndpointProtectionConfiguration. Дефендераддитионалгуардедфолдерс 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/Дефендер/контролледфолдеракцесспротектедфолдерс

### <a name="windows10endpointprotectionconfigurationdefenderadvancedransomewareprotectiontype"></a>Windows10EndpointProtectionConfiguration. Дефендерадванцедрансомеварепротектионтипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderattacksurfacereductionexcludedpaths"></a>Windows10EndpointProtectionConfiguration. Дефендераттакксурфацередуктионексклудедпасс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктиононлексклусионс

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecution"></a>Windows10EndpointProtectionConfiguration. Дефендеремаилконтентексекутион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловемаилсканнинг

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecutiontype"></a>Windows10EndpointProtectionConfiguration. Дефендеремаилконтентексекутионтипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxml"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXml 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/експлоитгуард/експлоитпротектионсеттингс

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxmlfilename"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXmlFileName 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експлоитгуард/експлоитпротектионсеттингс

### <a name="windows10endpointprotectionconfigurationdefenderguardedfoldersallowedapppaths"></a>Windows10EndpointProtectionConfiguration. Дефендергуардедфолдерсалловедапппасс 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/Дефендер/контролледфолдеракцессалловедаппликатионс

### <a name="windows10endpointprotectionconfigurationdefenderguardmyfolderstype"></a>Windows10EndpointProtectionConfiguration.DefenderGuardMyFoldersType 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/енаблеконтролледфолдеракцесс

### <a name="windows10endpointprotectionconfigurationdefendernetworkprotectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderNetworkProtectionType 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/Дефендер/енабленетворкпротектион

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunch"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunch 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunchtype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunchType
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocess"></a>Windows10EndpointProtectionConfiguration. Дефендероффицеаппслаунччилдпроцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocesstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsLaunchChildProcessType 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjection"></a>Windows10EndpointProtectionConfiguration. Дефендероффицеаппсосерпроцессинжектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjectiontype"></a>Windows10EndpointProtectionConfiguration. Дефендероффицеаппсосерпроцессинжектионтипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе 

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32imports"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32Imports 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32importstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32ImportsType 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderpreventcredentialstealingtype"></a>Windows10EndpointProtectionConfiguration. Дефендерпревенткредентиалстеалингтипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreation"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreation 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreationtype"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreationType 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderprotectagainstpotentiallyunwantedapplications"></a>Windows10EndpointProtectionConfiguration. Дефендерпротектагаинстпотентиаллюнвантедаппликатионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мссекуритигуиде/турнонвиндовсдефендерпротектионагаинстпотентиаллюнвантедаппликатионс

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecution"></a>Windows10EndpointProtectionConfiguration. Дефендерскриптдовнлоадедпайлоадексекутион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecutiontype"></a>Windows10EndpointProtectionConfiguration. Дефендерскриптдовнлоадедпайлоадексекутионтипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocode"></a>Windows10EndpointProtectionConfiguration. Дефендерскриптобфускатедмакрокоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocodetype"></a>Windows10EndpointProtectionConfiguration. Дефендерскриптобфускатедмакрокодетипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterblockexploitprotectionoverride"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterBlockExploitProtectionOverride 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/виндовсдефендерсекуритицентер/дисалловексплоитпротектионоверриде

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableaccountui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблеаккаунтуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисаблеаккаунтпротектионуи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableappbrowserui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблеаппбровсеруи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисаблеаппбровсеруи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablefamilyui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблефамилюи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисаблефамилюи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablehealthui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableHealthUI 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисаблехеалсуи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablenetworkui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисабленетворкуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисабленетворкуи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablesecurebootui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблесекуребутуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/хидесекуребут

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisabletroubleshootingui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблетраублешутингуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/хидетпмтраублешутинг

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablevirusui"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентердисаблевирусуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/дисаблевирусуи

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpemail"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpEmail 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/емаил

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpphone"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpPhone 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/фоне

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpurl"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpURL 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/УРЛ

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenteritcontactdisplay"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентеритконтактдисплай 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/Виндовсдефендерсекуритицентер/енаблекустомизедтоастс,/виндовсдефендерсекуритицентер/енаблеинаппкустомизатион

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenternotificationsfromapp"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентернотификатионсфромапп 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/хидевиндовссекуритинотификатионареаконтрол

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterorganizationdisplayname"></a>Windows10EndpointProtectionConfiguration. Дефендерсекуритицентерорганизатиондисплайнаме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсдефендерсекуритицентер/компанинаме

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutable"></a>Windows10EndpointProtectionConfiguration. Дефендерунтрустедексекутабле 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutabletype"></a>Windows10EndpointProtectionConfiguration. Дефендерунтрустедексекутаблетипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocess"></a>Windows10EndpointProtectionConfiguration. Дефендерунтрустедусбпроцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/аттакксурфацередуктионрулес

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocesstype"></a>Windows10EndpointProtectionConfiguration. Дефендерунтрустедусбпроцесстипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/КОНФИГ/ДЕФЕНДЕР/АТТАККСУРФАЦЕРЕДУКТИОНРУЛЕС (CSP/Configuration, требуются свойства Graph: Windows10endpointprotection/Configuration. дефендероффицеаппсосерпроцессинжектионтипе, windows10endpointprotection/ Configuration. Дефендероффицеаппсексекутаблеконтенткреатионорлаунчтипе, windows10endpointprotection/Configuration. Дефендероффицеаппслаунччилдпроцесстипе, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. Дефендерскриптобфускатедмакрокодетипе, windows10endpointprotection/Configuration. Дефендерскриптдовнлоадедпайлоадексекутионтипе , windows10endpointprotection/Configuration. Дефендеремаилконтентексекутионтипе, windows10endpointprotection/Configuration. Дефендерпревенткредентиалстеалингтипе, windows10endpointprotection/ Configuration. Дефендерунтрустедусбпроцесстипе

### <a name="windows10endpointprotectionconfigurationdeviceguardenablesecurebootwithdma"></a>Windows10EndpointProtectionConfiguration. Девицегуарденаблесекуребутвисдма 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицегуард/рекуиреплатформсекуритифеатурес

### <a name="windows10endpointprotectionconfigurationdeviceguardenablevirtualizationbasedsecurity"></a>Windows10EndpointProtectionConfiguration. Девицегуарденаблевиртуализатионбаседсекурити 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/девицегуард/енаблевиртуализатионбаседсекурити

### <a name="windows10endpointprotectionconfigurationdeviceguardlaunchsystemguard"></a>Windows10EndpointProtectionConfiguration. Девицегуардлаунчсистемгуард 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицегуард/конфигуресистемгуардлаунч

### <a name="windows10endpointprotectionconfigurationdeviceguardlocalsystemauthoritycredentialguardsettings"></a>Windows10EndpointProtectionConfiguration. Девицегуардлокалсистемаусоритикредентиалгуардсеттингс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицегуард/лсакфгфлагс

### <a name="windows10endpointprotectionconfigurationdmaguarddeviceenumerationpolicy"></a>Windows10EndpointProtectionConfiguration. Дмагуарддевицеенумератионполици 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/дмагуард/девицеенумератионполици

### <a name="windows10endpointprotectionconfigurationeventlogserviceapplicationlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration. Евентлогсервицеаппликатионлогмаксимумфилесизеинкб 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/евентлогсервице/спеЦифимаксимумфилесизеаппликатионлог

### <a name="windows10endpointprotectionconfigurationeventlogservicesecuritylogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceSecurityLogMaximumFileSizeInKb 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/евентлогсервице/спеЦифимаксимумфилесизесекуритилог

### <a name="windows10endpointprotectionconfigurationeventlogservicesystemlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration. Евентлогсервицесистемлогмаксимумфилесизеинкб 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/евентлогсервице/спеЦифимаксимумфилесизесистемлог

### <a name="windows10endpointprotectionconfigurationexplorerdataexecutionprevention"></a>Windows10EndpointProtectionConfiguration. Експлорердатаексекутионпревентион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/филиксплорер/турноффдатаексекутионпревентионфорексплорер

### <a name="windows10endpointprotectionconfigurationexplorerheapterminationoncorruption"></a>Windows10EndpointProtectionConfiguration. Експлорерхеаптерминатиононкорруптион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/филиксплорер/турноффхеаптерминатиононкорруптион

### <a name="windows10endpointprotectionconfigurationfirewallblockstatefulftp"></a>Windows10EndpointProtectionConfiguration. Фиреваллблоккстатефулфтп 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/дисаблестатефулфтп

### <a name="windows10endpointprotectionconfigurationfirewallcertificaterevocationlistcheckmethod"></a>Windows10EndpointProtectionConfiguration. Фиреваллцертификатеревокатионлистчеккмесод 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/крлчекк

### <a name="windows10endpointprotectionconfigurationfirewallidletimeoutforsecurityassociationinseconds"></a>Windows10EndpointProtectionConfiguration. ФиреваллидлетимеаутфорсекуритяссоЦиатионинсекондс 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/саидлетиме

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowdhcp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowDHCP 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/ипсецексемпт

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowicmp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowICMP 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/ипсецексемпт

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowneighbordiscovery"></a>Windows10EndpointProtectionConfiguration. Фиреваллипсецексемптионсалловнеигхбордисковери 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/ипсецексемпт

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowrouterdiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowRouterDiscovery 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/ипсецексемпт

### <a name="windows10endpointprotectionconfigurationfirewallmergekeyingmodulesettings"></a>Windows10EndpointProtectionConfiguration. Фиреваллмержекэйингмодулесеттингс 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/оппортунистикаллиматчауссетперкм

### <a name="windows10endpointprotectionconfigurationfirewallpacketqueueingmethod"></a>Windows10EndpointProtectionConfiguration. Фиреваллпаккеткуеуеингмесод 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/енаблепаккеткуеуе

### <a name="windows10endpointprotectionconfigurationfirewallpresharedkeyencodingmethod"></a>Windows10EndpointProtectionConfiguration. Фиреваллпрешаредкэйенкодингмесод 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/Глобал/прешаредкэйенкодинг

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomain"></a>Windows10EndpointProtectionConfiguration. Фиреваллпрофиледомаин 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/Енаблефиревалл,/Дисаблестеалсмоде,/Шиелдед,/Дисаблеуникастреспонсестомултикастброадкаст,/DisableInboundNotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Дефаултаутбаундактион,/Дефаултинбаундактион,/Дисаблестеалсмодеипсексекуредпаккетексемптион,/AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофиледомаин. Инбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/домаинпрофиле/дефаултинбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофиледомаин. Инбаунднотификатионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/домаинпрофиле/дисаблеинбаунднотификатионс

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофиледомаин. Инбаунднотификатионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/домаинпрофиле/енаблефиревалл

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomainoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофиледомаин. Аутбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/домаинпрофиле/дефаултаутбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivate"></a>Windows10EndpointProtectionConfiguration. Фиреваллпрофилепривате 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/Енаблефиревалл,/Дисаблестеалсмоде,/Шиелдед,/Дисаблеуникастреспонсестомултикастброадкаст,/DisableInboundNotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Дефаултаутбаундактион,/Дефаултинбаундактион,/Дисаблестеалсмодеипсексекуредпаккетексемптион,/AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivatefirewallenabled"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепривате. Фиревалленаблед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/приватепрофиле/енаблефиревалл

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепривате. Инбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/приватепрофиле/дефаултинбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепривате. Инбаунднотификатионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/приватепрофиле/дисаблеинбаунднотификатионс

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепривате. Аутбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/приватепрофиле/дефаултаутбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublic"></a>Windows10EndpointProtectionConfiguration. Фиреваллпрофилепублик 
**CSP**:./вендор/мсфт/фиревалл  
**URI смещения**:/Енаблефиревалл,/Дисаблестеалсмоде,/Шиелдед,/Дисаблеуникастреспонсестомултикастброадкаст,/DisableInboundNotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Дефаултаутбаундактион,/Дефаултинбаундактион,/Дисаблестеалсмодеипсексекуредпаккетексемптион,/AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicconnectionsecurityrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Коннектионсекуритирулесфромграупполицимержед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/алловлокалипсекполицимерже

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicfirewallenabled"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Фиревалленаблед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/енаблефиревалл

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Инбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/дефаултинбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Инбаунднотификатионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/дисаблеинбаунднотификатионс

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Аутбаундконнектионсблоккед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/дефаултаутбаундактион

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicpolicyrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration. Фиреваллпрофилепублик. Полицирулесфромграупполицимержед 
**CSP**:./девице/вендор/мсфт/фиревалл  
**URI смещения**:/мдмсторе/публикпрофиле/алловлокалполицимерже

### <a name="windows10endpointprotectionconfigurationlanmanagerauthenticationlevel"></a>Windows10EndpointProtectionConfiguration. Ланманажераусентикатионлевел 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворксекурити\_ланманажераусентикатионлевел

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationdisableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration. Ланманажерворкстатиондисаблеинсекурегуестлогонс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ланманворкстатион/енаблеинсекурегуестлогонс

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationenableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration. Ланманажерворкстатионенаблеинсекурегуестлогонс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ланманворкстатион/енаблеинсекурегуестлогонс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratoraccountname"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсадминистратораккаунтнаме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_ренамеадминистратораккаунт

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratorelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсадминистраторелеватионпромптбехавиор
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_бехавиорофсилеватионпромптфорадминистраторс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowanonymousenumerationofsamaccountsandshares"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсаллованонимаусенумератионофсамаккаунтсандшарес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворкакцесс\_доноталлованонимаусенумератионофсамаккаунтсандшарес

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowpku2uauthenticationrequests"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowPKU2UAuthenticationRequests 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворксекурити\_AllowPKU2UAuthenticationRequests

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanager"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловремотекаллстосекуритяккаунтсманажер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворкакцесс\_рестриктклиентсалловедтомакеремотекаллстосам

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanagerhelperbool"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловремотекаллстосекуритяккаунтсманажерхелпербул 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворкакцесс\_рестриктклиентсалловедтомакеремотекаллстосам

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowsystemtobeshutdownwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловсистемтобешутдовнвисаусавингтологон 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/шутдовн\_алловсистемтобешутдовнвисаусавингтологон

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationelevation"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловуиакцессаппликатионелеватион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_алловуиакцессаппликатионстопромптфорелеватион

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationsforsecurelocations"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловуиакцессаппликатионсфорсекурелокатионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_онлелеватеуиакцессаппликатионссатареинсталлединсекурелокатионс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowundockwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсалловундокквисаусавингтологон 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/девицес\_алловундокквисаусавингтологон

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockmicrosoftaccounts"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсблоккмикрософтаккаунтс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_блоккмикрософтаккаунтс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremotelogonwithblankpassword"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсблоккремотелогонвисбланкпассворд 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_лимитлокалаккаунтусеофбланкпассвордстоконсолелогононли

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremoteopticaldriveaccess"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсблоккремотеоптикалдривеакцесс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/девицес\_рестрикткдромакцесстолокаллилогжедонусеронли

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockusersinstallingprinterdrivers"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсблоккусерсинсталлингпринтердриверс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/девицес\_превентусерсфроминсталлингпринтердриверсвхенконнектингтошаредпринтерс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclearvirtualmemorypagefile"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсклеарвиртуалмеморипажефиле 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/шутдовн\_клеарвиртуалмеморипажефиле

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClientDigitallySignCommunicationsAlways 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/микрософтнетворкклиент\_дигиталлисигнкоммуникатионсалвайс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientsendunencryptedpasswordtothirdpartysmbservers"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсклиентсендуненкриптедпассвордтосирдпартисмбсерверс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/микрософтнетворкклиент\_сендуненкриптедпассвордтосирдпартисмбсерверс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdetectapplicationinstallationsandpromptforelevation"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдетектаппликатионинсталлатионсандпромптфорелеватион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_детектаппликатионинсталлатионсандпромптфорелеватион

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableadministratoraccount"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдисаблеадминистратораккаунт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_енаблеадминистратораккаунтстатус

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableclientdigitallysigncommunicationsifserveragrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableClientDigitallySignCommunicationsIfServerAgrees 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/микрософтнетворкклиент\_дигиталлисигнкоммуникатионсифсерверагрис

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableguestaccount"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдисаблегуестаккаунт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_енаблегуестаккаунтстатус

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдисаблесервердигиталлисигнкоммуникатионсалвайс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/микрософтнетворксервер\_дигиталлисигнкоммуникатионсалвайс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsifclientagrees"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдисаблесервердигиталлисигнкоммуникатионсифклиентагрис 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/микрософтнетворксервер\_дигиталлисигнкоммуникатионсифклиентагрис

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotallowanonymousenumerationofsamaccounts"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдоноталлованонимаусенумератионофсамаккаунтс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворкакцесс\_доноталлованонимаусенумератионофсамаккаунтс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotrequirectrlaltdel"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotRequireCtrlAltDel 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_донотрекуиректрлалтдел

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotstorelanmanagerhashvalueonnextpasswordchange"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсдонотстореланманажерхашвалуеоннекстпассвордчанже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворксекурити\_донотстореланманажерхашвалуеоннекстпассвордчанже

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableadministratoraccount"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсенаблеадминистратораккаунт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_енаблеадминистратораккаунтстатус

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableguestaccount"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсенаблегуестаккаунт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_енаблегуестаккаунтстатус

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsformatandejectofremovablemediaalloweduser"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсформатандежектофремоваблемедиаалловедусер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/девицес\_алловедтоформатандежектремоваблемедиа

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsguestaccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsGuestAccountName 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/аккаунтс\_ренамегуестаккаунт

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshidelastsignedinuser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideLastSignedInUser 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_донотдисплайластсигнедин

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshideusernameatsignin"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideUsernameAtSignIn 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_донотдисплайусернамеатсигнин

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationdisplayedonlockscreen"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсинформатиондисплайедонлоккскрин 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_дисплайусеринформатионвхенсесессионислоккед

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationshownonlockscreen"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсинформатионшовнонлоккскрин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_дисплайусеринформатионвхенсесессионислоккед

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetext"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageText 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_мессажетекстфорусерсаттемптингтологон

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetitle"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageTitle 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_мессажетитлефорусерсаттемптингтологон

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimit"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimit 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_мачинеинактивитилимит

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimitinminutes"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimitInMinutes 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_мачинеинактивитилимит

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedclients"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedClients 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворксекурити\_минимумсессионсекуритифорнтлмсспбаседклиентс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedservers"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсминимумсессионсекуритифорнтлмсспбаседсерверс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворксекурити\_минимумсессионсекуритифорнтлмсспбаседсерверс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsonlyelevatesignedexecutables"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсонлелеватесигнедексекутаблес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_онлелеватиксекутаблефилессатаресигнедандвалидатед

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsrestrictanonymousaccesstonamedpipesandshares"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсрестриктанонимаусакцесстонамедпипесандшарес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/нетворкакцесс\_рестриктанонимаусакцесстонамедпипесандшарес

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionssmartcardremovalbehavior"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионссмарткардремовалбехавиор 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/интерактивелогон\_смарткардремовалбехавиор

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsstandarduserelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсстандардусерелеватионпромптбехавиор 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_бехавиорофсилеватионпромптфорстандардусерс

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsswitchtosecuredesktopwhenpromptingforelevation"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионссвитчтосекуредесктопвхенпромптингфорелеватион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_свитчтосесекуредесктопвхенпромптингфорелеватион

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmode"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsUseAdminApprovalMode 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_усеадминаппровалмоде

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmodeforadministrators"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсусеадминаппровалмодефорадминистраторс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_руналладминистраторсинадминаппровалмоде

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsvirtualizefileandregistrywritefailurestoperuserlocations"></a>Windows10EndpointProtectionConfiguration. Локалсекуритйоптионсвиртуализефилеандрегистривритефаилурестоперусерлокатионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/локалполиЦиессекуритйоптионс/усераккаунтконтрол\_виртуализефилеандрегистривритефаилурестоперусерлокатионс

### <a name="windows10endpointprotectionconfigurationnetworkicmpredirectsoverrideospfgeneratedroutes"></a>Windows10EndpointProtectionConfiguration.NetworkIcmpRedirectsOverrideOspfGeneratedRoutes 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мсслегаци/алловикмпредиректстуверридеоспфженератедраутес

### <a name="windows10endpointprotectionconfigurationnetworkignorenetbiosnamereleaserequestsexceptfromwinsservers"></a>Windows10EndpointProtectionConfiguration.NetworkIgnoreNetBiosNameReleaseRequestsExceptFromWinsServers 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мсслегаци/алловсекомпутертоигноренетбиоснамерелеасерекуестсексцептфромвинссерверс

### <a name="windows10endpointprotectionconfigurationnetworkipsourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration. Нетворкипсаурцераутингпротектионлевел 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мсслегаци/ипсаурцераутингпротектионлевел

### <a name="windows10endpointprotectionconfigurationnetworkipv6sourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpV6SourceRoutingProtectionLevel 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/config/MSSLegacy/IPv6SourceRoutingProtectionLevel

### <a name="windows10endpointprotectionconfigurationpasswordpinlogon"></a>Windows10EndpointProtectionConfiguration. Пассвордпинлогон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/кредентиалпровидерс/алловпинлогон

### <a name="windows10endpointprotectionconfigurationpowershellshellscriptblocklogging"></a>Windows10EndpointProtectionConfiguration. Повершеллшеллскриптблокклоггинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсповершелл/турнонповершеллскриптблокклоггинг

### <a name="windows10endpointprotectionconfigurationremoteassistancesolicitedsetting"></a>Windows10EndpointProtectionConfiguration. РемотеассистанцесолиЦитедсеттинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/харденедункпасс

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesclientconnectionencryptionlevel"></a>Windows10EndpointProtectionConfiguration. Ремотедесктопсервицесклиентконнектионенкриптионлевел 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/клиентконнектионенкриптионлевел

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesdriveredirection"></a>Windows10EndpointProtectionConfiguration. Ремотедесктопсервицесдривередиректион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/доноталловдривередиректион

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespasswordsaving"></a>Windows10EndpointProtectionConfiguration. Ремотедесктопсервицеспассвордсавинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/доноталловпассвордсавинг

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespromptforpassworduponconnection"></a>Windows10EndpointProtectionConfiguration. Ремотедесктопсервицеспромптфорпассвордупонконнектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/промптфорпассвордупонконнектион

### <a name="windows10endpointprotectionconfigurationremotedesktopservicessecurerpccommunication"></a>Windows10EndpointProtectionConfiguration. Ремотедесктопсервицессекурерпккоммуникатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотедесктопсервицес/рекуиресекурерпккоммуникатион

### <a name="windows10endpointprotectionconfigurationremotehostdelegationofnonexportablecredentials"></a>Windows10EndpointProtectionConfiguration. Ремотехостделегатионофнонекспортаблекредентиалс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/кредентиалсделегатион/ремотехосталловсделегатионофнонекспортаблекредентиалс

### <a name="windows10endpointprotectionconfigurationremotemanagementclientbasicauthentication"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементклиентбасикаусентикатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**: клиент\_/конфиг/ремотеманажемент/алловбасикаусентикатион

### <a name="windows10endpointprotectionconfigurationremotemanagementclientdigestauthentication"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементклиентдижестаусентикатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотеманажемент/дисалловдижестаусентикатион

### <a name="windows10endpointprotectionconfigurationremotemanagementclientunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементклиентуненкриптедтраффик 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**: клиент\_/конфиг/ремотеманажемент/алловуненкриптедтраффик

### <a name="windows10endpointprotectionconfigurationremotemanagementservicebasicauthentication"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементсервицебасикаусентикатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**: служба\_/конфиг/ремотеманажемент/алловбасикаусентикатион

### <a name="windows10endpointprotectionconfigurationremotemanagementservicestoringrunascredentials"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементсервицесторингрунаскредентиалс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотеманажемент/дисалловсторингофрунаскредентиалс

### <a name="windows10endpointprotectionconfigurationremotemanagementserviceunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration. Ремотеманажементсервицеуненкриптедтраффик 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**: служба\_/конфиг/ремотеманажемент/алловуненкриптедтраффик

### <a name="windows10endpointprotectionconfigurationrpcunauthenticatedclientoptions"></a>Windows10EndpointProtectionConfiguration. Рпкунаусентикатедклиентоптионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотепроцедурекалл/рестриктунаусентикатедрпкклиентс

### <a name="windows10endpointprotectionconfigurationsecurityguideapplyuacrestrictionstolocalaccountsonnetworklogon"></a>Windows10EndpointProtectionConfiguration. Секуритигуидеапплюакрестриктионстолокалаккаунтсоннетворклогон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мссекуритигуиде/апплюакрестриктионстолокалаккаунтсоннетворклогон

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1clientdriverstartconfiguration"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1ClientDriverStartConfiguration 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/config/MSSecurityGuide/ConfigureSMBV1ClientDriver

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1server"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1Server 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/config/MSSecurityGuide/ConfigureSMBV1Server

### <a name="windows10endpointprotectionconfigurationsecurityguidestructuredexceptionhandlingoverwriteprotection"></a>Windows10EndpointProtectionConfiguration. Секуритигуидеструктуредексцептионхандлинговервритепротектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мссекуритигуиде/енаблеструктуредексцептионхандлинговервритепротектион

### <a name="windows10endpointprotectionconfigurationsecurityguidewdigestauthentication"></a>Windows10EndpointProtectionConfiguration. Секуритигуидевдижестаусентикатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/мссекуритигуиде/вдижестаусентикатион

### <a name="windows10endpointprotectionconfigurationsmartscreenblockoverrideforfiles"></a>Windows10EndpointProtectionConfiguration. Смартскринблокковерридефорфилес 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/девицегуард/рекуиреплатформсекуритифеатурес

### <a name="windows10endpointprotectionconfigurationsmartscreenenableinshell"></a>Windows10EndpointProtectionConfiguration. Смартскриненаблеиншелл 
**Поставщик CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **смещения URI**:/конфиг/смартскрин/енаблесмартскрининшелл

### <a name="windows10endpointprotectionconfigurationsolicitedremoteassistance"></a>windows10endpointprotectionconfiguration. СолиЦитедремотеассистанце 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ремотеассистанце/солиЦитедремотеассистанце

### <a name="windows10endpointprotectionconfigurationuserrightsaccesscredentialmanagerastrustedcaller"></a>Windows10EndpointProtectionConfiguration. Усерригхтсакцесскредентиалманажераструстедкаллер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/акцесскредентиалманажераструстедкаллер

### <a name="windows10endpointprotectionconfigurationuserrightsaccessfromnetwork"></a>windows10EndpointProtectionConfiguration. Усерригхтсакцессфромнетворк 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/акцессфромнетворк

### <a name="windows10endpointprotectionconfigurationuserrightsactaspartoftheoperatingsystem"></a>Windows10EndpointProtectionConfiguration. Усерригхтсактаспартофсеоператингсистем 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/актаспартофсеоператингсистем

### <a name="windows10endpointprotectionconfigurationuserrightsallowaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration. Усерригхтсалловакцессфромнетворк 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/акцессфромнетворк

### <a name="windows10endpointprotectionconfigurationuserrightsbackupdata"></a>Windows10EndpointProtectionConfiguration. Усерригхтсбаккупдата 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/баккупфилесанддиректориес

### <a name="windows10endpointprotectionconfigurationuserrightsblockaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration. Усерригхтсблоккакцессфромнетворк 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/денякцессфромнетворк

### <a name="windows10endpointprotectionconfigurationuserrightschangesystemtime"></a>Windows10EndpointProtectionConfiguration. Усерригхтсчанжесистемтиме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/чанжесистемтиме

### <a name="windows10endpointprotectionconfigurationuserrightscreateglobalobjects"></a>Windows10EndpointProtectionConfiguration. Усерригхтскреатеглобалобжектс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/креатеглобалобжектс

### <a name="windows10endpointprotectionconfigurationuserrightscreatepagefile"></a>Windows10EndpointProtectionConfiguration. Усерригхтскреатепажефиле 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/креатепажефиле

### <a name="windows10endpointprotectionconfigurationuserrightscreatepermanentsharedobjects"></a>Windows10EndpointProtectionConfiguration. Усерригхтскреатеперманентшаредобжектс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/креатеперманентшаредобжектс

### <a name="windows10endpointprotectionconfigurationuserrightscreatesymboliclinks"></a>Windows10EndpointProtectionConfiguration. Усерригхтскреатесимболиклинкс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/креатесимболиклинкс

### <a name="windows10endpointprotectionconfigurationuserrightscreatetoken"></a>Windows10EndpointProtectionConfiguration. Усерригхтскреатетокен 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/креатетокен

### <a name="windows10endpointprotectionconfigurationuserrightsdebugprograms"></a>Windows10EndpointProtectionConfiguration. Усерригхтсдебугпрограмс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/дебугпрограмс

### <a name="windows10endpointprotectionconfigurationuserrightsdelegation"></a>Windows10EndpointProtectionConfiguration. Усерригхтсделегатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/енабледелегатион

### <a name="windows10endpointprotectionconfigurationuserrightsdenyaccessfromnetwork"></a>windows10EndpointProtectionConfiguration. Усерригхтсденякцессфромнетворк 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/денякцессфромнетворк

### <a name="windows10endpointprotectionconfigurationuserrightsgeneratesecurityaudits"></a>Windows10EndpointProtectionConfiguration. Усерригхтсженератесекуритяудитс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/женератесекуритяудитс

### <a name="windows10endpointprotectionconfigurationuserrightsimpersonateclient"></a>Windows10EndpointProtectionConfiguration. Усерригхтсимперсонатеклиент 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/имперсонатеклиент

### <a name="windows10endpointprotectionconfigurationuserrightsincreaseschedulingpriority"></a>Windows10EndpointProtectionConfiguration. Усерригхтсинкреасесчедулингприорити 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/инкреасесчедулингприорити

### <a name="windows10endpointprotectionconfigurationuserrightsloadunloaddrivers"></a>Windows10EndpointProtectionConfiguration. Усерригхтслоадунлоаддриверс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/лоадунлоаддевицедриверс

### <a name="windows10endpointprotectionconfigurationuserrightslocallogon"></a>Windows10EndpointProtectionConfiguration. Усерригхтслокаллогон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/алловлокаллогон

### <a name="windows10endpointprotectionconfigurationuserrightslockmemory"></a>Windows10EndpointProtectionConfiguration. Усерригхтслоккмемори 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/локкмемори

### <a name="windows10endpointprotectionconfigurationuserrightsmanageauditingandsecuritylogs"></a>Windows10EndpointProtectionConfiguration. Усерригхтсманажеаудитингандсекуритилогс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/манажеаудитингандсекуритилог

### <a name="windows10endpointprotectionconfigurationuserrightsmanagevolumes"></a>Windows10EndpointProtectionConfiguration. Усерригхтсманажеволумес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/манажеволуме

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyfirmwareenvironment"></a>Windows10EndpointProtectionConfiguration. Усерригхтсмодифифирмваринвиронмент 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/модифифирмваринвиронмент

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyobjectlabels"></a>Windows10EndpointProtectionConfiguration. Усерригхтсмодифйобжектлабелс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/модифйобжектлабел

### <a name="windows10endpointprotectionconfigurationuserrightsprofilesingleprocess"></a>Windows10EndpointProtectionConfiguration. Усерригхтспрофилесинглепроцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/профилесинглепроцесс

### <a name="windows10endpointprotectionconfigurationuserrightsregisterprocessasservice"></a>Windows10EndpointProtectionConfiguration. Усерригхтсрегистерпроцессассервице 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/денилокаллогон

### <a name="windows10endpointprotectionconfigurationuserrightsremotedesktopserviceslogon"></a>Windows10EndpointProtectionConfiguration. Усерригхтсремотедесктопсервицеслогон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/дениремотедесктопсервицеслогон

### <a name="windows10endpointprotectionconfigurationuserrightsremoteshutdown"></a>Windows10EndpointProtectionConfiguration. Усерригхтсремотешутдовн 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/ремотешутдовн

### <a name="windows10endpointprotectionconfigurationuserrightsrestoredata"></a>Windows10EndpointProtectionConfiguration. Усерригхтсресторедата 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/ресторефилесанддиректориес

### <a name="windows10endpointprotectionconfigurationuserrightstakeownership"></a>Windows10EndpointProtectionConfiguration. Усерригхтстакеовнершип 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/усерригхтс/такеовнершип

### <a name="windows10endpointprotectionconfigurationwindowsconnectionmanagerconnectiontonondomainnetworks"></a>Windows10EndpointProtectionConfiguration. Виндовсконнектионманажерконнектионтонондомаиннетворкс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсконнектионманажер/прохитконнектионтонондомаиннетворксвхенконнектедтодомаинаусентикатеднетворк

### <a name="windows10endpointprotectionconfigurationwindowslogonsigninlastinteractiveuseraftersysteminitiatedrestart"></a>Windows10EndpointProtectionConfiguration. Виндовслогонсигнинластинтерактивеусерафтерсистеминитиатедрестарт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовслогон/сигнинластинтерактивеусераутоматикалляфтерасистеминитиатедрестарт

### <a name="windows10endpointprotectionconfigurationxboxservicesaccessorymanagementservicestartupmode"></a>Windows10EndpointProtectionConfiguration. Ксбокссервицесакцессориманажементсервицестартупмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/системсервицес/конфигурексбоксакцессориманажементсервицестартупмоде

### <a name="windows10endpointprotectionconfigurationxboxservicesenablexboxgamesavetask"></a>Windows10EndpointProtectionConfiguration. Ксбокссервицесенаблексбоксгамесаветаск 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/тасксчедулер/енаблексбоксгамесаветаск

### <a name="windows10endpointprotectionconfigurationxboxservicesliveauthmanagerservicestartupmode"></a>Windows10EndpointProtectionConfiguration. Ксбокссервицесливеаусманажерсервицестартупмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/системсервицес/конфигурексбоксливеаусманажерсервицестартупмоде

### <a name="windows10endpointprotectionconfigurationxboxserviceslivegamesaveservicestartupmode"></a>Windows10EndpointProtectionConfiguration. Ксбокссервицесливегамесавесервицестартупмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/системсервицес/ксбокссервицесливегамесавесервицестартупмоде

### <a name="windows10endpointprotectionconfigurationxboxserviceslivenetworkingservicestartupmode"></a>Windows10EndpointProtectionConfiguration. Ксбокссервицесливенетворкингсервицестартупмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/системсервицес/конфигурексбоксливенетворкингсервицестартупмоде

### <a name="windows10enterprisemodernappmanagementconfigurationuninstallbuiltinapps"></a>Windows10EnterpriseModernAppManagementConfiguration. Унинсталлбуилтинаппс
**CSP**: Н/д API Graph **URI смещения**только для вызова: Н/д API Graph только вызов

### <a name="windows10generalconfigurationaccountsblockaddingnonmicrosoftaccountemail"></a>Windows10GeneralConfiguration. Аккаунтсблоккаддингнонмикрософтаккаунтемаил 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аккаунтс/алловаддингнонмикрософтаккаунтсмануалли

### <a name="windows10generalconfigurationantitheftmodeblocked"></a>Windows10GeneralConfiguration. Антисефтмодеблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/антисефтмоде

### <a name="windows10generalconfigurationappmanagementmsiallowusercontroloverinstall"></a>Windows10GeneralConfiguration. Аппманажементмсиалловусерконтроловеринсталл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/мсиалловусерконтроловеринсталл

### <a name="windows10generalconfigurationappmanagementmsialwaysinstallwithelevatedprivileges"></a>Windows10GeneralConfiguration. Аппманажементмсиалвайсинсталлвиселеватедпривилежес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/мсиалвайсинсталлвиселеватедпривилежес

### <a name="windows10generalconfigurationappsallowtrustedappssideloading"></a>Windows10GeneralConfiguration. Аппсалловтрустедаппссиделоадинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловаллтрустедаппс

### <a name="windows10generalconfigurationappsblockwindowsstoreoriginatedapps"></a>Windows10GeneralConfiguration.AppsBlockWindowsStoreOriginatedApps 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/дисаблестореоригинатедаппс

### <a name="windows10generalconfigurationappsmicrosoftaccountsoptional"></a>Windows10GeneralConfiguration. Аппсмикрософтаккаунтсоптионал 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппрунтиме/алловмикрософтаккаунтстобеоптионал

### <a name="windows10generalconfigurationassignedaccessmultimodeprofiles"></a>Windows10GeneralConfiguration. Ассигнедакцессмултимодепрофилес 
**CSP**:./девице/вендор/мсфт/ассигнедакцесс  
**URI смещения**:/Настройка

### <a name="windows10generalconfigurationassignedaccesssinglemodeappusermodelid"></a>Windows10GeneralConfiguration. Ассигнедакцесссинглемодеаппусермоделид 
**CSP**:./девице/вендор/мсфт/ассигнедакцесс  
**URI смещения**:/Настройка

### <a name="windows10generalconfigurationassignedaccesssinglemodeusername"></a>Windows10GeneralConfiguration. Ассигнедакцесссинглемодеусернаме 
**CSP**:./девице/вендор/мсфт/ассигнедакцесс  
**URI смещения**:/Настройка

### <a name="windows10generalconfigurationauthenticationallowfidodevice"></a>Windows10GeneralConfiguration. Аусентикатионалловфидодевице 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аусентикатион/алловфидодевицесигнон

### <a name="windows10generalconfigurationauthenticationallowsecondarydevice"></a>Windows10GeneralConfiguration. Аусентикатионалловсекондаридевице 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аусентикатион/алловсекондаряусентикатиондевице

### <a name="windows10generalconfigurationauthenticationpreferredazureadtenantdomainname"></a>Windows10GeneralConfiguration. Аусентикатионпреферредазуреадтенантдомаиннаме 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аусентикатион/преферредаадтенантдомаиннаме

### <a name="windows10generalconfigurationauthenticationwebsignin"></a>Windows10GeneralConfiguration. Аусентикатионвебсигнин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аусентикатион/енаблевебсигнин

### <a name="windows10generalconfigurationautoplaydefaultautorunbehavior"></a>Windows10GeneralConfiguration. Аутоплайдефаултауторунбехавиор 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аутоплай/сетдефаултауторунбехавиор

### <a name="windows10generalconfigurationautoplayfornonvolumedevices"></a>Windows10GeneralConfiguration. Аутоплайфорнонволумедевицес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аутоплай/дисалловаутоплайфорнонволумедевицес

### <a name="windows10generalconfigurationautoplaymode"></a>Windows10GeneralConfiguration. Аутоплаймоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аутоплай/турноффаутоплай

### <a name="windows10generalconfigurationbluetoothallowedservices"></a>Windows10GeneralConfiguration. Блуетусалловедсервицес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/сервицесалловедлист

### <a name="windows10generalconfigurationbluetoothblockadvertising"></a>Windows10GeneralConfiguration. Блуетусблоккадвертисинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/алловадвертисинг

### <a name="windows10generalconfigurationbluetoothblockdiscoverablemode"></a>Windows10GeneralConfiguration.BluetoothBlockDiscoverableMode 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/алловдисковераблемоде

### <a name="windows10generalconfigurationbluetoothblocked"></a>Windows10GeneralConfiguration. Блуетусблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловблуетус

### <a name="windows10generalconfigurationbluetoothblockprepairing"></a>Windows10GeneralConfiguration. Блуетусблоккпрепаиринг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/алловпрепаиринг

### <a name="windows10generalconfigurationbluetoothblockpromptedproximalconnections"></a>Windows10GeneralConfiguration. Блуетусблоккпромптедпроксималконнектионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/алловпромптедпроксималконнектионс

### <a name="windows10generalconfigurationbluetoothdevicename"></a>Windows10GeneralConfiguration.BluetoothDeviceName 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/блуетус/локалдевиценаме

### <a name="windows10generalconfigurationbootstartdriverinitialization"></a>windows10generalconfiguration. Бутстартдриверинитиализатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/бутстартдриверинитиализатион

### <a name="windows10generalconfigurationcamerablocked"></a>Windows10GeneralConfiguration. Камераблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Камера/алловкамера

### <a name="windows10generalconfigurationcellularblockdatawhenroaming"></a>Windows10GeneralConfiguration. Целлуларблоккдатавхенроаминг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловцеллулардатароаминг

### <a name="windows10generalconfigurationcellularblockvpn"></a>Windows10GeneralConfiguration. Целлуларблокквпн 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловвпноверцеллулар

### <a name="windows10generalconfigurationcellularblockvpnwhenroaming"></a>Windows10GeneralConfiguration. Целлуларблокквпнвхенроаминг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловвпнроаминговерцеллулар

### <a name="windows10generalconfigurationcellulardata"></a>Windows10GeneralConfiguration. Целлулардата 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловцеллулардата

### <a name="windows10generalconfigurationcertificatesblockmanualrootcertificateinstallation"></a>Windows10GeneralConfiguration. Цертификатесблоккмануалрутцертификатеинсталлатион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/алловмануалрутцертификатеинсталлатион

### <a name="windows10generalconfigurationconnecteddevicesserviceblocked"></a>Windows10GeneralConfiguration. Коннектеддевицессервицеблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловконнектеддевицес

### <a name="windows10generalconfigurationcopypasteblocked"></a>Windows10GeneralConfiguration. Копипастеблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловкопипасте

### <a name="windows10generalconfigurationcortanablocked"></a>Windows10GeneralConfiguration. Кортанаблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/абовелокк/алловкортанаабовелокк

### <a name="windows10generalconfigurationcryptographyallowfipsalgorithmpolicy"></a>Windows10GeneralConfiguration.CryptographyAllowFipsAlgorithmPolicy 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/криптографи/алловфипсалгорисмполици

### <a name="windows10generalconfigurationdataprotectionblockdirectmemoryaccess"></a>Windows10GeneralConfiguration. Датапротектионблоккдиректмеморякцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/датапротектион/алловдиректмеморякцесс

### <a name="windows10generalconfigurationdefenderblockenduseraccess"></a>Windows10GeneralConfiguration. Дефендерблоккендусеракцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловусеруиакцесс

### <a name="windows10generalconfigurationdefenderblockonaccessprotection"></a>Windows10GeneralConfiguration. Дефендерблокконакцесспротектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловонакцесспротектион

### <a name="windows10generalconfigurationdefendercloudblocklevel"></a>Windows10GeneralConfiguration. Дефендерклаудблокклевел 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/клаудблокклевел

### <a name="windows10generalconfigurationdefendercloudextendedtimeout"></a>Windows10GeneralConfiguration. Дефендерклаудекстендедтимеаут 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/клаудекстендедтимеаут

### <a name="windows10generalconfigurationdefendercloudextendedtimeoutinseconds"></a>Windows10GeneralConfiguration. Дефендерклаудекстендедтимеаутинсекондс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/клаудекстендедтимеаут

### <a name="windows10generalconfigurationdefenderdaysbeforedeletingquarantinedmalware"></a>Windows10GeneralConfiguration. Дефендердайсбефоределетингкуарантинедмалваре 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/дайсторетаинклеанедмалваре

### <a name="windows10generalconfigurationdefenderdetectedmalwareactions"></a>Windows10GeneralConfiguration. Дефендердетектедмалвареактионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/среатсеверитидефаултактион

### <a name="windows10generalconfigurationdefenderfileextensionstoexclude"></a>Windows10GeneralConfiguration. Дефендерфиликстенсионстоексклуде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/ексклудедекстенсионс

### <a name="windows10generalconfigurationdefenderfilesandfolderstoexclude"></a>Windows10GeneralConfiguration. Дефендерфилесандфолдерстоексклуде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/ексклудедпасс

### <a name="windows10generalconfigurationdefendermonitorfileactivity"></a>Windows10GeneralConfiguration. Дефендермониторфилеактивити 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловреалтимемониторинг

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappaction"></a>Windows10GeneralConfiguration. Дефендерпотентиаллюнвантедаппактион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/пуапротектион

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappactionsetting"></a>Windows10GeneralConfiguration. Дефендерпотентиаллюнвантедаппактионсеттинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/пуапротектион

### <a name="windows10generalconfigurationdefenderprocessestoexclude"></a>Windows10GeneralConfiguration. Дефендерпроцессестоексклуде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/ексклудедпроцессес

### <a name="windows10generalconfigurationdefenderpromptforsamplesubmission"></a>Windows10GeneralConfiguration. Дефендерпромптфорсамплесубмиссион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/субмитсамплесконсент

### <a name="windows10generalconfigurationdefenderrequirebehaviormonitoring"></a>Windows10GeneralConfiguration. Дефендеррекуиребехавиормониторинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловбехавиормониторинг

### <a name="windows10generalconfigurationdefenderrequirecloudprotection"></a>Windows10GeneralConfiguration. Дефендеррекуиреклаудпротектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловклаудпротектион

### <a name="windows10generalconfigurationdefenderrequirenetworkinspectionsystem"></a>Windows10GeneralConfiguration. Дефендеррекуиренетворкинспектионсистем 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловинтрусионпревентионсистем

### <a name="windows10generalconfigurationdefenderrequirerealtimemonitoring"></a>Windows10GeneralConfiguration. Дефендеррекуиререалтимемониторинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловреалтимемониторинг

### <a name="windows10generalconfigurationdefenderscanarchivefiles"></a>Windows10GeneralConfiguration. Дефендерсканарчивефилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловарчивесканнинг

### <a name="windows10generalconfigurationdefenderscandownloads"></a>Windows10GeneralConfiguration. Дефендерскандовнлоадс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловиоавпротектион

### <a name="windows10generalconfigurationdefenderscanincomingmail"></a>Windows10GeneralConfiguration. Дефендерсканинкомингмаил 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловсканнингнетворкфилес

### <a name="windows10generalconfigurationdefenderscanmappednetworkdrivesduringfullscan"></a>Windows10GeneralConfiguration. Дефендерсканмаппеднетворкдривесдурингфуллскан 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловфуллсканонмаппеднетворкдривес

### <a name="windows10generalconfigurationdefenderscanmaxcpu"></a>Windows10GeneralConfiguration. Дефендерсканмакскпу 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/авгкпулоадфактор

### <a name="windows10generalconfigurationdefenderscannetworkfiles"></a>Windows10GeneralConfiguration. Дефендерсканнетворкфилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловсканнингнетворкфилес

### <a name="windows10generalconfigurationdefenderscanremovabledrivesduringfullscan"></a>Windows10GeneralConfiguration. Дефендерсканремовабледривесдурингфуллскан 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловфуллсканремовабледривесканнинг

### <a name="windows10generalconfigurationdefenderscanscriptsloadedininternetexplorer"></a>Windows10GeneralConfiguration. Дефендерсканскриптслоадедининтернетексплорер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/алловскриптсканнинг

### <a name="windows10generalconfigurationdefenderscantype"></a>Windows10GeneralConfiguration. Дефендерскантипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/сканпараметер

### <a name="windows10generalconfigurationdefenderscheduledquickscantime"></a>Windows10GeneralConfiguration. Дефендерсчедуледкуиккскантиме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/счедулекуиккскантиме

### <a name="windows10generalconfigurationdefenderscheduledscantime"></a>Windows10GeneralConfiguration. Дефендерсчедуледскантиме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/счедулескантиме

### <a name="windows10generalconfigurationdefenderschedulescanday"></a>Windows10GeneralConfiguration. Дефендерсчедулескандай 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/счедулескандай

### <a name="windows10generalconfigurationdefendersignatureupdateintervalinhours"></a>Windows10GeneralConfiguration. Дефендерсигнатуреупдатеинтервалинхаурс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/сигнатуреупдатеинтервал

### <a name="windows10generalconfigurationdefendersubmitsamplesconsenttype"></a>Windows10GeneralConfiguration. Дефендерсубмитсамплесконсенттипе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/субмитсамплесконсент

### <a name="windows10generalconfigurationdefendersystemscanschedule"></a>Windows10GeneralConfiguration. Дефендерсистемскансчедуле 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Дефендер/счедулескандай

### <a name="windows10generalconfigurationdeveloperunlocksetting"></a>Windows10GeneralConfiguration. Девелоперунлокксеттинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловдевелоперунлокк

### <a name="windows10generalconfigurationdevicemanagementblockfactoryresetonmobile"></a>Windows10GeneralConfiguration. Девицеманажементблоккфакториресетонмобиле 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/алловусерторесетфоне

### <a name="windows10generalconfigurationdevicemanagementblockmanualunenroll"></a>Windows10GeneralConfiguration. Девицеманажементблоккмануалуненролл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловмануалмдмуненроллмент

### <a name="windows10generalconfigurationdiagnosticsdatasubmissionmode"></a>Windows10GeneralConfiguration. Диагностиксдатасубмиссионмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/алловтелеметри

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedoff"></a>Windows10GeneralConfiguration. Дисплайапплиствисгдидпискалингтурнедофф 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/дисплай/турноффгдидпискалингфораппс

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedon"></a>Windows10GeneralConfiguration. Дисплайапплиствисгдидпискалингтурнедон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/дисплай/турнонгдидпискалингфораппс

### <a name="windows10generalconfigurationedgeallowstartpagesmodification"></a>Windows10GeneralConfiguration. Еджеалловстартпажесмодификатион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/хомепажес

### <a name="windows10generalconfigurationedgeblockaccesstoaboutflags"></a>Windows10GeneralConfiguration. Еджеблоккакцесстоабаутфлагс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентакцесстоабаутфлагсинмикрософтедже

### <a name="windows10generalconfigurationedgeblockaddressbardropdown"></a>Windows10GeneralConfiguration. Еджеблоккаддрессбардропдовн 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловаддрессбардропдовн

### <a name="windows10generalconfigurationedgeblockautofill"></a>Windows10GeneralConfiguration. Еджеблоккаутофилл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловаутофилл

### <a name="windows10generalconfigurationedgeblockcompatibilitylist"></a>Windows10GeneralConfiguration. Еджеблокккомпатибилитилист 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловмикрософткомпатибилитилист

### <a name="windows10generalconfigurationedgeblockdevelopertools"></a>Windows10GeneralConfiguration. Еджеблоккдевелопертулс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловдевелопертулс

### <a name="windows10generalconfigurationedgeblocked"></a>Windows10GeneralConfiguration. Еджеблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловбровсер

### <a name="windows10generalconfigurationedgeblockeditfavorites"></a>Windows10GeneralConfiguration. Еджеблоккедитфаворитес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/локкдовнфаворитес

### <a name="windows10generalconfigurationedgeblockextensions"></a>Windows10GeneralConfiguration. Еджеблоккекстенсионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловекстенсионс

### <a name="windows10generalconfigurationedgeblockfullscreenmode"></a>Windows10GeneralConfiguration. Еджеблоккфуллскринмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловфуллскринмоде

### <a name="windows10generalconfigurationedgeblockinprivatebrowsing"></a>Windows10GeneralConfiguration. Еджеблоккинприватебровсинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловинпривате

### <a name="windows10generalconfigurationedgeblocklivetiledatacollection"></a>Windows10GeneralConfiguration. Еджеблоккливетиледатаколлектион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентливетиледатаколлектион

### <a name="windows10generalconfigurationedgeblockpasswordmanager"></a>Windows10GeneralConfiguration. Еджеблоккпассвордманажер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловпассвордманажер

### <a name="windows10generalconfigurationedgeblockpopups"></a>Windows10GeneralConfiguration. Еджеблоккпопупс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловпопупс

### <a name="windows10generalconfigurationedgeblockprelaunch"></a>Windows10GeneralConfiguration. Еджеблоккпрелаунч 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловпрелаунч

### <a name="windows10generalconfigurationedgeblockprinting"></a>Windows10GeneralConfiguration. Еджеблоккпринтинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловпринтинг

### <a name="windows10generalconfigurationedgeblocksavinghistory"></a>Windows10GeneralConfiguration. Еджеблокксавингхистори 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловсавингхистори

### <a name="windows10generalconfigurationedgeblocksearchsuggestions"></a>Windows10GeneralConfiguration. Еджеблокксеарчсугжестионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловсеарчсугжестионсинаддрессбар

### <a name="windows10generalconfigurationedgeblocksendingdonottrackheader"></a>Windows10GeneralConfiguration. Еджеблокксендингдоноттраккхеадер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловдоноттракк

### <a name="windows10generalconfigurationedgeblocksendingintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration. Еджеблокксендингинтранеттраффиктоинтернетексплорер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сендинтранеттраффиктоинтернетексплорер

### <a name="windows10generalconfigurationedgeblocksideloadingextensions"></a>Windows10GeneralConfiguration. Еджеблокксиделоадинжекстенсионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловсиделоадингофекстенсионс

### <a name="windows10generalconfigurationedgeblocktabpreloading"></a>Windows10GeneralConfiguration. Еджеблокктабпрелоадинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловтабпрелоадинг

### <a name="windows10generalconfigurationedgeblockwebcontentonnewtabpage"></a>Windows10GeneralConfiguration. Еджеблокквебконтентонневтабпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловвебконтентонневтабпаже

### <a name="windows10generalconfigurationedgeclearbrowsingdataonexit"></a>Windows10GeneralConfiguration. Еджеклеарбровсингдатаонексит 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/клеарбровсингдатаонексит

### <a name="windows10generalconfigurationedgecookiepolicy"></a>Windows10GeneralConfiguration. Еджекукиеполици 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловкукиес

### <a name="windows10generalconfigurationedgedisablefirstrunpage"></a>Windows10GeneralConfiguration. Еджедисаблефирструнпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентфирструнпаже

### <a name="windows10generalconfigurationedgeenterprisemodesitelistlocation"></a>Windows10GeneralConfiguration. Еджеентерприсемодесителистлокатион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/ентерприсесителистсервицеурл

### <a name="windows10generalconfigurationedgefavoritesbarvisibility"></a>Windows10GeneralConfiguration. Еджефаворитесбарвисибилити 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/конфигурефаворитесбар

### <a name="windows10generalconfigurationedgefavoriteslistlocation"></a>Windows10GeneralConfiguration. Еджефаворитеслистлокатион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/провисионфаворитес

### <a name="windows10generalconfigurationedgefirstrunurl"></a>Windows10GeneralConfiguration. Еджефирструнурл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/фирструнурл

### <a name="windows10generalconfigurationedgehomebuttonconfiguration"></a>Windows10GeneralConfiguration. Еджехомебуттонконфигуратион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сесомебуттонурл

### <a name="windows10generalconfigurationedgehomebuttonconfigurationenabled"></a>Windows10GeneralConfiguration. Еджехомебуттонконфигуратионенаблед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/конфигурехомебуттон

### <a name="windows10generalconfigurationedgehomepageurls"></a>Windows10GeneralConfiguration. Еджехомепажеурлс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сесомебуттонурл

### <a name="windows10generalconfigurationedgenewtabpageurl"></a>Windows10GeneralConfiguration. Едженевтабпажеурл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сетневтабпажеурл

### <a name="windows10generalconfigurationedgeopenswith"></a>Windows10GeneralConfiguration. Еджеопенсвис 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/конфигуреопенмикрософтеджевис

### <a name="windows10generalconfigurationedgepreventcertificateerroroverride"></a>Windows10GeneralConfiguration. Еджепревентцертификатирророверриде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентцертерророверридес

### <a name="windows10generalconfigurationedgerequiresmartscreen"></a>Windows10GeneralConfiguration. Еджерекуиресмартскрин 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/алловсмартскрин

### <a name="windows10generalconfigurationedgesearchengine"></a>Windows10GeneralConfiguration. Еджесеарченгине 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сетдефаултсеарченгине

### <a name="windows10generalconfigurationedgesendintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration. Еджесендинтранеттраффиктоинтернетексплорер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/сендинтранеттраффиктоинтернетексплорер

### <a name="windows10generalconfigurationedgeshowmessagewhenopeninginternetexplorersites"></a>Windows10GeneralConfiguration. Еджешовмессажевхенопенингинтернетексплорерситес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/шовмессажевхенопенингситесининтернетексплорер

### <a name="windows10generalconfigurationedgesyncfavoriteswithinternetexplorer"></a>Windows10GeneralConfiguration. Еджесинкфаворитесвисинтернетексплорер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/синкфаворитесбетвиниеандмикрософтедже

### <a name="windows10generalconfigurationedgetelemetryformicrosoft365analytics"></a>Windows10GeneralConfiguration.EdgeTelemetryForMicrosoft365Analytics 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/config/Browser/ConfigureTelemetryForMicrosoft365Analytics

### <a name="windows10generalconfigurationenableautomaticredeployment"></a>Windows10GeneralConfiguration. Енаблеаутоматикредеплоймент 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/кредентиалпровидерс/дисаблеаутоматикредеплойменткредентиалс

### <a name="windows10generalconfigurationenterprisecloudprintdiscoveryendpoint"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтдисковерендпоинт 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/клаудпринтердисковерендпоинт

### <a name="windows10generalconfigurationenterprisecloudprintdiscoverymaxlimit"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтдисковеримакслимит 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/дисковеримакспринтерлимит

### <a name="windows10generalconfigurationenterprisecloudprintmopriadiscoveryresourceidentifier"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтмоприадисковериресаурцеидентифиер 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/моприадисковериресаурцеид

### <a name="windows10generalconfigurationenterprisecloudprintoauthauthority"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтоаусаусорити 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/клаудпринтоаусаусорити

### <a name="windows10generalconfigurationenterprisecloudprintoauthclientidentifier"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтоаусклиентидентифиер 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/клаудпринтоаусаусорити

### <a name="windows10generalconfigurationenterprisecloudprintresourceidentifier"></a>Windows10GeneralConfiguration. Ентерприсеклаудпринтресаурцеидентифиер 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ентерприсеклаудпринт/клаудпринтресаурцеид

### <a name="windows10generalconfigurationexperienceblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration. ЕкспериенцеблоккконсумерспеЦификфеатурес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсконсумерфеатурес

### <a name="windows10generalconfigurationexperienceblockdevicediscovery"></a>Windows10GeneralConfiguration. Експериенцеблоккдевицедисковери 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловдевицедисковери

### <a name="windows10generalconfigurationexperienceblockerrordialogwhennosim"></a>Windows10GeneralConfiguration. Експериенцеблоккеррордиалогвхенносим 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловсимеррордиалогпромптвхенносим

### <a name="windows10generalconfigurationexperienceblocktaskswitcher"></a>Windows10GeneralConfiguration. Експериенцеблокктасксвитчер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловтасксвитчер

### <a name="windows10generalconfigurationexperienceblockwindowsspotlight"></a>Windows10GeneralConfiguration. Експериенцеблокквиндовсспотлигхт 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсспотлигхт

### <a name="windows10generalconfigurationexperiencedonotsyncbrowsersettings"></a>Windows10GeneralConfiguration. Експериенцедонотсинкбровсерсеттингс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/донотсинкбровсерсеттингс

### <a name="windows10generalconfigurationgamedvrblocked"></a>Windows10GeneralConfiguration. Гамедврблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловгамедвр

### <a name="windows10generalconfigurationhardwaredeviceinstallationbydeviceidentifiers"></a>Windows10GeneralConfiguration. Хардваредевицеинсталлатионбидевицеидентифиерс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицеинсталлатион/превентинсталлатионофматчингдевицеидс

### <a name="windows10generalconfigurationhardwaredeviceinstallationbysetupclasses"></a>Windows10GeneralConfiguration. Хардваредевицеинсталлатионбисетупклассес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицеинсталлатион/превентинсталлатионофматчингдевицесетупклассес

### <a name="windows10generalconfigurationinkworkspaceaccess"></a>Windows10GeneralConfiguration. Инкворкспацеакцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсинкворкспаце/алловвиндовсинкворкспаце

### <a name="windows10generalconfigurationinkworkspaceaccessstate"></a>Windows10GeneralConfiguration. Инкворкспацеакцессстате 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсинкворкспаце/алловвиндовсинкворкспаце

### <a name="windows10generalconfigurationinkworkspaceblocksuggestedapps"></a>Windows10GeneralConfiguration. Инкворкспацеблокксугжестедаппс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовсинкворкспаце/алловсугжестедаппсинвиндовсинкворкспаце

### <a name="windows10generalconfigurationinternetexploreractivexcontrolsinprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerActiveXControlsInProtectedMode 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/доноталловактивексконтролсинпротектедмоде

### <a name="windows10generalconfigurationinternetexplorerautocomplete"></a>Windows10GeneralConfiguration. Интернетексплорераутокомплете 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/алловаутокомплете

### <a name="windows10generalconfigurationinternetexplorerblockoutdatedactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплорерблоккаутдатедактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/донотблоккаутдатедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarnings"></a>Windows10GeneralConfiguration. Интернетексплорербипасссмартскринварнингс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблебипассофсмартскринварнингс

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarningsaboutuncommonfiles"></a>Windows10GeneralConfiguration. Интернетексплорербипасссмартскринварнингсабаутункоммонфилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблебипассофсмартскринварнингсабаутункоммонфилес

### <a name="windows10generalconfigurationinternetexplorercertificateaddressmismatchwarning"></a>Windows10GeneralConfiguration. Интернетексплорерцертификатеаддрессмисматчварнинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/алловцертификатеаддрессмисматчварнинг

### <a name="windows10generalconfigurationinternetexplorercheckservercertificaterevocation"></a>Windows10GeneralConfiguration. Интернетексплорерчекксерверцертификатеревокатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/чекксерверцертификатеревокатион

### <a name="windows10generalconfigurationinternetexplorerchecksignaturesondownloadedprograms"></a>Windows10GeneralConfiguration. Интернетексплорерчекксигнатуресондовнлоадедпрограмс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/чекксигнатуресондовнлоадедпрограмс

### <a name="windows10generalconfigurationinternetexplorercrashdetection"></a>Windows10GeneralConfiguration. Интернетексплореркрашдетектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблекрашдетектион

### <a name="windows10generalconfigurationinternetexplorerdisableprocessesinenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerDisableProcessesInEnhancedProtectedMode 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблепроцессесиненханцедпротектедмоде

### <a name="windows10generalconfigurationinternetexplorerdownloadenclosures"></a>Windows10GeneralConfiguration. Интернетексплорердовнлоаденклосурес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблинклосуредовнлоадинг

### <a name="windows10generalconfigurationinternetexplorerencryptionsupport"></a>Windows10GeneralConfiguration. Интернетексплореренкриптионсуппорт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблинкриптионсуппорт

### <a name="windows10generalconfigurationinternetexplorerenhancedprotectedmode"></a>Windows10GeneralConfiguration. Интернетексплореренханцедпротектедмоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/алловенханцедпротектедмоде

### <a name="windows10generalconfigurationinternetexplorerfallbacktossl3"></a>Windows10GeneralConfiguration.InternetExplorerFallbackToSsl3 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/config/InternetExplorer/AllowFallbackToSSL3

### <a name="windows10generalconfigurationinternetexplorerignorecertificateerrors"></a>Windows10GeneralConfiguration. Интернетексплореригнорецертификатиррорс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблеигнорингцертификатиррорс

### <a name="windows10generalconfigurationinternetexplorerincludeallnetworkpaths"></a>Windows10GeneralConfiguration. Интернетексплореринклудеаллнетворкпасс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/инклудеаллнетворкпасс

### <a name="windows10generalconfigurationinternetexplorerinternetzoneaccesstodatasources"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеакцесстодатасаурцес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловакцесстодатасаурцес

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловонляппроведдомаинстаусеактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловонляппроведдомаинстаусетдкактивексконтрол

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowvbscripttorun"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеалловвбскриптторун 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловвбскриптторунининтернетексплорер

### <a name="windows10generalconfigurationinternetexplorerinternetzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеаутоматикпромптфорфиледовнлоадс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловаутоматикпромптингфорфиледовнлоадс

### <a name="windows10generalconfigurationinternetexplorerinternetzonecopyandpasteviascript"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонекопяндпастевиаскрипт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловкопипастевиаскрипт

### <a name="windows10generalconfigurationinternetexplorerinternetzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонекроссситескриптингфилтер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонинаблекроссситескриптингфилтер

### <a name="windows10generalconfigurationinternetexplorerinternetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонедонотрунантималвареагаинстактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонедотнетфрамеворкрелианткомпонентс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловнетфрамеворкрелианткомпонентс

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadSignedActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонедовнлоадсигнедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadUnsignedActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонедовнлоадунсигнедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонедраганддропоркопяндпастефилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловдраганддропкопяндпастефилес

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонедрагконтентфромдифферентдомаинсакроссвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонинабледраггингофконтентфромдифферентдомаинсакроссвиндовс

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонедрагконтентфромдифферентдомаинсвисинвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонинабледраггингофконтентфромдифферентдомаинсвисинвиндовс

### <a name="windows10generalconfigurationinternetexplorerinternetzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеинклуделокалпасвхенуплоадингфилестосервер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеинклуделокалпасвхенуплоадингфилестосервер

### <a name="windows10generalconfigurationinternetexplorerinternetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеинитиализеандскриптактивексконтролснотмаркедассафе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеинитиализеандскриптактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонежавапермиссионс


### <a name="windows10generalconfigurationinternetexplorerinternetzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонелаунчаппликатионсандфилесинанифраме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонелаунчингаппликатионсандфилесинифраме

### <a name="windows10generalconfigurationinternetexplorerinternetzonelessprivilegedsites"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонелесспривилежедситес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловлесспривилежедситес

### <a name="windows10generalconfigurationinternetexplorerinternetzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLoadingOfXamlFiles 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловлоадингофксамлфилес

### <a name="windows10generalconfigurationinternetexplorerinternetzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLogonOptions 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонелогоноптионс

### <a name="windows10generalconfigurationinternetexplorerinternetzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзоненавигатевиндовсандфрамесакроссдифферентдомаинс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзоненавигатевиндовсандфрамес

### <a name="windows10generalconfigurationinternetexplorerinternetzonepopupblocker"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонепопупблоккер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеусепопупблоккер

### <a name="windows10generalconfigurationinternetexplorerinternetzoneprotectedmode"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонепротектедмоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонинаблепротектедмоде

### <a name="windows10generalconfigurationinternetexplorerinternetzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонерундотнетфрамеворкрелианткомпонентссигнедвисаусентикоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеруннетфрамеворкрелианткомпонентссигнедвисаусентикоде

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонескриптингофвеббровсерконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловскриптингофинтернетексплорервеббровсерконтролс

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонескриптинитиатедвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловскриптинитиатедвиндовс

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptlets"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонескриптлетс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловскриптлетс

### <a name="windows10generalconfigurationinternetexplorerinternetzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонесекуритиварнингфорпотентиаллюнсафефилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонешовсекуритиварнингфорпотентиаллюнсафефилес

### <a name="windows10generalconfigurationinternetexplorerinternetzonesmartscreen"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонесмартскрин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловсмартскриние

### <a name="windows10generalconfigurationinternetexplorerinternetzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration. Интернетексплореринтернетзонеупдатестостатусбарвиаскрипт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловупдатестостатусбарвиаскрипт

### <a name="windows10generalconfigurationinternetexplorerinternetzoneuserdatapersistence"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUserDataPersistence 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интернетзонеалловусердатаперсистенце

### <a name="windows10generalconfigurationinternetexplorerintranetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплореринтранетзонедонотрунантималвареагаинстактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интранетзонедонотрунантималвареагаинстактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerintranetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration. Интернетексплореринтранетзонеинитиализеандскриптактивексконтролснотмаркедассафе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интранетзонеинитиализеандскриптактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerintranetzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплореринтранетзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/интранетзонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплорерлокалмачинезонедонотрунантималвареагаинстактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локалмачинезонедонотрунантималвареагаинстактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорерлокалмачинезонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локалмачинезонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerlockeddowninternetzonesmartscreen"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнинтернетзонесмартскрин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнинтернетзонеалловсмартскриние

### <a name="windows10generalconfigurationinternetexplorerlockeddownintranetzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнинтранетзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнинтранетжавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerlockeddownlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнлокалмачинезонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнлокалмачинезонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнрестриктедзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнрестриктедситесзонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнрестриктедзонесмартскрин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнрестриктедситесзонеалловсмартскриние

### <a name="windows10generalconfigurationinternetexplorerlockeddowntrustedzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорерлоккеддовнтрустедзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/локкеддовнтрустедситесзонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerpreventmanagingsmartscreenfilter"></a>Windows10GeneralConfiguration. Интернетексплорерпревентманагингсмартскринфилтер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/превентманагингсмартскринфилтер

### <a name="windows10generalconfigurationinternetexplorerpreventperuserinstallationofactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerPreventPerUserInstallationOfActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/превентперусеринсталлатионофактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerprocessesconsistentmimehandling"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессесконсистентмимехандлинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/консистентмимехандлингинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesmimesniffingsafetyfeature"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMimeSniffingSafetyFeature 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/мимесниффингсафетифеатуреинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesmkprotocolsecurityrestriction"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессесмкпротоколсекуритирестриктион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/мкпротоколсекуритирестриктионинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesnotificationbar"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессеснотификатионбар 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/нотификатионбаринтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesprotectionfromzoneelevation"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессеспротектионфромзонилеватион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/протектионфромзонилеватионинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictactivexinstall"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессесрестриктактивексинсталл 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктактивексинсталлинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictfiledownload"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессесрестриктфиледовнлоад 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктфиледовнлоадинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerprocessesscriptedwindowsecurityrestrictions"></a>Windows10GeneralConfiguration. Интернетексплорерпроцессесскриптедвиндовсекуритирестриктионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/скриптедвиндовсекуритирестриктионсинтернетексплорерпроцессес

### <a name="windows10generalconfigurationinternetexplorerremoverunthistimebuttonforoutdatedactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплорерремоверунсистимебуттонфораутдатедактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/ремоверунсистимебуттонфораутдатедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneaccesstodatasources"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеакцесстодатасаурцес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловакцесстодатасаурцес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneactivescripting"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеактивескриптинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловактивескриптинг

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеалловонляппроведдомаинстаусеактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловонляппроведдомаинстаусеактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловонляппроведдомаинстаусетдкактивексконтрол

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowvbscripttorun"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеалловвбскриптторун 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловвбскриптторунининтернетексплорер

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеаутоматикпромптфорфиледовнлоадс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловаутоматикпромптингфорфиледовнлоадс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonebinaryandscriptbehaviors"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонебинаряндскриптбехавиорс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловбинаряндскриптбехавиорс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecopyandpasteviascript"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонекопяндпастевиаскрипт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловкопипастевиаскрипт

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонекроссситескриптингфилтер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонинаблекроссситескриптингфилтер

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедонотрунантималвареагаинстактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонедонотрунантималвареагаинстактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедотнетфрамеворкрелианткомпонентс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловнетфрамеворкрелианткомпонентс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедовнлоадсигнедактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонедовнлоадсигнедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadUnsignedActiveXControls 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонедовнлоадунсигнедактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедраганддропоркопяндпастефилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловдраганддропкопяндпастефилес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедрагконтентфромдифферентдомаинсакроссвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонинабледраггингофконтентфромдифферентдомаинсакроссвиндовс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонедрагконтентфромдифферентдомаинсвисинвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонинабледраггингофконтентфромдифферентдомаинсвисинвиндовс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonefiledownloads"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонефиледовнлоадс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловфиледовнлоадс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеинклуделокалпасвхенуплоадингфилестосервер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеинклуделокалпасвхенуплоадингфилестосервер

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеинитиализеандскриптактивексконтролснотмаркедассафе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеинитиализеандскриптактивексконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонежавапермиссионс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонелаунчаппликатионсандфилесинанифраме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонелаунчингаппликатионсандфилесинифраме

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelessprivilegedsites"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонелесспривилежедситес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловлесспривилежедситес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонелоадингофксамлфилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловлоадингофксамлфилес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelogonoptions"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонелогоноптионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонелогоноптионс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonemetarefresh"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеметарефреш 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловметарефреш

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзоненавигатевиндовсандфрамесакроссдифферентдомаинс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзоненавигатевиндовсандфрамес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonepopupblocker"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонепопупблоккер 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеусепопупблоккер

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneprotectedmode"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонепротектедмоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонетурнонпротектедмоде

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerunactivexcontrolsandplugins"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонерунактивексконтролсандплугинс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонерунактивексконтролсандплугинс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонерундотнетфрамеворкрелианткомпонентссигнедвисаусентикоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеруннетфрамеворкрелианткомпонентссигнедвисаусентикоде

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptactivexcontrolsmarkedsafeforscripting"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонескриптактивексконтролсмаркедсафефорскриптинг 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонескриптактивексконтролсмаркедсафефорскриптинг

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofjavaapplets"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонескриптингофжаваапплетс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонескриптингофжаваапплетс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонескриптингофвеббровсерконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловскриптингофинтернетексплорервеббровсерконтролс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонескриптинитиатедвиндовс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловскриптинитиатедвиндовс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptlets"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонескриптлетс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловскриптлетс

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонесекуритиварнингфорпотентиаллюнсафефилес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонешовсекуритиварнингфорпотентиаллюнсафефилес

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонесмартскрин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловсмартскриние

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеупдатестостатусбарвиаскрипт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловупдатестостатусбарвиаскрипт

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneuserdatapersistence"></a>Windows10GeneralConfiguration. Интернетексплореррестриктедзонеусердатаперсистенце 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/рестриктедситесзонеалловусердатаперсистенце

### <a name="windows10generalconfigurationinternetexplorersecuritysettingscheck"></a>Windows10GeneralConfiguration. Интернетексплорерсекуритисеттингсчекк 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/дисаблесекуритисеттингсчекк

### <a name="windows10generalconfigurationinternetexplorersecurityzonesuseonlymachinesettings"></a>Windows10GeneralConfiguration. Интернетексплорерсекуритизонесусеонлимачинесеттингс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/секуритизонесусеонлимачинесеттингс

### <a name="windows10generalconfigurationinternetexplorersoftwarewhensignatureisinvalid"></a>Windows10GeneralConfiguration. Интернетексплорерсофтваревхенсигнатуреисинвалид 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/алловсофтваревхенсигнатуреисинвалид

### <a name="windows10generalconfigurationinternetexplorertrustedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration. Интернетексплорертрустедзонедонотрунантималвареагаинстактивексконтролс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/трустедситесзонедонотрунантималвареагаинстактивексконтролс

### <a name="windows10generalconfigurationinternetexplorertrustedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration. Интернетексплорертрустедзонеинитиализеандскриптактивексконтролснотмаркедассафе 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/трустедситесзонеинитиализеандскриптактивексконтролс

### <a name="windows10generalconfigurationinternetexplorertrustedzonejavapermissions"></a>Windows10GeneralConfiguration. Интернетексплорертрустедзонежавапермиссионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/трустедситесзонежавапермиссионс

### <a name="windows10generalconfigurationinternetexploreruseactivexinstallerservice"></a>Windows10GeneralConfiguration. Интернетексплорерусеактивексинсталлерсервице 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/спеЦифюсеофактивексинсталлерсервице

### <a name="windows10generalconfigurationinternetexplorerusersaddingsites"></a>Windows10GeneralConfiguration. Интернетексплорерусерсаддингситес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/доноталловусерстоаддситес

### <a name="windows10generalconfigurationinternetexploreruserschangingpolicies"></a>Windows10GeneralConfiguration. ИнтернетексплорерусерсчангингполиЦиес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/интернетексплорер/доноталловусерсточанжеполиЦиес

### <a name="windows10generalconfigurationinternetsharingblocked"></a>Windows10GeneralConfiguration. Интернетшарингблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/ВИФИ/алловинтернетшаринг

### <a name="windows10generalconfigurationlocationservicesblocked"></a>Windows10GeneralConfiguration. Локатионсервицесблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/алловлокатион

### <a name="windows10generalconfigurationlockscreenallowtimeoutconfiguration"></a>Windows10GeneralConfiguration. Локкскриналловтимеаутконфигуратион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/алловскринтимеаутвхилелоккедусер/конфиг

### <a name="windows10generalconfigurationlockscreenblockactioncenternotifications"></a>Windows10GeneralConfiguration. Локкскринблоккактионцентернотификатионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/абовелокк/алловактионцентернотификатионс

### <a name="windows10generalconfigurationlockscreenblockcortana"></a>Windows10GeneralConfiguration. Локкскринблокккортана 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/абовелокк/алловкортанаабовелокк

### <a name="windows10generalconfigurationlockscreenblocktoastnotifications"></a>Windows10GeneralConfiguration. Локкскринблокктоастнотификатионс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/абовелокк/алловтоастс

### <a name="windows10generalconfigurationlockscreencamera"></a>Windows10GeneralConfiguration. Локкскринкамера 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/превентенаблинглоккскринкамера

### <a name="windows10generalconfigurationlockscreenhidenetworkselectionui"></a>Windows10GeneralConfiguration. Локкскринхиденетворкселектионуи 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовслогон/донтдисплайнетворкселектионуи

### <a name="windows10generalconfigurationlockscreenslideshow"></a>Windows10GeneralConfiguration. Локкскринслидешов 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/превентлоккскринслидешов

### <a name="windows10generalconfigurationlockscreentimeoutinseconds"></a>Windows10GeneralConfiguration. Локкскринтимеаутинсекондс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/скринтимеаутвхилелоккед

### <a name="windows10generalconfigurationlogonblockfastuserswitching"></a>Windows10GeneralConfiguration. Логонблоккфастусерсвитчинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовслогон/хидефастусерсвитчинг

### <a name="windows10generalconfigurationmessagingblockmms"></a>Windows10GeneralConfiguration. Мессагингблоккммс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/мессагинг/алловммс

### <a name="windows10generalconfigurationmessagingblockrichcommunicationservices"></a>Windows10GeneralConfiguration. Мессагингблоккричкоммуникатионсервицес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/мессагинг/алловркс

### <a name="windows10generalconfigurationmessagingblocksync"></a>Windows10GeneralConfiguration. Мессагингблокксинк 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/мессагинг/алловмессажесинк

### <a name="windows10generalconfigurationmicrosoftaccountblocked"></a>Windows10GeneralConfiguration. Микрософтаккаунтблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аккаунтс/алловмикрософтаккаунтконнектион

### <a name="windows10generalconfigurationmicrosoftaccountblocksettingssync"></a>Windows10GeneralConfiguration. Микрософтаккаунтблокксеттингссинк 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловсинкмисеттингс

### <a name="windows10generalconfigurationmicrosoftaccountsigninassistantsettings"></a>Windows10GeneralConfiguration. Микрософтаккаунтсигнинассистантсеттингс 
**CSP**:./девице/вендор/мсфт/аккаунтс  
**URI смещения**:/алловмикрософтаккаунтсигнинассистант

### <a name="windows10generalconfigurationnetworkproxyapplysettingsdevicewide"></a>Windows10GeneralConfiguration. Нетворкпроксяпплисеттингсдевицевиде 
**CSP**:./девице/вендор/мсфт/нетворкпрокси  
**URI смещения**:/проксисеттингсперусер

### <a name="windows10generalconfigurationnetworkproxyautomaticconfigurationurl"></a>Windows10GeneralConfiguration. Нетворкпроксяутоматикконфигуратионурл 
**CSP**:./девице/вендор/мсфт/нетворкпрокси  
**URI смещения**:/сетупскриптурл

### <a name="windows10generalconfigurationnetworkproxydisableautodetect"></a>Windows10GeneralConfiguration. Нетворкпроксидисаблеаутодетект 
**CSP**:./девице/вендор/мсфт/нетворкпрокси  
**URI смещения**:/аутодетект

### <a name="windows10generalconfigurationnetworkproxyserver"></a>Windows10GeneralConfiguration. Нетворкпроксисервер 
**CSP**:./вендор/мсфт/нетворкпрокси  
**URI смещения**:/proxyAddress,/Ексцептионс и/усепроксифорлокаладдрессес

### <a name="windows10generalconfigurationnfcblocked"></a>Windows10GeneralConfiguration. Нфкблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловнфк

### <a name="windows10generalconfigurationonedrivedisablefilesync"></a>Windows10GeneralConfiguration. Онедриведисаблефилесинк 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/дисаблеонедривефилесинк

### <a name="windows10generalconfigurationpasswordblocksimple"></a>Windows10GeneralConfiguration. Пассвордблокксимпле 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/алловсимпледевицепассворд

### <a name="windows10generalconfigurationpasswordexpirationdays"></a>Windows10GeneralConfiguration. Пассвордекспиратиондайс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/девицепассвордекспиратион

### <a name="windows10generalconfigurationpasswordminimumageindays"></a>Windows10GeneralConfiguration. Пассвордминимумажеиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/минимумпассвордаже

### <a name="windows10generalconfigurationpasswordminimumcharactersetcount"></a>Windows10GeneralConfiguration. Пассвордминимумчарактерсеткаунт 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/миндевицепассвордкомплексчарактерс

### <a name="windows10generalconfigurationpasswordminimumlength"></a>Windows10GeneralConfiguration. Пассвордминимумленгс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/миндевицепассвордленгс

### <a name="windows10generalconfigurationpasswordminutesofinactivitybeforescreentimeout"></a>Windows10GeneralConfiguration. Пассвордминутесофинактивитибефорескринтимеаут 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/максинактивититимедевицелокк

### <a name="windows10generalconfigurationpasswordpreviouspasswordblockcount"></a>Windows10GeneralConfiguration. Пассвордпревиауспассвордблокккаунт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/девицепассвордхистори

### <a name="windows10generalconfigurationpasswordrequired"></a>Windows10GeneralConfiguration. Пассвордрекуиред 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/девицепассворденаблед

### <a name="windows10generalconfigurationpasswordrequiredtype"></a>Windows10GeneralConfiguration. Пассвордрекуиредтипе 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/алфанумерикдевицепассвордрекуиред

### <a name="windows10generalconfigurationpasswordrequirewhenresumefromidlestate"></a>Windows10GeneralConfiguration. Пассвордрекуиревхенресумефромидлестате 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/алловидлеретурнвисаутпассворд

### <a name="windows10generalconfigurationpasswordsigninfailurecountbeforefactoryreset"></a>Windows10GeneralConfiguration.PasswordSignInFailureCountBeforeFactoryReset 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицелокк/максдевицепассвордфаиледаттемптс

### <a name="windows10generalconfigurationpersonalizationdesktopimageurl"></a>Windows10GeneralConfiguration. Персонализатиондесктопимажеурл 
**CSP**:./девице/вендор/мсфт/персонализатион  
**URI смещения**:/десктопимажеурл

### <a name="windows10generalconfigurationpersonalizationlockscreenimageurl"></a>Windows10GeneralConfiguration. Персонализатионлоккскринимажеурл 
**CSP**:./девице/вендор/мсфт/персонализатион  
**URI смещения**:/локкскринимажеурл

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhileonbattery"></a>Windows10GeneralConfiguration. Поверрекуирепассвордонвакевхилеонбаттери 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/повер/рекуирепассвордвхенкомпутервакесонбаттери

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhilepluggedin"></a>Windows10GeneralConfiguration. Поверрекуирепассвордонвакевхилеплугжедин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/повер/рекуирепассвордвхенкомпутервакесплугжедин

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhileonbattery"></a>Windows10GeneralConfiguration. Поверстандбистатесвхенслипингвхилеонбаттери 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/повер/алловстандбистатесвхенслипингонбаттери

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhilepluggedin"></a>Windows10GeneralConfiguration. Поверстандбистатесвхенслипингвхилеплугжедин 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/повер/алловстандбивхенслипингплугжедин

### <a name="windows10generalconfigurationpreventinstallationofmatchingdeviceids"></a>windows10generalconfiguration. Превентинсталлатионофматчингдевицеидс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицеинсталлатион/превентинсталлатионофматчингдевицеидс

### <a name="windows10generalconfigurationpreventinstallationofmatchingdevicesetupclasses"></a>windows10generalconfiguration. Превентинсталлатионофматчингдевицесетупклассес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/девицеинсталлатион/превентинсталлатионофматчингдевицесетупклассес

### <a name="windows10generalconfigurationprinterblockaddition"></a>Windows10GeneralConfiguration. Принтерблоккаддитион 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/едукатион/превентаддингневпринтерс

### <a name="windows10generalconfigurationprinterdefaultname"></a>Windows10GeneralConfiguration. Принтердефаултнаме 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/едукатион/дефаултпринтернаме

### <a name="windows10generalconfigurationprinternames"></a>Windows10GeneralConfiguration. Принтернамес 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/едукатион/принтернамес

### <a name="windows10generalconfigurationprivacyadvertisingid"></a>Windows10GeneralConfiguration. Привациадвертисингид 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/приваци/дисаблеадвертисингид

### <a name="windows10generalconfigurationprivacyautoacceptpairingandconsentprompts"></a>Windows10GeneralConfiguration. Привациаутоакцептпаирингандконсентпромптс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/приваци/алловаутоакцептпаирингандпривациконсентпромптс

### <a name="windows10generalconfigurationprivacyblockactivityfeed"></a>Windows10GeneralConfiguration. Привациблоккактивитифид 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/приваци/енаблеактивитифид

### <a name="windows10generalconfigurationprivacyblockinputpersonalization"></a>Windows10GeneralConfiguration. Привациблоккинпутперсонализатион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/приваци/алловинпутперсонализатион

### <a name="windows10generalconfigurationprivacyblockpublishuseractivities"></a>Windows10GeneralConfiguration. Привациблоккпублишусерактивитиес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/приваци/публишусерактивитиес

### <a name="windows10generalconfigurationsafesearchfilter"></a>Windows10GeneralConfiguration. Сафесеарчфилтер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/сафесеарчпермиссионс

### <a name="windows10generalconfigurationscreencaptureblocked"></a>Windows10GeneralConfiguration. Скринкаптуреблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловскринкаптуре

### <a name="windows10generalconfigurationsearchblockdiacritics"></a>Windows10GeneralConfiguration. Сеарчблоккдиакритикс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/алловусингдиакритикс

### <a name="windows10generalconfigurationsearchblockwebresults"></a>Windows10GeneralConfiguration. Сеарчблокквебресултс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/донотусевебресултс

### <a name="windows10generalconfigurationsearchdisableautolanguagedetection"></a>Windows10GeneralConfiguration. Сеарчдисаблеаутолангуажедетектион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/алвайсусеаутолангдетектион

### <a name="windows10generalconfigurationsearchdisableindexerbackoff"></a>Windows10GeneralConfiguration. Сеарчдисаблеиндексербаккофф 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/дисаблебаккофф

### <a name="windows10generalconfigurationsearchdisableindexingencrypteditems"></a>Windows10GeneralConfiguration. Сеарчдисаблеиндексинженкриптедитемс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/алловиндексинженкриптедсторесоритемс

### <a name="windows10generalconfigurationsearchdisableindexingremovabledrive"></a>Windows10GeneralConfiguration. Сеарчдисаблеиндексингремовабледриве 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/дисаблеремовабледривеиндексинг

### <a name="windows10generalconfigurationsearchdisablelocation"></a>Windows10GeneralConfiguration. Сеарчдисаблелокатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/алловсеарчтауселокатион

### <a name="windows10generalconfigurationsearchdisableuselocation"></a>Windows10GeneralConfiguration. Сеарчдисаблеуселокатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/алловсеарчтауселокатион

### <a name="windows10generalconfigurationsearchenableautomaticindexsizemanangement"></a>Windows10GeneralConfiguration. СеарченаблеаутоматиЦиндекссиземананжемент 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/превентиндексингловдискспацемб

### <a name="windows10generalconfigurationsearchenableremotequeries"></a>Windows10GeneralConfiguration. Сеарченаблеремотекуериес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/СЕАРЧ/превентремотекуериес

### <a name="windows10generalconfigurationsecurityblockazureadjoineddevicesautoencryption"></a>Windows10GeneralConfiguration. Секуритиблокказуреаджоинеддевицесаутоенкриптион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/превентаутоматикдевицеенкриптионфоразуреаджоинеддевицес

### <a name="windows10generalconfigurationsettingsblockaccountspage"></a>Windows10GeneralConfiguration. Сеттингсблоккаккаунтспаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockaddprovisioningpackage"></a>Windows10GeneralConfiguration. Сеттингсблоккаддпровисионингпаккаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/алловаддпровисионингпаккаже

### <a name="windows10generalconfigurationsettingsblockappspage"></a>Windows10GeneralConfiguration. Сеттингсблоккаппспаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockchangelanguage"></a>Windows10GeneralConfiguration. Сеттингсблоккчанжелангуаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/алловлангуаже

### <a name="windows10generalconfigurationsettingsblockchangepowersleep"></a>Windows10GeneralConfiguration. Сеттингсблоккчанжеповерслип 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/алловповерслип

### <a name="windows10generalconfigurationsettingsblockchangeregion"></a>Windows10GeneralConfiguration. Сеттингсблоккчанжерегион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/алловрегион

### <a name="windows10generalconfigurationsettingsblockchangesystemtime"></a>Windows10GeneralConfiguration. Сеттингсблоккчанжесистемтиме 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/алловдатетиме

### <a name="windows10generalconfigurationsettingsblockdevicespage"></a>Windows10GeneralConfiguration. Сеттингсблоккдевицеспаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockeaseofaccesspage"></a>Windows10GeneralConfiguration. Сеттингсблоккеасеофакцесспаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockeditdevicename"></a>Windows10GeneralConfiguration. Сеттингсблоккедитдевиценаме 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/алловедитдевиценаме

### <a name="windows10generalconfigurationsettingsblockgamingpage"></a>Windows10GeneralConfiguration. Сеттингсблоккгамингпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblocknetworkinternetpage"></a>Windows10GeneralConfiguration. Сеттингсблоккнетворкинтернетпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockpersonalizationpage"></a>Windows10GeneralConfiguration. Сеттингсблоккперсонализатионпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockprivacypage"></a>Windows10GeneralConfiguration. Сеттингсблоккприваципаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockremoveprovisioningpackage"></a>Windows10GeneralConfiguration. Сеттингсблоккремовепровисионингпаккаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/алловремовепровисионингпаккаже

### <a name="windows10generalconfigurationsettingsblocksystempage"></a>Windows10GeneralConfiguration. Сеттингсблокксистемпаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblocktimelanguagepage"></a>Windows10GeneralConfiguration. Сеттингсблокктимелангуажепаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationsettingsblockupdatesecuritypage"></a>Windows10GeneralConfiguration. Сеттингсблоккупдатесекуритипаже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Сеттингс/пажевисибилитилист

### <a name="windows10generalconfigurationshareduserappdataallowed"></a>Windows10GeneralConfiguration. Шаредусераппдатаалловед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловшаредусераппдата

### <a name="windows10generalconfigurationsmartscreenblockpromptoverride"></a>Windows10GeneralConfiguration. Смартскринблоккпромптоверриде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентсмартскринпромптоверриде

### <a name="windows10generalconfigurationsmartscreenblockpromptoverrideforfiles"></a>Windows10GeneralConfiguration. Смартскринблоккпромптоверридефорфилес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентсмартскринпромптоверридефорфилес

### <a name="windows10generalconfigurationsmartscreenenableappinstallcontrol"></a>Windows10GeneralConfiguration. Смартскриненаблеаппинсталлконтрол 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/смартскрин/енаблеаппинсталлконтрол

### <a name="windows10generalconfigurationstartblockunpinningappsfromtaskbar"></a>Windows10GeneralConfiguration. Стартблоккунпиннингаппсфромтаскбар 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/нопиннингтотаскбар

### <a name="windows10generalconfigurationstartmenuapplistvisibility"></a>Windows10GeneralConfiguration. Стартменуапплиствисибилити 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидеапплист

### <a name="windows10generalconfigurationstartmenuhidechangeaccountsettings"></a>Windows10GeneralConfiguration. Стартменухидечанжеаккаунтсеттингс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидечанжеаккаунтсеттингс

### <a name="windows10generalconfigurationstartmenuhidefrequentlyusedapps"></a>Windows10GeneralConfiguration. Стартменухидефрекуентлюседаппс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидефрекуентлюседаппс

### <a name="windows10generalconfigurationstartmenuhidehibernate"></a>Windows10GeneralConfiguration. Стартменухидехибернате 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидехибернате

### <a name="windows10generalconfigurationstartmenuhidelock"></a>Windows10GeneralConfiguration. Стартменухиделокк 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хиделокк

### <a name="windows10generalconfigurationstartmenuhidepowerbutton"></a>Windows10GeneralConfiguration. Стартменухидеповербуттон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидеповербуттон

### <a name="windows10generalconfigurationstartmenuhiderecentjumplists"></a>Windows10GeneralConfiguration. Стартменухидерецентжумплистс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидерецентжумплистс

### <a name="windows10generalconfigurationstartmenuhiderecentlyaddedapps"></a>Windows10GeneralConfiguration. Стартменухидерецентляддедаппс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидерецентляддедаппс

### <a name="windows10generalconfigurationstartmenuhiderestartoptions"></a>Windows10GeneralConfiguration. Стартменухидерестартоптионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидерестарт

### <a name="windows10generalconfigurationstartmenuhideshutdown"></a>Windows10GeneralConfiguration. Стартменухидешутдовн 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидешутдовн

### <a name="windows10generalconfigurationstartmenuhidesignout"></a>Windows10GeneralConfiguration. Стартменухидесигнаут 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидесигнаут

### <a name="windows10generalconfigurationstartmenuhidesleep"></a>Windows10GeneralConfiguration. Стартменухидеслип 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидеслип

### <a name="windows10generalconfigurationstartmenuhideswitchaccount"></a>Windows10GeneralConfiguration. Стартменухидесвитчаккаунт 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидесвитчаккаунт

### <a name="windows10generalconfigurationstartmenuhideusertile"></a>Windows10GeneralConfiguration. Стартменухидеусертиле 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/хидеусертиле

### <a name="windows10generalconfigurationstartmenulayoutedgeassetsxml"></a>Windows10GeneralConfiguration. Стартменулайаутеджеассетсксмл 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/импортеджеассетс

### <a name="windows10generalconfigurationstartmenulayoutxml"></a>Windows10GeneralConfiguration. Стартменулайаутксмл 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/стартлайаут

### <a name="windows10generalconfigurationstartmenumode"></a>Windows10GeneralConfiguration. Стартменумоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/форцестартсизе

### <a name="windows10generalconfigurationstartmenupinnedfolderdocuments"></a>Windows10GeneralConfiguration. Стартменупиннедфолдердокументс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдердокументс

### <a name="windows10generalconfigurationstartmenupinnedfolderdownloads"></a>Windows10GeneralConfiguration. Стартменупиннедфолдердовнлоадс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдердовнлоадс

### <a name="windows10generalconfigurationstartmenupinnedfolderfileexplorer"></a>Windows10GeneralConfiguration. Стартменупиннедфолдерфиликсплорер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдерфиликсплорер

### <a name="windows10generalconfigurationstartmenupinnedfolderhomegroup"></a>Windows10GeneralConfiguration. Стартменупиннедфолдерхомеграуп 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдерхомеграуп

### <a name="windows10generalconfigurationstartmenupinnedfoldermusic"></a>Windows10GeneralConfiguration. Стартменупиннедфолдермусик 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдермусик

### <a name="windows10generalconfigurationstartmenupinnedfoldernetwork"></a>Windows10GeneralConfiguration. Стартменупиннедфолдернетворк 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдернетворк

### <a name="windows10generalconfigurationstartmenupinnedfolderpersonalfolder"></a>Windows10GeneralConfiguration. Стартменупиннедфолдерперсоналфолдер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдерперсоналфолдер

### <a name="windows10generalconfigurationstartmenupinnedfolderpictures"></a>Windows10GeneralConfiguration. Стартменупиннедфолдерпиктурес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдерпиктурес

### <a name="windows10generalconfigurationstartmenupinnedfoldersettings"></a>Windows10GeneralConfiguration. Стартменупиннедфолдерсеттингс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдерсеттингс

### <a name="windows10generalconfigurationstartmenupinnedfoldervideos"></a>Windows10GeneralConfiguration. Стартменупиннедфолдервидеос 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/старт/алловпиннедфолдервидеос

### <a name="windows10generalconfigurationstorageblockremovablestorage"></a>Windows10GeneralConfiguration. Сторажеблоккремоваблестораже 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/алловсторажекард

### <a name="windows10generalconfigurationstoragerequiremobiledeviceencryption"></a>Windows10GeneralConfiguration. Сторажерекуиремобиледевицеенкриптион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/секурити/рекуиредевицеенкриптион

### <a name="windows10generalconfigurationstoragerestrictappdatatosystemvolume"></a>Windows10GeneralConfiguration. Сторажерестриктаппдататосистемволуме 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/рестриктаппдататосистемволуме

### <a name="windows10generalconfigurationstoragerestrictappinstalltosystemvolume"></a>Windows10GeneralConfiguration. Сторажерестриктаппинсталлтосистемволуме 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/рестриктапптосистемволуме

### <a name="windows10generalconfigurationsystembootstartdriverinitialization"></a>Windows10GeneralConfiguration. Систембутстартдриверинитиализатион 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/бутстартдриверинитиализатион

### <a name="windows10generalconfigurationsystemtelemetryproxyserver"></a>Windows10GeneralConfiguration. Системтелеметрипроксисервер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/систем/телеметрипрокси

### <a name="windows10generalconfigurationtaskmanagerblockendtask"></a>Windows10GeneralConfiguration. Таскманажерблоккендтаск 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/таскманажер/алловендтаск

### <a name="windows10generalconfigurationtenantlockdownrequirenetworkduringoutofboxexperience"></a>Windows10GeneralConfiguration. Тенантлоккдовнрекуиренетворкдурингаутофбоксекспериенце 
**CSP**:./вендор/мсфт/тенантлоккдовн  
**URI смещения**:/рекуиренетворкинубе

### <a name="windows10generalconfigurationusbblocked"></a>Windows10GeneralConfiguration. Усбблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Коннективити/алловусбконнектион

### <a name="windows10generalconfigurationvoicerecordingblocked"></a>Windows10GeneralConfiguration. Воицерекордингблоккед 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвоицерекординг

### <a name="windows10generalconfigurationwebrtcblocklocalhostipaddress"></a>Windows10GeneralConfiguration. Вебрткблокклокалхостипаддресс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/превентусинглокалхостипаддрессфорвебртк

### <a name="windows10generalconfigurationwifiblockautomaticconnecthotspots"></a>Windows10GeneralConfiguration. Вифиблоккаутоматикконнексотспотс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/ВИФИ/алловаутоконнекттовифисенсехотспотс

### <a name="windows10generalconfigurationwifiblocked"></a>Windows10GeneralConfiguration. Вифиблоккед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/ВИФИ/алловвифи

### <a name="windows10generalconfigurationwifiblockmanualconfiguration"></a>Windows10GeneralConfiguration. Вифиблоккмануалконфигуратион 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/ВИФИ/алловмануалвифи/конфигуратион

### <a name="windows10generalconfigurationwifiscaninterval"></a>Windows10GeneralConfiguration. Вифисканинтервал 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/ВИФИ/влансканмоде

### <a name="windows10generalconfigurationwindowslogonlocalusersondomainjoinedcomputers"></a>Windows10GeneralConfiguration. Виндовслогонлокалусерсондомаинжоинедкомпутерс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/виндовслогон/енумерателокалусерсондомаинжоинедкомпутерс

### <a name="windows10generalconfigurationwindowsspotlightblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration. ВиндовсспотлигхтблоккконсумерспеЦификфеатурес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсконсумерфеатурес

### <a name="windows10generalconfigurationwindowsspotlightblocked"></a>Windows10GeneralConfiguration. Виндовсспотлигхтблоккед 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсспотлигхт

### <a name="windows10generalconfigurationwindowsspotlightblockonactioncenter"></a>Windows10GeneralConfiguration. Виндовсспотлигхтблокконактионцентер 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсспотлигхтонактионцентер

### <a name="windows10generalconfigurationwindowsspotlightblocktailoredexperiences"></a>Windows10GeneralConfiguration. Виндовсспотлигхтблокктаилоредекспериенцес 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловтаилоредекспериенцесвисдиагностикдата

### <a name="windows10generalconfigurationwindowsspotlightblockthirdpartynotifications"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockThirdPartyNotifications 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловсирдпартисугжестионсинвиндовсспотлигхт

### <a name="windows10generalconfigurationwindowsspotlightblockwelcomeexperience"></a>Windows10GeneralConfiguration. Виндовсспотлигхтблокквелкомикспериенце 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовсспотлигхтвиндовсвелкомикспериенце

### <a name="windows10generalconfigurationwindowsspotlightblockwindowstips"></a>Windows10GeneralConfiguration. Виндовсспотлигхтблокквиндовстипс 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/алловвиндовстипс

### <a name="windows10generalconfigurationwindowsspotlightconfigureonlockscreen"></a>Windows10GeneralConfiguration. Виндовсспотлигхтконфигуреонлоккскрин 
**CSP**:./Усер/вендор/мсфт/Полици  
**URI смещения**:/конфиг/експериенце/конфигуревиндовсспотлигхтонлоккскрин

### <a name="windows10generalconfigurationwindowsstoreblockautoupdate"></a>Windows10GeneralConfiguration. Виндовсстореблоккаутаупдате 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловаппстореаутаупдате

### <a name="windows10generalconfigurationwindowsstoreblocked"></a>Windows10GeneralConfiguration. Виндовсстореблоккед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/алловсторе

### <a name="windows10generalconfigurationwindowsstoreenableprivatestoreonly"></a>Windows10GeneralConfiguration. Виндовссторинаблеприватестореонли 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/аппликатионманажемент/рекуиреприватестореонли

### <a name="windows10generalconfigurationwirelessdisplayblockprojectiontothisdevice"></a>Windows10GeneralConfiguration. Вирелессдисплайблоккпрожектионтосисдевице 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/вирелессдисплай/алловпрожектионтопк

### <a name="windows10generalconfigurationwirelessdisplayblockuserinputfromreceiver"></a>Windows10GeneralConfiguration. Вирелессдисплайблоккусеринпутфромрецеивер 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/вирелессдисплай/алловусеринпутфромвирелессдисплайрецеивер

### <a name="windows10generalconfigurationwirelessdisplayrequirepinforpairing"></a>Windows10GeneralConfiguration. Вирелессдисплайрекуирепинфорпаиринг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/вирелессдисплай/рекуирепинфорпаиринг

### <a name="windows10networkboundaryconfigurationwindowsnetworkisolationpolicy"></a>Windows10NetworkBoundaryConfiguration. Виндовснетворкисолатионполици 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/нетворкисолатион/ентерприсеклаудресаурцес,/конфиг/нетворкисолатион/ентерприсеипранже,/config/NetworkIsolation/EnterpriseIPRangesAreAuthoritative,/config/NetworkIsolation/ Ентерприсеинтерналпроксисерверс,/конфиг/нетворкисолатион/ентерприсенетворкдомаиннамес,/Config/NetworkIsolation/EnterpriseProxyServers,/Config/NetworkIsolation/EnterpriseProxyServersAreAuthoritative,/Config/NetworkIsolation/ неутралресаурцес

### <a name="windows10policyoverrideconfigurationprefermdmovergrouppolicy"></a>Windows10PolicyOverrideConfiguration. Префермдмоверграупполици 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/контролполициконфликт/мдмвинсовергп

### <a name="windows10secureassessmentconfigurationallowprinting"></a>Windows10SecureAssessmentConfiguration. Алловпринтинг 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/рекуирепринтинг

### <a name="windows10secureassessmentconfigurationallowscreencapture"></a>Windows10SecureAssessmentConfiguration. Алловскринкаптуре 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/алловскринмониторинг

### <a name="windows10secureassessmentconfigurationallowtextsuggestion"></a>Windows10SecureAssessmentConfiguration.AllowTextSuggestion 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/алловтекстсугжестионс

### <a name="windows10secureassessmentconfigurationconfigurationaccount"></a>Windows10SecureAssessmentConfiguration. Конфигуратионаккаунт 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/тестераккаунт

### <a name="windows10secureassessmentconfigurationconfigurationaccounttype"></a>Windows10SecureAssessmentConfiguration. Конфигуратионаккаунттипе 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/тестераккаунт

### <a name="windows10secureassessmentconfigurationlaunchuri"></a>Windows10SecureAssessmentConfiguration. Лаунчури 
**CSP**:./вендор/мсфт/секуреассессмент  
**URI смещения**:/лаунчури

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsblocktelemetry"></a>Windows10TeamGeneralConfiguration. Азуреоператионалинсигхтсблокктелеметри 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/Момажент/воркспацеид и/момажент/воркспацекэй

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspaceid"></a>Windows10TeamGeneralConfiguration. Азуреоператионалинсигхтсворкспацеид 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/момажент/воркспацеид

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspacekey"></a>Windows10TeamGeneralConfiguration. Азуреоператионалинсигхтсворкспацекэй 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/момажент/воркспацекэй

### <a name="windows10teamgeneralconfigurationconnectappblockautolaunch"></a>Windows10TeamGeneralConfiguration. Коннектаппблоккаутолаунч 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/Коннект/аутолаунч

### <a name="windows10teamgeneralconfigurationdeviceaccountblockexchangeservices"></a>Windows10TeamGeneralConfiguration. Девицеаккаунтблоккексчанжесервицес 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/девицеаккаунт/емаил

### <a name="windows10teamgeneralconfigurationdeviceaccountemailaddress"></a>Windows10TeamGeneralConfiguration. Девицеаккаунтемаиладдресс 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/девицеаккаунт/емаил

### <a name="windows10teamgeneralconfigurationdeviceaccountexchangeserveraddress"></a>Windows10TeamGeneralConfiguration. Девицеаккаунтексчанжесервераддресс 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/девицеаккаунт/ексчанжесервер

### <a name="windows10teamgeneralconfigurationdeviceaccountrequirepasswordrotation"></a>Windows10TeamGeneralConfiguration. Девицеаккаунтрекуирепассвордротатион 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/девицеаккаунт/пассвордротатионенаблед

### <a name="windows10teamgeneralconfigurationdeviceaccountsessioninitiationprotocoladdress"></a>Windows10TeamGeneralConfiguration. Девицеаккаунтсессионинитиатионпротоколаддресс 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/девицеаккаунт/сипаддресс

### <a name="windows10teamgeneralconfigurationmaintenancewindowblocked"></a>Windows10TeamGeneralConfiguration. Маинтенанцевиндовблоккед 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/Маинтенанцехаурссимпле/хаурс/дуратион и/маинтенанцехаурссимпле/хаурс/старттиме

### <a name="windows10teamgeneralconfigurationmaintenancewindowdurationinhours"></a>Windows10TeamGeneralConfiguration. Маинтенанцевиндовдуратионинхаурс 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/маинтенанцехаурссимпле/хаурс/дуратион

### <a name="windows10teamgeneralconfigurationmaintenancewindowstarttime"></a>Windows10TeamGeneralConfiguration. Маинтенанцевиндовстарттиме 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/маинтенанцехаурссимпле/хаурс/старттиме

### <a name="windows10teamgeneralconfigurationmiracastblocked"></a>Windows10TeamGeneralConfiguration. Миракастблоккед 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/вирелесспрожектион/енаблед

### <a name="windows10teamgeneralconfigurationmiracastchannel"></a>Windows10TeamGeneralConfiguration. Миракастчаннел 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/вирелесспрожектион/Чаннел

### <a name="windows10teamgeneralconfigurationmiracastrequirepin"></a>Windows10TeamGeneralConfiguration. Миракастрекуирепин 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/вирелесспрожектион/пинрекуиред

### <a name="windows10teamgeneralconfigurationsettingsblockmymeetingsandfiles"></a>Windows10TeamGeneralConfiguration. Сеттингсблоккмимитингсандфилес 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/донотшовмимитингсандфилес

### <a name="windows10teamgeneralconfigurationsettingsblocksessionresume"></a>Windows10TeamGeneralConfiguration. Сеттингсблокксессионресуме 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/алловсессионресуме

### <a name="windows10teamgeneralconfigurationsettingsblocksigninsuggestions"></a>Windows10TeamGeneralConfiguration. Сеттингсблокксигнинсугжестионс 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/дисаблесигнинсугжестионс

### <a name="windows10teamgeneralconfigurationsettingsdefaultvolume"></a>Windows10TeamGeneralConfiguration. Сеттингсдефаултволуме 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/дефаултволуме

### <a name="windows10teamgeneralconfigurationsettingsscreentimeoutinminutes"></a>Windows10TeamGeneralConfiguration. Сеттингсскринтимеаутинминутес 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/скринтимеаут

### <a name="windows10teamgeneralconfigurationsettingssessiontimeoutinminutes"></a>Windows10TeamGeneralConfiguration. Сеттингссессионтимеаутинминутес 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/сессионтимеаут

### <a name="windows10teamgeneralconfigurationsettingssleeptimeoutinminutes"></a>Windows10TeamGeneralConfiguration. Сеттингсслиптимеаутинминутес 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/пропертиес/слиптимеаут

### <a name="windows10teamgeneralconfigurationwelcomescreenbackgroundimageurl"></a>Windows10TeamGeneralConfiguration. Велкомескринбаккграундимажеурл 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/велкоме/куррентбаккграундпас

### <a name="windows10teamgeneralconfigurationwelcomescreenblockautomaticwakeup"></a>Windows10TeamGeneralConfiguration. Велкомескринблоккаутоматиквакеуп 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/велкоме/аутовакескрин

### <a name="windows10teamgeneralconfigurationwelcomescreenmeetinginformation"></a>Windows10TeamGeneralConfiguration. Велкомескринмитингинформатион 
**CSP**:./вендор/мсфт/сурфацехуб  
**URI смещения**:/инбоксаппс/велкоме/митингинфуптион

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingblob"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Адванцедсреатпротектионоффбоардингблоб 
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/оффбоардинг 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingfilename"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Адванцедсреатпротектионоффбоардингфиленаме
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/оффбоардинг 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingblob"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Адванцедсреатпротектиононбоардингблоб 
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/онбоардинг 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingfilename"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Адванцедсреатпротектиононбоардингфиленаме 
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/онбоардинг 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationallowsamplesharing"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Алловсамплешаринг 
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/конфигуратион/самплешаринг

### <a name="windowsdefenderadvancedthreatprotectionconfigurationenableexpeditedtelemetryreporting"></a>Виндовсдефендерадванцедсреатпротектионконфигуратион. Енабликспедитедтелеметрирепортинг 
**CSP**:./девице/вендор/мсфт/виндовсадванцедсреатпротектион  
**URI смещения**:/конфигуратион/телеметрирепортингфрекуенци

### <a name="windowsdeliveryoptimizationconfigurationdeliveryoptimizationmode"></a>Виндовсделиверйоптимизатионконфигуратион. Деливерйоптимизатионмоде 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/деливерйоптимизатион/додовнлоадмоде

### <a name="windowsidentityprotectionconfigurationenhancedantispoofingforfacialfeaturesenabled"></a>Виндовсидентитипротектионконфигуратион. ЕнханцедантиспуфингфорфаЦиалфеатуресенаблед 
**CSP**:./девице/вендор/мсфт/пасспортфорворк  
**URI смещения**:/Биометрикс/фаЦиалфеатуресусинханцедантиспуфинг

### <a name="windowsidentityprotectionconfigurationpinexpirationindays"></a>Виндовсидентитипротектионконфигуратион. Пинекспиратиониндайс 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/експиратион

### <a name="windowsidentityprotectionconfigurationpinlowercasecharactersusage"></a>Виндовсидентитипротектионконфигуратион. Пинловеркасечарактерсусаже 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/ловеркаселеттерс

### <a name="windowsidentityprotectionconfigurationpinmaximumlength"></a>Виндовсидентитипротектионконфигуратион. Пинмаксимумленгс 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/максимумпинленгс

### <a name="windowsidentityprotectionconfigurationpinminimumlength"></a>Виндовсидентитипротектионконфигуратион. Пинминимумленгс 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/минимумпинленгс

### <a name="windowsidentityprotectionconfigurationpinpreviousblockcount"></a>Виндовсидентитипротектионконфигуратион. Пинпревиаусблокккаунт 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/Хистори

### <a name="windowsidentityprotectionconfigurationpinrecoveryenabled"></a>Виндовсидентитипротектионконфигуратион. Пинрековеренаблед 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/енаблепинрековери

### <a name="windowsidentityprotectionconfigurationpinspecialcharactersusage"></a>Виндовсидентитипротектионконфигуратион. ПинспеЦиалчарактерсусаже 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/спеЦиалчарактерс

### <a name="windowsidentityprotectionconfigurationpinuppercasecharactersusage"></a>Виндовсидентитипротектионконфигуратион. Пинупперкасечарактерсусаже
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/пинкомплексити/упперкаселеттерс

### <a name="windowsidentityprotectionconfigurationsecuritydevicerequired"></a>Виндовсидентитипротектионконфигуратион. Секуритидевицерекуиред 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/рекуиресекуритидевице

### <a name="windowsidentityprotectionconfigurationunlockwithbiometricsenabled"></a>WindowsIdentityProtectionConfiguration.UnlockWithBiometricsEnabled 
**CSP**:./девице/вендор/мсфт/пасспортфорворк  
**URI смещения**:/Биометрикс/усебиометрикс

### <a name="windowsidentityprotectionconfigurationusecertificatesforonpremisesauthenabled"></a>Виндовсидентитипротектионконфигуратион. Усецертификатесфоронпремисесаусенаблед 
**CSP**:./девице/вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/усецертификатефоронпремаус

### <a name="windowsidentityprotectionconfigurationwindowshelloforbusinessblocked"></a>Виндовсидентитипротектионконфигуратион. Виндовшеллофорбусинессблоккед 
**CSP**:./вендор/мсфт/пасспортфорворк  
**URI смещения**:/{аадтенантид}/полиЦиес/усепасспортфорворк

### <a name="windowskioskconfigurationedgekioskenablepublicbrowsing"></a>Виндовскиоскконфигуратион. Еджекиоскенаблепубликбровсинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/конфигурекиоскмоде

### <a name="windowskioskconfigurationedgekioskresetafteridletimeinminutes"></a>Виндовскиоскконфигуратион. Еджекиоскресетафтеридлетимеинминутес 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/Бровсер/конфигурекиоскресетафтеридлетимеаут

### <a name="windowskioskconfigurationkioskbrowserblockedurlexceptions"></a>Виндовскиоскконфигуратион. Киоскбровсерблоккедурлексцептионс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/блоккедурлексцептионс

### <a name="windowskioskconfigurationkioskbrowserblockedurls"></a>Виндовскиоскконфигуратион. Киоскбровсерблоккедурлс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/блоккедурлс

### <a name="windowskioskconfigurationkioskbrowserdefaulturl"></a>Виндовскиоскконфигуратион. Киоскбровсердефаултурл 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/дефаултурл

### <a name="windowskioskconfigurationkioskbrowserenableendsessionbutton"></a>Виндовскиоскконфигуратион. Киоскбровсеренаблиндсессионбуттон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/енаблиндсессионбуттон

### <a name="windowskioskconfigurationkioskbrowserenablehomebutton"></a>Виндовскиоскконфигуратион. Киоскбровсеренаблехомебуттон 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/енаблехомебуттон

### <a name="windowskioskconfigurationkioskbrowserenablenavigationbuttons"></a>Виндовскиоскконфигуратион. Киоскбровсеренабленавигатионбуттонс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/енабленавигатионбуттонс

### <a name="windowskioskconfigurationkioskbrowserrestartonidletimeinminutes"></a>Виндовскиоскконфигуратион. Киоскбровсеррестартонидлетимеинминутес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/киоскбровсер/киоскбровсеррестартонидлетимеинминутес

### <a name="windowsupdateforbusinessconfigurationautomaticupdatemode"></a>Виндовсупдатефорбусинессконфигуратион. Аутоматикупдатемоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/алловаутаупдате

### <a name="windowsupdateforbusinessconfigurationautorestartnotificationdismissal"></a>Виндовсупдатефорбусинессконфигуратион. Ауторестартнотификатиондисмиссал 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/ауторестартрекуиреднотификатиондисмиссал

### <a name="windowsupdateforbusinessconfigurationbusinessreadyupdatesonly"></a>Виндовсупдатефорбусинессконфигуратион. Бусинессреадюпдатесонли 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/бранчреадинесслевел

### <a name="windowsupdateforbusinessconfigurationdeliveryoptimizationmode"></a>Виндовсупдатефорбусинессконфигуратион. Деливерйоптимизатионмоде 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/деливерйоптимизатион/додовнлоадмоде

### <a name="windowsupdateforbusinessconfigurationdriversexcluded"></a>Виндовсупдатефорбусинессконфигуратион. Дриверсексклудед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/ексклудевудриверсинкуалитюпдате

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineforfeatureupdatesindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестартдеадлинефорфеатуреупдатесиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестартдеадлинефорфеатуреупдатес

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестартдеадлинеиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестартдеадлине

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleforfeatureupdatesindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестартснузесчедулефорфеатуреупдатесиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестартснузесчедулефорфеатуреупдатес

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестартснузесчедулеиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестартснузесчедуле

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleforfeatureupdatesindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестарттранситионсчедулефорфеатуреупдатесиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестарттранситионсчедулефорфеатуреупдатес

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleindays"></a>Виндовсупдатефорбусинессконфигуратион. Енгажедрестарттранситионсчедулеиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/енгажедрестарттранситионсчедуле

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesdeferralperiodindays"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатесдеферралпериодиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/деферфеатуреупдатеспериодиндайс

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespaused"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатеспаусед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/паусефеатуреупдатес

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespausestartdatetime"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатеспаусестартдатетиме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/паусефеатуреупдатесстарттиме

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackstartdatetime"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатесроллбаккстартдатетиме
**CSP**: Н/д API Graph только **URI смещения**: Н/д-API Graph только

### <a name="windowsupdateforbusinessconfigurationfeatureupdateswillberolledback"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатесвиллберолледбакк 
**CSP**: Н/д API Graph только **URI смещения**: Н/д-API Graph только

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackwindowindays"></a>Виндовсупдатефорбусинессконфигуратион. Феатуреупдатесроллбакквиндовиндайс
**CSP**: Н/д API Graph только **URI смещения**: Н/д-API Graph только

### <a name="windowsupdateforbusinessconfigurationinstallationschedule"></a>Виндовсупдатефорбусинессконфигуратион. Инсталлатионсчедуле
**CSP**:./ДЕВИЦЕ/ВЕНДОР/МСФТ/ПОЛИЦИ **offset URI**:/конфиг/упдате/активехаурсстарт,/конфиг/упдате/активехаурсенд,/config/Update/ScheduledInstallDay,/config/Update/ScheduledInstallTime

### <a name="windowsupdateforbusinessconfigurationmicrosoftupdateserviceallowed"></a>Виндовсупдатефорбусинессконфигуратион. Микрософтупдатесервицеалловед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/алловмуупдатесервице

### <a name="windowsupdateforbusinessconfigurationpreviewbuildsetting"></a>Виндовсупдатефорбусинессконфигуратион. Превиевбуилдсеттинг 
**CSP**:./вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/манажепревиевбуилдс

### <a name="windowsupdateforbusinessconfigurationqualityupdatesdeferralperiodindays"></a>Виндовсупдатефорбусинессконфигуратион. Куалитюпдатесдеферралпериодиндайс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/деферкуалитюпдатеспериодиндайс

### <a name="windowsupdateforbusinessconfigurationqualityupdatespaused"></a>Виндовсупдатефорбусинессконфигуратион. Куалитюпдатеспаусед 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/паусекуалитюпдатес

### <a name="windowsupdateforbusinessconfigurationqualityupdatespausestartdatetime"></a>Виндовсупдатефорбусинессконфигуратион. Куалитюпдатеспаусестартдатетиме 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/паусекуалитюпдатесстарттиме

### <a name="windowsupdateforbusinessconfigurationqualityupdatesrollbackstartdatetime"></a>Виндовсупдатефорбусинессконфигуратион. Куалитюпдатесроллбаккстартдатетиме
**CSP**: Н/д API Graph только **URI смещения**: Н/д-API Graph только

### <a name="windowsupdateforbusinessconfigurationqualityupdateswillberolledback"></a>Виндовсупдатефорбусинессконфигуратион. Куалитюпдатесвиллберолледбакк 
**CSP**: Н/д API Graph только **URI смещения**: Н/д-API Graph только

### <a name="windowsupdateforbusinessconfigurationscheduleimminentrestartwarninginminutes"></a>Виндовсупдатефорбусинессконфигуратион. Счедулеимминентрестартварнингинминутес 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/счедулеимминентрестартварнинг

### <a name="windowsupdateforbusinessconfigurationschedulerestartwarninginhours"></a>Виндовсупдатефорбусинессконфигуратион. Счедулерестартварнингинхаурс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/счедулерестартварнинг

### <a name="windowsupdateforbusinessconfigurationskipchecksbeforerestart"></a>Виндовсупдатефорбусинессконфигуратион. Скипчекксбефоререстарт 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/сетедурестарт

### <a name="windowsupdateforbusinessconfigurationupdateweeks"></a>Виндовсупдатефорбусинессконфигуратион. Упдатевикс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/счедулединсталлеверивик,/конфиг/упдате/счедулединсталлфирствик,/config/Update/ScheduledInstallFourthWeek,/config/Update/ScheduledInstallSecondWeek,/config/Update/ScheduledInstallThirdWeek

### <a name="windowsupdateforbusinessconfigurationuserpauseaccess"></a>Виндовсупдатефорбусинессконфигуратион. Усерпаусеакцесс 
**CSP**:./девице/вендор/мсфт/Полици  
**URI смещения**:/конфиг/упдате/сетдисаблепаусеуксакцесс


## <a name="next-steps"></a>Следующие шаги

- [Общие сведения о конфигурации устройства](device-profiles.md)
- [Справочник по поставщику услуг конфигурации](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (открывает другой сайт документов)
