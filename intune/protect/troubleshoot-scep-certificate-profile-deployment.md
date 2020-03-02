---
title: Устранение неполадок при развертывании профилей сертификатов SCEP на устройствах с помощью Microsoft Intune | Документация Майкрософт
description: Устранение неполадок при отправке профиля сертификата SCEP на устройство с помощью Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26eb6a5cb8e7aba01ce32ab8bec8ad917604a55c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514784"
---
# <a name="troubleshoot-deployment-of-a-scep-certificate-profile-to-devices-in-microsoft-intune"></a>Устранение неполадок при развертывании профилей сертификатов SCEP на устройствах в Microsoft Intune

Следующие сведения помогут устранить неполадки при развертывании профилей сертификатов SCEP с помощью Intune.

Эта статья ссылается на шаг 1 [общих сведений о потоке обмена данными SCEP](troubleshoot-scep-certificate-profiles.md).


## <a name="android"></a>Android

Профили сертификатов SCEP для Android переходят на устройство в виде SyncML и записываются в журнал [OMADM](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices).

### <a name="validate-that-the-android-device-was-sent-the-policy"></a>Проверка отправки политики устройством Android

Чтобы проверить, отправлен ли профиль на нужное устройство, в [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) перейдите в раздел **Устранение неполадок и поддержка** > **Устранение неполадок**.  В окне *Устранение неполадок* установите **назначения** **профилям конфигурации**, а затем проверьте следующие конфигурации:

1. Укажите пользователя, который должен получить профиль сертификата SCEP.

2. Проверьте членство в группе "Пользователи", чтобы убедиться в том, что они находятся в группе безопасности, используемой с профилем сертификата SCEP.

3. Проверьте, когда устройство последний раз синхронизировалось с Intune.

![Проверка политики](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-android.png)

### <a name="validate-the-policy-reached-the-android-device"></a>Проверка политики, достигшей устройства Android

Проверьте [журнал устройств OMADM](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Найдите записи, аналогичные приведенным ниже, которые регистрируются, когда устройство получает профиль из Intune:

```
Time    VERB    Event     com.microsoft.omadm.syncml.SyncmlSession     9595        9    <?xml version="1.0" encoding="utf-8"?><SyncML xmlns="SYNCML:SYNCML1.2"><SyncHdr><VerDTD>1.2</VerDTD><VerProto>DM/1.2</VerProto><SessionID>1</SessionID><MsgID>6</MsgID><Target><LocURI>urn:uuid:UUID</LocURI></Target><Source><LocURI>https://a.manage.microsoft.com/devicegatewayproxy/AndroidHandler.ashx</LocURI></Source><Meta><MaxMsgSize xmlns="syncml:metinf">524288</MaxMsgSize></Meta></SyncHdr><SyncBody><Status><CmdID>1</CmdID><MsgRef>6</MsgRef><CmdRef>0</CmdRef><Cmd>SyncHdr</Cmd><Data>200</Data></Status><Replace><CmdID>2</CmdID><Item><Target><LocURI>./Vendor/MSFT/Scheduler/IntervalDurationSeconds</LocURI></Target><Meta><Format xmlns="syncml:metinf">int</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>28800</Data></Item></Replace><Replace><CmdID>3</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseIDs</LocURI></Target><Data>contoso.onmicrosoft.com</Data></Item></Replace><Exec><CmdID>4</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseApps/ClearNotifications</LocURI></Target></Item></Exec><Add><CmdID>5</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Root/{GUID}/EncodedCertificate</LocURI></Target><Data>Data</Data></Item></Add><Add><CmdID>6</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Enroll/ModelName=AC_51…%2FLogicalName_39907…%3BHash=-1518303401/Install</LocURI></Target><Meta><Format xmlns="syncml:metinf">xml</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>&lt;CertificateRequest&gt;&lt;ConfigurationParametersDocument&gt;&amp;lt;ConfigurationParameters xmlns="http://schemas.microsoft.com/SystemCenterConfigurationManager/2012/03/07/CertificateEnrollment/ConfigurationParameters"&amp;gt;&amp;lt;ExpirationThreshold&amp;gt;20&amp;lt;/ExpirationThreshold&amp;gt;&amp;lt;RetryCount&amp;gt;3&amp;lt;/RetryCount&amp;gt;&amp;lt;RetryDelay&amp;gt;1&amp;lt;/RetryDelay&amp;gt;&amp;lt;TemplateName /&amp;gt;&amp;lt;SubjectNameFormat&amp;gt;{ID}&amp;lt;/SubjectNameFormat&amp;gt;&amp;lt;SubjectAlternativeNameFormat&amp;gt;{ID}&amp;lt;/SubjectAlternativeNameFormat&amp;gt;&amp;lt;KeyStorageProviderSetting&amp;gt;0&amp;lt;/KeyStorageProviderSetting&amp;gt;&amp;lt;KeyUsage&amp;gt;32&amp;lt;/KeyUsage&amp;gt;&amp;lt;KeyLength&amp;gt;2048&amp;lt;/KeyLength&amp;gt;&amp;lt;HashAlgorithms&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-1&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-2&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;/HashAlgorithms&amp;gt;&amp;lt;NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls&amp;gt;&amp;lt;CAThumbprint&amp;gt;{GUID}&amp;lt;/CAThumbprint&amp;gt;&amp;lt;ValidityPeriod&amp;gt;2&amp;lt;/ValidityPeriod&amp;gt;&amp;lt;ValidityPeriodUnit&amp;gt;Years&amp;lt;/ValidityPeriodUnit&amp;gt;&amp;lt;EKUMapping&amp;gt;&amp;lt;EKUMap&amp;gt;&amp;lt;EKUName&amp;gt;Client Authentication&amp;lt;/EKUName&amp;gt;&amp;lt;EKUOID&amp;gt;1.3.6.1.5.5.7.3.2&amp;lt;/EKUOID&amp;gt;&amp;lt;/EKUMap&amp;gt;&amp;lt;/EKUMapping&amp;gt;&amp;lt;/ConfigurationParameters&amp;gt;&lt;/ConfigurationParametersDocument&gt;&lt;RequestParameters&gt;&lt;CertificateRequestToken&gt;PENlcnRFbn... Hash: 1,010,143,298&lt;/CertificateRequestToken&gt;&lt;SubjectName&gt;CN=name&lt;/SubjectName&gt;&lt;Issuers&gt;CN=FourthCoffee CA; DC=fourthcoffee; DC=local&lt;/Issuers&gt;&lt;SubjectAlternativeName&gt;&lt;SANs&gt;&lt;SAN NameFormat="ID" AltNameType="2" OID="{OID}"&gt;&lt;/SAN&gt;&lt;SAN NameFormat="ID" AltNameType="11" OID="{OID}"&gt;john@contoso.onmicrosoft.com&lt;/SAN&gt;&lt;/SANs&gt;&lt;/SubjectAlternativeName&gt;&lt;NDESUrl&gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&lt;/NDESUrl&gt;&lt;/RequestParameters&gt;&lt;/CertificateRequest&gt;</Data></Item></Add><Get><CmdID>7</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/SCEP</LocURI></Target></Item></Get><Add><CmdID>8</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Add><Replace><CmdID>9</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Replace><Get><CmdID>10</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr</LocURI></Target></Item></Get><Get><CmdID>11</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/CacheVersion</LocURI></Target></Item></Get><Get><CmdID>12</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/ChangedNodes</LocURI></Target></Item></Get><Get><CmdID>13</CmdID><Item><Target><LocURI>./DevDetail/Ext/Microsoft/LocalTime</LocURI></Target></Item></Get><Get><CmdID>14</CmdID><Item><Target><LocURI>./Vendor/MSFT/DeviceLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Get><CmdID>15</CmdID><Item><Target><LocURI>./Vendor/MSFT/WorkProfileLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Final /></SyncBody></SyncML>
```

Примеры записей ключей:

- `ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c%3BHash=-1518303401`
- `NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls`

## <a name="iosipados"></a>iOS/iPadOS

### <a name="validate-that-the-iosipados-device-was-sent-the-policy"></a>Проверка отправки политики устройством iOS/iPadOS

Чтобы проверить, отправлен ли профиль на нужное устройство, в [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) перейдите в раздел **Устранение неполадок и поддержка** > **Устранение неполадок**.  В окне *Устранение неполадок* установите **назначения** **профилям конфигурации**, а затем проверьте следующие конфигурации:

1. Укажите пользователя, который должен получить профиль сертификата SCEP.

2. Проверьте членство в группе "Пользователи", чтобы убедиться в том, что они находятся в группе безопасности, используемой с профилем сертификата SCEP.

3. Проверьте, когда устройство последний раз синхронизировалось с Intune.

![Проверка политики](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-ios.png)

### <a name="validate-the-policy-reached-the-ios-or-ipados-device"></a>Проверка политики, достигшей устройства iOS или iPadOS

Проверьте [журнал отладки устройств](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Найдите записи, аналогичные приведенным ниже, которые регистрируются, когда устройство получает профиль из Intune:

```
debug    18:30:54.638009 -0500    profiled    Adding dependent ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 to parent 636572740000000000000012 in domain PayloadDependencyDomainCertificate to system\
```

Примеры записей ключей:

- `ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295`
- `PayloadDependencyDomainCertificate`

## <a name="windows"></a>Windows

### <a name="validate-that-the-windows-device-was-sent-the-policy"></a>Проверка отправки политики устройством Windows

Чтобы проверить, отправлен ли профиль на нужное устройство, в [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) [перейдите](https://go.microsoft.com/fwlink/?linkid=2109431) в раздел **Устранение неполадок и поддержка** > **Устранение неполадок**.  В окне *Устранение неполадок* установите **назначения** **профилям конфигурации**, а затем проверьте следующие конфигурации:

1. Укажите пользователя, который должен получить профиль сертификата SCEP.

2. Проверьте членство в группе "Пользователи", чтобы убедиться в том, что они находятся в группе безопасности, используемой с профилем сертификата SCEP.

3. Проверьте, когда устройство последний раз синхронизировалось с Intune.

![Проверка политики](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-windows.png)

### <a name="validate-the-policy-reached-the-windows-device"></a>Проверка политики, достигшей устройства Windows

Поступление политики для профиля регистрируется в журнале *DeviceManagement-Enterprise-Diagnostics-Provider* > **Администратор** с помощью идентификатора события **306**. 

Чтобы открыть файл журнала, выполните следующие действия:

1. На устройстве выполните **eventvwr.msc**, чтобы открыть средство просмотра событий Windows.

2. Разверните **Журналы приложений и служб** > **Майкрософт** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Администратор**.

3. Найдите событие **306**, подобное приведенному в следующем примере:

   ```
   Event ID:      306
   Task Category: None
   Level:         Information
   User:          SYSTEM
   Computer:      <Computer Name>
   Description:
   SCEP: CspExecute for UniqueId : (ModelName_<ModelName>_LogicalName_<LogicalName>_Hash_<Hash>) InstallUserSid : (<UserSid>) InstallLocation : (user) NodePath : (clientinstall)  KeyProtection: (0x2) Result : (Unknown Win32 Error code: 0x2ab0003).
   ```

   Код ошибки **0x2ab0003** преобразуется в **DM_S_ACCEPTED_FOR_PROCESSING**.

   Неудачный код ошибки может указывать на первоначальную проблему.

## <a name="next-steps"></a>Дальнейшие шаги

Если профиль достигает устройства, следующим шагом является проверка [устройства для связи с сервером NDES](troubleshoot-scep-certificate-device-to-ndes.md).
