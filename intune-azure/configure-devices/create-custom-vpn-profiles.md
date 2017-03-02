---
title: "Как создать настраиваемые профили VPN с помощью Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Создание профилей VPN в Intune с помощью настраиваемых конфигураций."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 132844bb1d1119390b7f55cca58cecbd5b8ee90a
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Как создать настраиваемые профили VPN в Microsoft Intune

## <a name="create-a-custom-configuration"></a>Создание настраиваемой конфигурации
С помощью политик настраиваемых конфигураций Intune можно создать профили VPN для следующих устройств:

* Устройства под управлением Android 4 и более поздней версии.
* Зарегистрированные устройства под управлением Windows 8.1 и более поздней версии.
* Устройства под управлением Windows Phone 8.1 и более поздней версии.
* Зарегистрированные устройства под управлением Windows 10 Desktop и более поздней версии. 
* Устройства с Windows 10 Mobile

Этот тип политики удобен, когда стандартные политики VPN Intune не содержат нужные вам параметры

## <a name="to-create-a-custom-configuration-policy"></a>Создание политики настраиваемой конфигурации:

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Другое** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
4. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
5. В колонке профилей выберите **Создание профиля**.
6. В колонке **Создание профиля** введите **имя** и **описание** для профиля VPN.
7. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить параметры VPN. Сейчас для пользовательских параметров устройства можно выбрать одну из следующих платформ:
    - **Android**
    - **iOS** (настраивается с помощью файла, экспортированного из Apple Configurator)
    - **macOS** (настраивается с помощью файла, экспортированного из Apple Configurator)
    - **Windows Phone 8.1**
    - **Windows 10 и более поздних версий**.
6. В раскрывающемся списке **Профиль** выберите **Пользовательский**.
7. В колонке **Настраиваемые параметры OMA URI** возле каждого параметра URI, который вы хотите указать, выберите **Добавить**, укажите нужные данные, а затем выберите кнопку **ОК**. Пример:

   ![Диалоговое окно настраиваемой конфигурации профиля VPN](./media/Intune_Add_VPN_URI.png)

4.  После ввода всех необходимых параметров URI нажмите кнопку **ОК**, а затем в колонке **Создать профиль** выберите **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](how-to-assign-device-profiles.md).

## <a name="example-uri-settings"></a>Примеры параметров URI

Эти параметры можно использовать для создания настраиваемой конфигурации VPN в вымышленной компании Contoso.
Дополнительные сведения обо всех параметрах, которые можно использовать, см. в статье [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)

Собственный VPN Contoso (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

По любым вопросам о назначении и использовании этих параметров клиентам следует обращаться к документации по поставщику службы конфигурации (CSP): https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>Параметры URI для VPN для каждого приложения Android в PulseSecure
### <a name="custom-uri-for-package-list"></a>НАСТРАИВАЕМЫЙ КОД URI ДЛЯ СПИСКА ПРИЛОЖЕНИЙ
-  Тип данных = строковый
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Значение = список пакетов с разделителями
   - Разделители: точка с запятой (;), двоеточие (:), запятая (,), вертикальная черта (|)

Примеры:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>НАСТРАИВАЕМЫЙ КОД URI ДЛЯ РЕЖИМА (НЕОБЯЗАТЕЛЬНО)
- Тип данных = строковый
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Примечания
> - Используйте то же *имя*, которые вы присвоили настраиваемому профилю.
> - Возможные значения: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Если значение PackageList не указано, по умолчанию используется значение *GLOBAL* (для обратной совместимости с системными профилями).
> - Если значение PackageList указано, по умолчанию используется значение *WHITELIST*.




