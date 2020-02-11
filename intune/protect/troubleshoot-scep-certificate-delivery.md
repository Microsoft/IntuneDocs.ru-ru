---
title: Устранение неполадок при доставке сертификатов на устройства при использовании SCEP с Microsoft Intune | Документация Майкрософт
description: Устранение неполадок при доставке сертификата на устройство из центра сертификации при использовании профилей сертификатов SCEP с Intune для развертывания сертификатов.
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
ms.openlocfilehash: 77be59d126dc7e73bee468ca938938c6bb1b2e1a
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915880"
---
# <a name="troubleshoot-the-delivery-of-certificates-provisioned-by-scep-to-devices-in-microsoft-intune"></a>Устранение неполадок при доставке сертификатов, подготовленных SCEP, на устройства в Microsoft Intune

Сведения их этой статьи помогут вам исследовать доставку сертификатов на устройства при использовании SCEP для подготовки сертификатов в Intune. После того как служба регистрации сертификатов для сетевых устройств (NDES) получает запрошенный сертификат для устройства из центра сертификации (ЦС), она передает его обратно на устройство.

Эта статья содержит ссылки на этап 5 [рабочего процесса связи SCEP](troubleshoot-scep-certificate-profiles.md); доставки сертификата на устройство, отправившего запрос на сертификат.

## <a name="review-the-certification-authority"></a>Проверка центра сертификации

После выдачи сертификата ЦС вы увидите запись, аналогичную приведенному ниже примеру в ЦС:

![Пример выданных сертификатов](../protect/media/troubleshoot-scep-certificate-delivery/certificate-authority.png)

## <a name="review-the-device"></a>Проверка устройства

### <a name="android"></a>Android

Для устройств, зарегистрированных в администраторе устройств, вы увидите уведомление, аналогичное приведенному ниже, в котором предлагается установить сертификат:

![Уведомление Android](../protect/media/troubleshoot-scep-certificate-delivery/android-notification.png)

Для Android Enterprise или Samsung Knox установка сертификата осуществляется автоматически и без вмешательства пользователя.

Чтобы просмотреть установленный сертификат на Android, используйте стороннее приложение для просмотра сертификатов.

Кроме того, вы можете проверить [журнал устройств OMADM](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Найдите записи, похожие на приведенные ниже, которые регистрируются при установке сертификатов:

**Корневой сертификат**.

```
2018-02-27T04:50:52.1890000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        9    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALL_REQUESTED
2018-02-27T04:53:31.1300000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        0    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T04:53:32.0390000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595       14    Root cert '17…' state changed from CERT_INSTALLING to CERT_INSTALL_SUCCESS
```

**Сертификат, подготовленный через SCEP**

```
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    There are 1 requests
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    Trying to enroll certificate request: ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787
2018-02-27T05:16:20.6150000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:20.6530000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:21.7460000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.7890000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:28.0340000    VERB    Event     org.jscep.transaction.EnrollmentTransaction    18327       10    Response: org.jscep.message.CertRep@3150777b[failInfo=<null>,pkiStatus=SUCCESS,recipientNonce=Nonce [GUID],messageData=org.spongycastle.cms.CMSSignedData@27cc8998,messageType=CERT_REP,senderNonce=Nonce [GUID],transId=TRANSID]
2018-02-27T05:16:28.2440000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       10    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ENROLLED to CERT_INSTALL_REQUESTED
2018-02-27T05:18:44.9820000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327        0    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T05:18:45.3460000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       14    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALLING to CERT_ACCESS_REQUESTED
2018-02-27T05:20:15.3520000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       21    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ACCESS_REQUESTED to CERT_ACCESS_GRANTED
```

### <a name="ios-and-ipados"></a>iOS и iPadOS

На устройстве iOS или iPadOS можно просмотреть сертификат в профиле управления устройствами. Изучите сведения об установленных сертификатах.

![Сертификат iOS](../protect/media/troubleshoot-scep-certificate-delivery/ios-certificate.png)

Кроме того, в [журналах отладки iOS](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices) можно найти записи, аналогичные приведенным ниже:

```
Debug 18:30:53.691033 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\  
Debug 18:30:54.640644 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
Debug 18:30:55.487908 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQG 
Debug 18:30:57.285730 -0500 profiled Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 in domain ManagedProfileToManagingProfile to system\ 
Default 18:30:57.320616 -0500 profiled Profile \'93www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295\'94 installed.\ 
```

### <a name="windows"></a>Windows

На устройстве Windows убедитесь, что сертификат был доставлен:

- Запустите **eventvwr.msc**, чтобы открыть средство просмотра событий. Перейдите в раздел **Журналы приложений и служб** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Администратор** и найдите **Событие 39**. Это событие должно иметь общее описание: **SCEP: сертификат успешно установлен.**

   ![Событие 39 в журнале приложений Windows](../protect/media/troubleshoot-scep-certificate-delivery/device-app-log.png)

Чтобы просмотреть сертификат на устройстве, запустите **certmgr.msc** для открытия оснастки MMC "Сертификаты" и убедитесь, что корневые и SCEP-сертификаты установлены правильно на устройстве в личном хранилище:

   1. Перейдите в раздел **Сертификаты (локальный компьютер)**  > **Доверенные корневые центры сертификации** > **Сертификаты** и убедитесь в наличии корневого сертификата из центра сертификации. Значения для параметров *Кому выдан* и *Кем выдан* будут одинаковыми.
   2. В оснастке MMC "Сертификаты" перейдите в раздел **Сертификаты — текущий пользователь** > **Личные** > **Сертификаты** и убедитесь в наличии запрошенного сертификата со значением *Кем выдан*, совпадающим с именем ЦС.

## <a name="troubleshoot-failures"></a>Устранение сбоев

### <a name="android"></a>Android

Чтобы устранить эту проблему, проверьте ошибки, зарегистрированные в журнале OMA DM.

### <a name="ios-and-ipados"></a>iOS и iPadOS

Чтобы устранить эту проблему, проверьте ошибки, зарегистрированные в журнале отладки устройств.

### <a name="windows"></a>Windows

Чтобы устранить неполадки, связанные с тем, что сертификат не устанавливается на устройстве, просмотрите журнал событий Windows на наличие ошибок, сообщающих о проблемах:

- Выполните **eventvwr.msc** на устройстве, чтобы открыть средство просмотра событий, а затем перейдите в раздел **Журналы приложений и служб** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Администратор**.

Ошибки доставки и установки сертификата на устройстве обычно связаны с операциями Windows, а не Intune.

## <a name="next-steps"></a>Дальнейшие шаги

Если сертификат успешно развернут на устройстве, но Intune не сообщает об успешном выполнении, см. статью [Troubleshoot NDES reporting of certificate deployments in Microsoft Intune](troubleshoot-scep-certificate-reporting.md) (Устранение неполадок с отчетами NDES о развертываниях сертификатов в Microsoft Intune) для устранения неполадок при отчетах.
