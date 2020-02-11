---
title: Устранение неполадок при создании отчетов об успешном развертывании сертификатов на устройствах при использовании SCEP с Microsoft Intune | Документация Майкрософт
description: Устранение неполадок с отчетами NDES и соединителя в Intune об успешном развертывании сертификатов, которые были подготовлены с помощью профилей сертификатов SCEP.
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
ms.openlocfilehash: 2ccc738626efc140efca46d1b997164ed36dd37f
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916023"
---
# <a name="troubleshoot-ndes-reporting-of-certificate-deployments-in-microsoft-intune"></a>Устранение неполадок с отчетами NDES о развертываниях сертификатов в Microsoft Intune

Используйте следующие сведения, чтобы убедиться, что NDES и Microsoft Intune Certificate Connector успешно передают отчет Intune о том, что сертификат был доставлен на устройство. Создание отчетов для Intune — это последний этап использования профилей сертификатов SCEP для подготовки устройств Windows с помощью сертификата.

Эта статья относится к 6 шагу [рабочего процесса подключения SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-for-signs-of-successful-reporting"></a>Проверка на наличие успешных отчетов

Если отчет был успешным, вы найдете записи, аналогичные приведенным ниже примерам, на сервере NDES:

- **Журнал IIS**:

  `fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/Notify - 443 - fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 204 0 0 277 62`

- **NDESPlugin.log**:

  ```
  Calling Notifyrequest ...
  Sending request to certificate registration point.
  Exiting Notify with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  ![Журнал соединителя сертификатов Intune](../protect/media/troubleshoot-scep-certificate-reporting/certificate-registration-point-log.png)

- **NDESConnector.svclog**:

  ![Журнал соединителя сертификатов Intune](../protect/media/troubleshoot-scep-certificate-reporting/ndesconnector-log.png)

- **CertificateRequestStatus**:

  Откройте папку *%ProgramFiles%\Microsoft Intune\CertificateRequestStatus*, в которой вы увидите папки **Сбой**, **Обработка** и **Успешно**, содержащие файлы состояния запросов сертификатов.

  Если запрос сертификата успешно обработан, вы увидите, что в папке **Успешно** есть новые файлы. Вы можете использовать файл *Notepad. exe*, чтобы открыть файлы и просмотреть данные, передаваемые в службу Intune с помощью соединителя сертификатов Intune. Передаваемые данные содержат такие сведения, как **CertificateSerialNumber**, **UserID**, **DeviceID** и **Thumbprint**.

### <a name="troubleshoot-stuck-files"></a>Устранение неполадок с зависанием файлов

Если в папке *Успешно* не отображаются новые файлы, проверьте, не зависли ли они в папке *Обработка*.

Убедитесь, что служба соединителя Intune запущена на сервере NDES и в файле Ndesconnector.svclog нет ошибок.

## <a name="next-steps"></a>Дальнейшие шаги

[Получение поддержки для Microsoft Intune](../fundamentals/get-support.md)
