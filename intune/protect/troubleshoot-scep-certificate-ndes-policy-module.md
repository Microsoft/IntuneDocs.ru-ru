---
title: Устранение неполадок модуля политики Microsoft Intune Certificate Connector | Документация Майкрософт
description: Устранение неполадок в работе модуля политики NDES, когда модуль обрабатывает запрос на сертификат при использовании профилей сертификатов SCEP для развертывания сертификатов с помощью Intune.
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
ms.openlocfilehash: be53f6102226b004cab2bd953357e8c360a00f67
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915841"
---
# <a name="troubleshoot-the-ndes-policy-module-in-microsoft-intune"></a>Устранение неполадок модуля политики NDES в Microsoft Intune

Сведения из этой статьи помогут вам проверить работу модуля политики службы регистрации сертификатов для сетевых устройств (NDES), который устанавливается c помощью Microsoft Intune Certificate Connector. Когда NDES получает запрос на сертификат, он перенаправляет запрос в модуль политики, который проверяет, действителен ли запрос для устройства. После проверки NDES свяжется с центром сертификации (ЦС), чтобы запросить сертификат от имени устройства.

Эта статья ссылается на 3 и 4 этапы [рабочего процесса обмена данными SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="ndes-communication-to-the-policy-module"></a>Обмен данными между NDES и модулем политики

После получения запроса на сертификат от устройства NDES проверяет запрос с помощью Intune через модуль политики, который устанавливается с помощью Microsoft Intune Certificate Connector. Эти записи относятся к *точке регистрации сертификатов*.

**Записи журнала, указывающие на успешное выполнение**.

Чтобы убедиться, что запрос на проверку отправлен в модуль, найдите запись, похожую на следующие примеры в журналах на сервере NDES:

- **Журналы IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 - 
  fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 201 0 0 341 875
  ```

- **Журналы NDESPlugin**:

  ```
  Calling VerifyRequest ...  
  Sending request to certificate registration point.
  ```

  В следующем примере показано, как успешно выполнить проверку запроса для устройств и возможно ли NDES связаться с центром сертификации:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`


**Когда индикаторы успеха отсутствуют**.

Если вы не нашли эти записи, начните с изучения руководства по устранению неполадок для [устройства связи с сервером NDES](troubleshoot-scep-certificate-device-to-ndes.md#troubleshoot-common-errors).

Если сведения из этой статьи не помогут устранить проблему, ниже приведены дополнительные записи, которые могут указывать на проблемы.

### <a name="ndespluginlog-contains-an-error-12175"></a>NDESPlugin.log содержит ошибку 12175

Если в журнале содержится ошибка 12175, аналогичная приведенной ниже, может возникнуть проблема с SSL-сертификатом:

```
WINHTTP_CALLBACK_STATUS_FLAG_CERT_CN_INVALID
Failed to send http request /CertificateRegistrationSvc/Certificate/VerifyRequest. Error 12175
```

Современные браузеры и браузеры на мобильных устройствах пропускают *Общее имя* для SSL-сертификата, если присутствуют *Альтернативные имена субъектов*.

**Решение**.  Выдайте сертификат SSL веб-сервера со следующими атрибутами для *общего* и *альтернативного имени субъекта*, а затем привяжите его к порту 443 в IIS:

  - **Имя субъекта**.  
    CN = имя внешнего сервера.
  - **Альтернативное имя субъекта**.  
     Имя = имя внешнего сервера.  
     Имя DNS = имя внутреннего сервера.

### <a name="ndespluginlog-contains-an-error-403--forbidden-access-is-denied"></a>NDESPlugin.log содержит ошибку "403 — запрещено: доступ запрещен"

Если в следующих журналах содержится ошибка 403, аналогичная приведенной ниже, то сертификат клиента может быть ненадежным или недопустимым:

**NDESPlugin.log**:

```
Sending request to certificate registration point.
Verify challenge returns <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns="http://www.w3.org/1999/xhtml"> <head><meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>403 - Forbidden: Access is denied.</title>
```

**Журнал IIS**:

```
POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 -<IP_address>
NDES_Plugin - 403 16 2148204809 453  
```

Эта проблема возникает, если в хранилище сертификатов Доверенных корневых центров сертификации сервера NDES имеются промежуточные сертификаты ЦС.

Если сертификат имеет те же значения параметров *Кому выдан* и *Кем выдан*, это — корневой сертификат. В противном случае это промежуточный сертификат.

**Решение**. Чтобы устранить эту проблему, выявите и удалите промежуточные сертификаты ЦС из хранилища сертификатов Доверенных корневых центров сертификации.

### <a name="ndespluginlog-indicates-the-challenge-returns-false"></a>NDESPlugin.log указывает, что запрос возвращает значение False

Когда результат запроса возвращает значение **False**, проверьте *CertificateRegistrationPoint.svclog* на наличие ошибок. Например, может появиться сообщение об ошибке Signing certificate could not be retrieved (Не удалось получить сертификат для подписи), которая будет иметь следующий вид:

```
Signing certificate could not be retrieved. System.Security.Cryptography.CryptographicException: m_safeCertContext is an invalid handle. at System.Security.Cryptography.X509Certificates.X509Certificate.ThrowIfContextInvalid() at System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString() at Microsoft.ConfigurationManager.CertRegPoint.CRPCertificate.RetrieveSigningCert(String certThumbprint
```

**Решение**. На сервере, где установлен соединитель, откройте редактор реестра, найдите раздел реестра `HKLM\SOFTWARE\Microsoft\MicrosoftIntune\NDESConnector` и проверьте, существует ли значение SigningCertificate.

Если это значение не существует, перезапустите службу соединителя Intune в services.msc и проверьте, отображается ли значение в реестре. Если значение по-прежнему отсутствует, это часто происходит из-за проблем с сетевым подключением между сервером, на котором работает служба NDES и служба Intune.

## <a name="ndes-passes-the-request-to-issue-the-certificate"></a>NDES передает запрос на выдачу сертификата

После успешной проверки точки регистрации сертификатов (модуля политики) NDES передает запрос сертификата в ЦС от имени устройства.

**Записи журнала, указывающие на успешное выполнение**.

- **Журналы NDESPlugin**:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **Журналы IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe ... 80 - 
  fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 2713 1296
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`

**Когда индикаторы успеха отсутствуют**.

Если вы не видите записи, указывающие на успех, выполните следующие действия:

1. Найдите проблемы, которые зарегистрированы в *CertificateRegistrationPoint.svclog*, когда точка регистрации сертификатов проверяла проблему. Найдите записи между следующими строками:

   - VerifyRequest запущен.
   - VerifyRequest завершен с состоянием False.

2. Откройте MMC в центре сертификации и выберите **Неудачные запросы** для поиска ошибок, помогающих определить проблему. Ниже приведен пример экрана:

   ![Пример неудачного запроса](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/failed-requests.png)

3. Проверьте журнал событий приложений в центре сертификации на наличие ошибок. Обычно можно увидеть ошибки, которые совпадают с теми, что вы видите в **Неудачных запросах** с предыдущего этапа. Ниже приведен пример экрана:

   ![Проверка журнала приложений](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/application-log-errors.png)

## <a name="next-steps"></a>Дальнейшие шаги

Если модуль политики NDES проверяет запрос, который перенаправляется в центр сертификации, ознакомьтесь со сведениями о [доставке сертификатов на устройство](troubleshoot-scep-certificate-delivery.md).
