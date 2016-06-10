---
# required metadata

title: Настраиваемые конфигурации профилей VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Настраиваемые конфигурации профилей VPN

## Создание настраиваемой конфигурации
Для создания профилей VPN в Intune можно использовать настраиваемые конфигурации. Чтобы создать настраиваемую конфигурацию, выполните указанные ниже действия.

   1. В консоли администрирования Intune выберите **Политика** -> **Добавить политику** -> *<Expand platform>* -> **Настраиваемая конфигурация** -> **Создать политику**
   2. Укажите имя политики.
   3. Для каждого параметра URI щелкните **Добавить** и укажите требуемые данные. Пример:

   ![Диалоговое окно настраиваемой конфигурации профиля VPN](./media/Intune_Add_VPN_URI.png)

   4.  Задав все параметры URI, щелкните **Сохранить политику**, а затем разверните политику.

## Развертывание политики конфигурации

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.

2.  В диалоговом окне **Управление развертыванием** выполните следующие действия.

    -   **Развертывание политики**. Выберите одну или несколько групп для развертывания политики, а затем нажмите **Добавить** &gt; **ОК**.

    -   **Чтобы закрыть диалоговое окно, не развертывая политику**, нажмите кнопку **Отмена**.

При выборе развернутой политики можно просмотреть дополнительные сведения о развертывании в нижней части списка политик.

##Пример параметров URI для настраиваемой конфигурации профиля VPN. Ниже приведены примеры значений URI для создания настраиваемой конфигурации VPN в вымышленной организации Contoso. Дополнительные сведения, например о типе данных для каждой записи, см. в статье [Поставщик службы конфигурации VPNv2](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

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

По любым вопросам о назначении и использовании этих параметров клиентам следует обращаться к документации по поставщику службы конфигурации: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## Параметры URI для VPN для каждого приложения Android в PulseSecure
### НАСТРАИВАЕМЫЙ КОД URI ДЛЯ СПИСКА ПРИЛОЖЕНИЙ 
-  Тип данных = строковый
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Значение = список пакетов с разделителями
   - Разделители: точка с запятой (;), двоеточие (:), запятая (,), вертикальная черта (|)

Примеры: 
- com.android.chrome
- com.android.chrome;com.android.browser

### НАСТРАИВАЕМЫЙ КОД URI ДЛЯ РЕЖИМА (НЕОБЯЗАТЕЛЬНО)
- Тип данных = строковый
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Примечания
> - Используйте то же *имя*, которые вы присвоили настраиваемому профилю.
> - Возможные значения: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Если значение PackageList не указано, по умолчанию используется значение *GLOBAL* (для обратной совместимости с системными профилями).
> - Если значение PackageList указано, по умолчанию используется значение *WHITELIST*.


### См. также
(VPN-подключения в Microsoft Intune)[vpn-connections-in-microsoft-intune.md]


<!--HONumber=May16_HO2-->


