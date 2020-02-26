---
title: Устранение неполадок при обмене данными между управляемыми устройствами и службой NDES в Microsoft Intune | Документация Майкрософт
description: Устранение неполадок при обмене данными между управляемыми устройствами и сервером NDES с использованием профилей сертификатов SCEP для развертывания сертификатов с помощью Intune.
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
ms.openlocfilehash: 7945f1df3ddf1a6ff2c42a537e1071d1b5acff24
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514274"
---
# <a name="troubleshoot-device-to-ndes-server-communication-for-scep-certificate-profiles-in-microsoft-intune"></a>Устранение неполадок при обмене данными между устройствами и сервером NDES для профилей сертификатов SCEP в Microsoft Intune

Следующие сведения помогут определить, может ли устройство, которое получило и обработало профиль сертификата SCEP в Intune, успешно связаться со службой регистрации сетевых устройств (NDES), чтобы предоставить запрос защиты. На устройстве генерируется закрытый ключ, а запрос подписания сертификата (CSR) и запрос защиты передаются с устройства на сервер NDES. Чтобы связаться с сервером NDES, устройство использует универсальный код ресурса (URI) профиля сертификата SCEP.

Эта статья ссылается на шаг 2 [общих сведений о потоке обмена данными SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-iis-logs-for-a-connection-from-the-device"></a>Проверка журналов IIS на наличие соединения с устройством

Журналы IIS содержат записи одинакового типа для всех платформ.


1. На сервере NDES откройте самый последний файл журнала IIS в папке: *%SystemDrive%\inetpub\logs\logfiles\w3svc1*

2. Найдите в журнале записи, аналогичные приведенным ниже примерам. Оба примера содержат состояние **200**, которое отображается в конце.

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACaps&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 186 0.`

   И

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACert&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 3567 0`

3. Когда устройство обращается к журналу IIS, HTTP-запрос GET для файла mscep.dll заносится в журнал.

   Проверьте код состояния в конце этого запроса:
   - **Код состояния — 200**. Это состояние указывает на успешное подключение к серверу NDES.
   - **Код состояния — 500**. В группе IIS_IURS могут отсутствовать правильные разрешения. Ознакомьтесь с разделом [Код состояния 500](#status-code-500) далее в этой статье.
   - Если код состояния отличен от 200 или 500, выполните указанные ниже действия:

     - Чтобы получить сведения о проверке конфигурации, ознакомьтесь с разделом [Проверка URL-адреса сервера SCEP](#test-the-scep-server-url) далее в этой статье.

     - Чтобы получить сведения о менее распространенных кодах ошибок, ознакомьтесь со статьей [Коды состояния HTTP в IIS 7 и более поздних версиях](https://support.microsoft.com/help/943891).

   Если запрос на подключение не заносится в журнал, контакт с устройства может быть заблокирован в сети между устройством и сервером NDES.

## <a name="review-device-logs-for-connections-to-ndes"></a>Проверка журналов устройств на наличие подключений к NDES

### <a name="android-devices"></a>Устройства Android

Проверьте [журнал устройств OMADM](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Найдите записи, аналогичные приведенным ниже, которые регистрируются при подключении устройства к NDES:

```
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  There are 1 requests
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  Trying to enroll certificate request: ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c;Hash=1677525787
2018-02-27T05:16:09.5530000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:14.6440000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Received '200 OK' when sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.8220000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10 Encoding message: org.jscep.message.PkcsReq@2b06f45f[messageData=org.<server>.pkcs.PKCS10CertificationRequest@699b3cd,messageType=PKCS_REQ,senderNonce=Nonce [D447AE9955E624A56A09D64E2B3AE76E],transId=251E592A777C82996C7CF96F3AAADCF996FC31FF]
2018-02-27T05:16:21.8790000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10  Signing pkiMessage using key belonging to [dn=CN=<uesrname>; serial=1]
2018-02-27T05:16:21.9580000  VERB  Event  org.jscep.transaction.EnrollmentTransaction  18327     10  Sending org.<server>.cms.CMSSignedData@ad57775
```

В число ключевых записей входят следующие примеры текстовых строк:

- Имеется 1 запрос.
- Получен ответ "200 ОК" при отправке GetCACaps(ca) по адресу https://\<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca.
- Подпись pkiMessage с помощью ключа, принадлежащего [dn=CN=\<username>; serial=1].


Подключение также заносится в журнал IIS в папку %SystemDrive%\inetpub\logs\LogFiles\W3SVC1\ сервера NDES. Ниже приведен пример:

```
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACert&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 3909 0
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACaps&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 421 
```

### <a name="iosipados-devices"></a>Устройства iOS и iPadOS

Проверьте [журнал отладки устройств](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Найдите записи, аналогичные приведенным ниже, которые регистрируются при подключении устройства к NDES:

```
debug    18:30:53.691033 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\ 
debug    18:30:54.640644 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
default    18:30:55.483977 -0500    profiled    Attempting to retrieve issued certificate...\ 
debug    18:30:55.487798 -0500    profiled    Sending CSR via GET.\  
debug    18:30:55.487908 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQGZwmPoqFMbX3g85CJT8khPaqFW05yGDTPSX9YpuEE0Bmtht9EwOpOZe6O7sd77IhfFZVmHmwy5mIYN7K6mpx/4Cb5zcNmY3wmTBlKEkDQpZDRf5PpVQ3bmQ3we9XxeK1S4UsAXHVdYGD+bg/bCafMIAGCSqGSIb3DQEHATAUBggqhkiG9w0DBwQI5D5J2lwZS5OggASCF6jSG9iZA/EJ93fEvZYLV0v7GVo3JAsR11O7DlmkIqvkAg5iC6DQvXO1j88T/MS3wV+rqUbEhktr8Xyf4sAAPI4M6HMfVENCJTStJw1PzaGwUJHEasq39793nw4k268UV5XHXvzZoF3Os2OxUHSfHECOj
```

В число ключевых записей входят следующие примеры текстовых строк:

- operation=GetCACert;
- попытка получить выданный сертификат;
- отправка CSR с помощью GET;
- operation=PKIOperation.

### <a name="windows-devices"></a>Устройства Windows

На устройстве Windows, которое подключено к NDES, можно открыть средство просмотра событий Windows и найти указания об успешном подключении устройств. Подключения регистрируются в журнале как идентификатор события **36** в журнале устройств *DeviceManagement-Enterprise-Diagnostics-Provide* > **Администратор**.

Чтобы открыть файл журнала, выполните следующие действия:

1. На устройстве выполните **eventvwr.msc**, чтобы открыть средство просмотра событий Windows.

2. Разверните **Журналы приложений и служб** > **Майкрософт** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Администратор**.

3. Найдите событие **36**, которое напоминает следующий пример, со строкой ключа **SCEP: Certificate request generated successfully** (SCEP: запрос сертификата успешно создан):

   ```
   Event ID:      36
   Task Category: None
   Level:         Information
   Keywords:
   User:          <UserSid>
   Computer:      <Computer Name>
   Description:
   SCEP: Certificate request generated successfully. Enhanced Key Usage: (1.3.6.1.5.5.7.3.2), NDES URL: (https://<server>/certsrv/mscep/mscep.dll/pkiclient.exe), Container Name: (), KSP Setting: (0x2), Store Location: (0x1).
   ```

## <a name="troubleshoot-common-errors"></a>Устранение распространенных ошибок

Следующие разделы могут помочь в решении распространенных проблем с подключением всех платформ устройств к службе NDES.

### <a name="status-code-500"></a>Код состояния 500

Подключения, аналогичные приведенному ниже примеру, с кодом состояния 500 указывают, что право пользователя *Имитация клиента после проверки подлинности* не назначено группе IIS_IURS на сервере NDES. Значение состояния **500** отображается в конце:

```
2017-08-08 20:22:16 IP_address GET /certsrv/mscep/mscep.dll operation=GetCACert&message=SCEP%20Authority 443 - 10.5.14.22 profiled/1.0+CFNetwork/811.5.4+Darwin/16.6.0 - 500 0 1346 31
```

**Чтобы устранить проблему, выполните указанные ниже действия**:

1. На сервере NDES выполните **secpol.msc**, чтобы открыть локальную политику безопасности.

2. Разверните узел **Локальные политики**, а затем щелкните пункт **Назначение прав пользователей**.

3. Дважды щелкните **Имитация клиента после проверки подлинности** на правой панели.

4. Щелкните **Добавление группы или пользователя...** , введите **IIS_IURS** в поле **Введите имена выбираемых объектов**, а затем нажмите кнопку **ОК**.

5. Нажмите кнопку **ОК**.

6. Перезагрузите компьютер и повторите попытку подключения с устройства.

### <a name="test-the-scep-server-url"></a>Проверка URL-адреса сервера SCEP

Выполните следующие действия, чтобы проверить URL-адрес, указанный в профиле сертификата SCEP.

1. В Intune измените профиль сертификата SCEP и скопируйте URL-адрес сервера. URL-адрес должен выглядеть примерно так: *https://contoso.com/certsrv/mscep/msecp.dll* .

2. Откройте веб-браузер и перейдите по URL-адресу сервера SCEP. Результат должен быть следующим: **Ошибка: HTTP 403.0 — запрещено**. Этот результат указывает, что URL-адрес работает правильно.

   Если эта ошибка не возникает, выберите ссылку, которая соответствует ошибке, чтобы просмотреть рекомендации, относящиеся к проблеме.
   - [Я получаю общее сообщение службы регистрации сетевых устройств](#general-ndes-message).
   - [Я получаю сообщение об ошибке "Ошибка: HTTP 503 — служба недоступна"](#http-error-503).
   - [Я получаю сообщение об ошибке GatewayTimeout](#gatewaytimeout).
   - [Я получаю сообщение об ошибке "HTTP 414 — слишком длинный URI запроса"](#http-414-request-uri-too-long).
   - [Я получаю сообщение об ошибке This page can't be displayed](#this-page-cant-be-displayed) (Невозможно отобразить страницу).
   - [Я получаю сообщение об ошибке "500 — внутренняя ошибка сервера"](#internal-server-error).

#### <a name="general-ndes-message"></a>Общее сообщение NDES

При переходе по URL-адресу сервера SCEP вы получаете следующее сообщение службы регистрации сетевых устройств:

![URL-адрес SCEP-сервера](../protect/media/troubleshoot-scep-certificate-device-to-ndes/ndes-server-url-message.png)

- **Причина**. Эта проблема обычно связана с установкой соединителя Microsoft Intune.

  MSCEP.dll — это расширение ISAPI, которое перехватывает входящий запрос и отображает ошибку HTTP 403, если оно установлено правильно.
  
  **Решение**. Проверьте файл *SetupMsi.log*, чтобы определить, успешно ли установлен соединитель Microsoft Intune. В следующем примере состояния *Установка успешно завершена* и *Установка завершена с состоянием: 0* указывают, что установка прошла успешно:

  ```
  MSI (c) (28:54) [16:13:11:905]: Product: Microsoft Intune Connector -- Installation completed successfully.
  MSI (c) (28:54) [16:13:11:999]: Windows Installer installed the product. Product Name: Microsoft Intune Connector. Product Version: 6.1711.4.0. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.
  ```

  Если установка завершилась сбоем, удалите соединитель Microsoft Intune, а затем переустановите его.

#### <a name="http-error-503"></a>Ошибка HTTP 503

При переходе по URL-адресу сервера SCEP появляется следующее сообщение об ошибке:

![Ошибка: HTTP 503 — служба недоступна](../protect/media/troubleshoot-scep-certificate-device-to-ndes/service-unavailable.png)

Эта проблема обычно вызвана тем, что пул приложений **SCEP** в службах IIS не запущен. На сервере NDES откройте **Диспетчер IIS** и перейдите в раздел **Пулы приложений**. Найдите пул приложений **SCEP** и убедитесь, что он запущен.

Если пул приложений SCEP не запущен, проверьте журнал событий приложений на сервере:

1. На устройстве выполните **eventvwr.msc**, чтобы открыть компонент **Просмотр событий**, и последовательно выберите **Журналы Windows** > **Приложения**.

2. Найдите событие, подобное приведенному ниже, которое означает, что пул приложений аварийно завершает работу при получении запроса:

   ```
   Log Name:      Application
   Source:        Application Error
   Event ID:      1000
   Task Category: Application Crashing Events
   Level:         Error
   Keywords:      Classic
   Description: Faulting application name: w3wp.exe, version: 8.5.9600.16384, time stamp: 0x5215df96
   Faulting module name: ntdll.dll, version: 6.3.9600.18821, time stamp: 0x59ba86db
   Exception code: 0xc0000005
   ```

**Распространенные причины сбоя пула приложений**:

- **Причина 1**. В хранилище сертификатов Доверенных корневых центров сертификации сервера NDES присутствуют промежуточные сертификаты ЦС (без подписи).

  **Решение**. Удалите промежуточные сертификаты из хранилища сертификатов Доверенных корневых центров сертификации, а затем перезапустите сервер NDES.
  
  Чтобы найти все промежуточные сертификаты в хранилище сертификатов Доверенных корневых центров сертификации, выполните следующий командлет PowerShell: `Get-Childitem -Path cert:\LocalMachine\root -Recurse | Where-Object {$_.Issuer -ne $_.Subject}`

  Сертификат, имеющий одинаковые значения **Кому выдан** и **Кем выдан**, является корневым сертификатом. В противном случае это промежуточный сертификат.

  После удаления сертификатов и перезапуска сервера повторно запустите командлет PowerShell, чтобы убедиться в отсутствии промежуточных сертификатов. Если они присутствуют, проверьте, отправляет ли групповая политика промежуточные сертификаты на сервер NDES. Если это так, исключите сервер NDES из групповой политики и снова удалите промежуточные сертификаты.

- **Причина 2**. URL-адреса в списке отзыва сертификатов (CRL) заблокированы или недоступны для сертификатов, используемых соединителем сертификатов Intune.

  **Решение**. Включите дополнительное функции ведения журнала для сбора дополнительных сведений:
  1. Откройте средство просмотра событий, щелкните **Представление** и убедитесь, что установлен флажок **Отобразить аналитический и отладочный журналы**.
  2. Перейдите в раздел **Журналы приложений и служб** > **Microsoft** > **Windows** > **CAPI2** > **Работающий**, щелкните правой кнопкой мыши **Работающий**, а затем выберите **Включить журнал**.
  3. После включения ведения журнала CAPI2 воспроизведите проблему и изучите журнал событий, чтобы устранить ее.

- **Причина 3**. Для разрешения IIS в **CertificateRegistrationSvc** включен параметр **Проверка подлинности Windows**.

  **Решение**. Включите параметр **Анонимная проверка подлинности** и отключите параметр **Проверка подлинности Windows**, а затем перезапустите сервер NDES.

  ![Разрешения IIS](../protect/media/troubleshoot-scep-certificate-device-to-ndes/iis-permissions.png)

#### <a name="gatewaytimeout"></a>GatewayTimeout

При переходе по URL-адресу сервера SCEP появляется следующее сообщение об ошибке:

![Ошибка GatewayTimeout](../protect/media/troubleshoot-scep-certificate-device-to-ndes/gateway-timeout.png)

- **Причина**. Служба **Соединитель прокси-сервера приложений Microsoft AAD** не запущена.

  **Решение**.  Запустите **services.msc**, а затем убедитесь, что служба **Соединитель прокси-сервера приложений Microsoft AAD** запущена, а для параметра **Тип запуска** установлено значение **Автоматически**.

#### <a name="http-414-request-uri-too-long"></a>HTTP 414 — слишком длинный URI запроса

При переходе по URL-адресу сервера SCEP появляется следующее сообщение об ошибке: `HTTP 414 Request-URI Too Long`.

- **Причина**. Для фильтрации запросов IIS не настроена поддержка длинных URL-адресов (запросов), получаемых службой NDES. Это можно сделать при [настройке службы NDES](certificates-scep-configure.md#configure-the-ndes-service) для использования с инфраструктурой SCEP.

- **Решение**. Настройте поддержку длинных URL-адресов.

  1. В диспетчере IIS на сервере NDES выберите **Веб-сайт по умолчанию** > **Фильтрация запросов** > **Изменить параметры функций**, чтобы открыть страницу **Изменение параметров фильтрации запросов**.

  2. Настройте следующие параметры.
     - **Максимальная длина URL-адреса (байт)** = 65534
     - **Максимальная длина строки запроса (байт)** = 65534

  3. Нажмите кнопку **ОК**, чтобы сохранить конфигурацию и закрыть диспетчер IIS.

  4. Проверьте эту конфигурацию, просмотрев следующий раздел реестра, чтобы убедиться в том, что он содержит указанные значения:

     HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters

     Убедитесь, что в качестве записей DWORD установлены следующие значения:
     - Имя. **MaxFieldLength** с десятичным значением **65534**.
     - Имя. **MaxRequestBytes** с десятичным значением **65534**.

  5. Перезагрузите сервер NDES.

#### <a name="this-page-cant-be-displayed"></a>Невозможно отобразить страницу

Вы настроили Azure AD Application Proxy. При переходе по URL-адресу сервера SCEP появляется следующее сообщение об ошибке:

`This page can't be displayed`

- **Причина**. Эта проблема возникает, если в конфигурации прокси приложения указан неправильный внешний URL-адрес SCEP. Примером такого URL-адреса является https://contoso.com/certsrv/mscep/mscep.dll.

  **Решение**. Используйте домен по умолчанию *yourtenant.msappproxy.net* для внешнего URL-адреса SCEP в конфигурации прокси приложения.

#### <a name="internal-server-error"></a>500 — внутренняя ошибка сервера

При переходе по URL-адресу сервера SCEP появляется следующее сообщение об ошибке:

![500 — внутренняя ошибка сервера](../protect/media/troubleshoot-scep-certificate-device-to-ndes/500-internal-server-error.png)

- **Причина 1**. Учетная запись службы NDES заблокирована, или истек срок ее действия.

  **Решение**. Разблокируйте учетную запись или сбросьте пароль.

- **Причина 2**. Срок действия сертификатов MSCEP-RA истек.

  **Решение**. Если срок действия сертификатов MSCEP-RA истек, переустановите роль NDES или запросите новые сертификаты для шифрования CEP и агента регистрации Exchange (автономный запрос).

  Чтобы запросить новые сертификаты, выполните следующие действия.

  1. В центре сертификации (ЦС) или выдающем ЦС откройте средство MMC "Центр сертификации". Убедитесь, что пользователь, вошедший в систему, и сервер NDES имеют разрешения **чтения** и **регистрации** для шаблонов сертификатов шифрования CEP и агента регистрации Exchange (автономный запрос).

  2. Проверьте сертификаты с истекшим сроком действия на сервере NDES, скопируйте сведения о **субъекте** из сертификата.

  3. Откройте оснастку MMC "Сертификаты" для **учетной записи компьютера**.

  4. Разверните вкладку **Личные**, щелкните правой кнопкой мыши **Сертификаты**, а затем выберите **Все задачи** > **Запросить новый сертификат**.

  5. На странице **Запрос сертификата** щелкните **Шифрование CEP**, затем щелкните **Требуется больше данных для подачи заявки на этот сертификат. Щелкните здесь для настройки параметров**.

     ![Выбор шифрования CEP](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-scep-encryption.png)

  6. В окне **Свойства сертификата** щелкните вкладку **Субъект**, введите в поле **Имя субъекта** сведения, полученные на шаге 2, нажмите кнопку **Добавить**, а затем — **ОК**.

  7. Завершите регистрацию сертификата.

  8. Откройте оснастку MMC "Сертификаты" в **учетной записи пользователя**.

     Регистрировать сертификат агента регистрации Exchange (автономный запрос) нужно в контексте пользователя, так как параметр **Тип субъекта** этого шаблона сертификата имеет значение **Пользователь**.

  9. Разверните вкладку **Личные**, щелкните правой кнопкой мыши **Сертификаты**, а затем выберите **Все задачи** > **Запросить новый сертификат**.

  10. На странице **Запрос сертификата** щелкните **Агент регистрации Exchange (автономный запрос)** , затем щелкните **Требуется больше данных для подачи заявки на этот сертификат. Щелкните здесь для настройки параметров**.

      ![Выбор агента регистрации Exchange](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-exchange-enrollment-agent.png)

  11. В окне **Свойства сертификата** щелкните вкладку **Субъект**, введите в поле **Имя субъекта** сведения, полученные на шаге 2, нажмите кнопку **Добавить**.

      ![Свойства сертификата](../protect/media/troubleshoot-scep-certificate-device-to-ndes/certificate-properties.png)

      Откройте вкладку **Закрытый ключ**, щелкните **Сделать закрытый ключ экспортируемым**, а затем нажмите кнопку **ОК**.

      ![Закрытый ключ](../protect/media/troubleshoot-scep-certificate-device-to-ndes/private-key.png)

  12. Завершите регистрацию сертификата.

  13. Экспортируйте сертификат агента регистрации Exchange (автономный запрос) из хранилища сертификатов текущего пользователя. В мастере экспорта сертификата установите флажок **Да, экспортировать закрытый ключ**.

  14. Импортируйте сертификат в хранилище сертификатов локального компьютера.

  15. В оснастке MMC "Сертификаты" выполните следующие действия для каждого из новых сертификатов.

      Щелкните сертификат правой кнопкой мыши, выберите **Все задачи** > **Управление закрытыми ключами** и добавьте разрешение на **чтение** в учетную запись службы NDES.

  16. Выполните команду **iisreset**, чтобы перезапустить IIS.

## <a name="next-steps"></a>Дальнейшие шаги

Если устройство успешно связывается с сервером NDES и передает запрос на сертификат, ознакомьтесь с [модулями политики Intune Certificate Connectors](troubleshoot-scep-certificate-ndes-policy-module.md).
