---
title: "Настраиваемые конфигурации профилей VPN Microsoft Intune | Документы Майкрософт"
description: "Создание профилей VPN в Intune с помощью настраиваемых конфигураций."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: 9dbb44981c1525e6137dd8a469b1582731ee9719


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Настраиваемые конфигурации профилей VPN Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Создание настраиваемой конфигурации
С помощью политик настраиваемых конфигураций Intune можно создать профили VPN для следующих устройств:

* Устройства под управлением Android 4 и более поздней версии.
* Устройства Android for Work
* Зарегистрированные устройства под управлением Windows 8.1 и более поздней версии.
* Устройства под управлением Windows Phone 8.1 и более поздней версии.
* Зарегистрированные устройства под управлением Windows 10 Desktop и более поздней версии. 
* Устройства под управлением Windows 10 Mobile.

Этот тип политики удобен, когда стандартные политики VPN Intune не содержат нужные вам параметры

## <a name="to-create-a-custom-configuration-policy"></a>Создание политики настраиваемой конфигурации:

   1. В [консоли администрирования Intune](https://manage.microsoft.com) выберите **Политика** > **Добавить политику** > *Развернуть платформу* > **Настраиваемая конфигурация** > **Создать политику**.
   2. Введите имя политики.
   3. Для каждого параметра URI, который требуется задать, щелкните **Добавить** и укажите требуемые данные. Пример:

   ![Диалоговое окно настраиваемой конфигурации профиля VPN](./media/Intune_Add_VPN_URI.png)

   4.  Задав все параметры URI, щелкните **Сохранить политику**, а затем разверните политику.

После этого [разверните политику](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) в обычном режиме.

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


### <a name="see-also"></a>См. также
[VPN-подключения в Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


