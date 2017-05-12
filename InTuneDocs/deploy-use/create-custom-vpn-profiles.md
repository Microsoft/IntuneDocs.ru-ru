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
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 56095b44e890759202d68312bd684c767d3410ce
ms.openlocfilehash: 284868ba0c79a6cbb1c3e5096a84461e99c0ba76
ms.contentlocale: ru-ru
ms.lasthandoff: 04/28/2017


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
Дополнительные сведения обо всех параметрах, которые можно использовать, см. в статье [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx)

**Собственная VPN Contoso (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com,

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com,

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com,

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
верно

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Сведения о назначении этих параметров и способах их использования см. в [документации по поставщику службы конфигурации (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

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

