---
title: Выдача сертификатов DigiCert PKCS с помощью Microsoft Intune
titleSuffix: Microsoft Intune
description: Установите и настройте Intune Certificate Connector для выдачи сертификатов PKCS платформы DigiCert PKI для устройств, управляемых в Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1679eb656e04296e53d8994dcd47144621c99d0c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721777"
---
# <a name="set-up-intune-certificate-connector-for-digicert-pki-platform"></a>Настройка Intune Certificate Connector для платформы DigiCert PKI  

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

С помощью Intune Certificate Connector можно выдавать сертификаты PKCS платформы DigiCert PKI для устройств, управляемых в Intune. Этот соединитель можно использовать только с центром сертификации DigiCert или одновременно с центрами сертификации DigiCert и Майкрософт.  
> [!TIP]  
> Компания DigiCert приобрела у Symantec бренд Website Security и связанные с ним решения PKI. Дополнительные сведения об этом изменении см. в [статье от технической поддержки Symantec](https://support.symantec.com/en_US/article.INFO4722.html).

Если вы уже используете Intune Certificate Connector для выдачи сертификатов центра сертификации (ЦС) Майкрософт по технологиям PKCS и SCEP, то можете использовать этот соединитель для настройки и выдачи сертификатов PKCS из ЦС DigiCert. Когда вы завершите настройку конфигурации, необходимой для ЦС DigiCert, Intune Certificate Connector сможет выдавать следующие сертификаты:

* сертификаты PKCS из ЦС Майкрософт;
* сертификаты PKCS из ЦС DigiCert;
* сертификаты Endpoint Protection из ЦС Майкрософт.

Если соединитель не установлен, но вы намерены использовать его одновременно для центров сертификации Майкрософт и DigiCert, сначала настройте соединитель для ЦС Майкрософт. Затем вернитесь к этой статье, чтобы настроить поддержку DigiCert. Дополнительные сведения о профилях сертификатов и соединителе см. в статье [Использование сертификатов для проверки подлинности в Microsoft Intune](certificates-configure.md).  

Если вы будете использовать соединитель только для центра сертификации DigiCert, можно сразу установить и настроить соединитель по инструкциям из этой статьи. 

## <a name="prerequisites"></a>Предварительные условия  
- **Действующая подписка ЦС DigiCert**. Эта подписка необходима для получения сертификата центра регистрации (RA) из центра сертификации DigiCert.

## <a name="install-the-digicert-ra-certificate"></a>Установка сертификата ЦС DigiCert  
 
1. Сохраните представленный ниже фрагмент кода в файл с именем **certreq.ini** и внесите в него соответствующие изменения (например, *имя субъекта в формате CN*).
 
        [Version] 
        Signature="$Windows NT$" 
        
        [NewRequest] 
        ;Change to your,country code, company name and common name 
        Subject = "Subject Name in CN format"
        
        KeySpec = 1 
        KeyLength = 2048 
        Exportable = TRUE 
        MachineKeySet = TRUE 
        SMIME = False 
        PrivateKeyArchive = FALSE 
        UserProtected = FALSE 
        UseExistingKeySet = FALSE 
        ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
        ProviderType = 12 
        RequestType = PKCS10 
        KeyUsage = 0xa0 
        
        [EnhancedKeyUsageExtension] 
        OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication
        
        ;----------------------------------------------- 

2. Откройте командную строку с повышенными привилегиями и создайте CSR-файл, выполнив следующую команду:

   `Certreq.exe -new certreq.ini request.csr`

3. Откройте файл request.csr в Блокноте и скопируйте содержимое CSR-файла, которое имеет следующий формат:


        -----BEGIN NEW CERTIFICATE REQUEST-----
        MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
        …
        …
        fzpeAWo=
        -----END NEW CERTIFICATE REQUEST-----


4. Войдите в ЦС DigiCert и выберите **Get an RA Cert** (Получить сертификат центра регистрации) в списке задач.

   a. В текстовое поле поместите содержимое CSR-файла, полученное на шаге 3. 

   b. Введите понятное имя для сертификата.

   c. Щелкните **Продолжить**. 

   d. Скачайте сертификат RA на локальный компьютер по предоставленной ссылке.

5. Импортируйте сертификат RA в хранилище сертификатов Windows, выполнив следующие действия:

   a. Откройте консоль MMC.

   b. Выберите **Файл** > **Добавление и удаление оснасток** > **Сертификат** > **Добавить**. 

   c. Выберите **Учетная запись компьютера** > **Далее**.

   d. Выберите **Локальный компьютер** > **Готово**. 

   д. Щелкните **ОК** в окне **Добавление или удаление оснасток**. Разверните **Certificates (Local Computer)** (Сертификаты на локальном компьютере)  > **Личные** > **Сертификаты**.

   f. Щелкните правой кнопкой мыши узел **Сертификаты** и выберите **Все задачи** > **Импорт**.  

   ж. Выберите расположение сертификата RA, который вы скачали из ЦС DigiCert, и щелкните **Далее**.

   з. Выберите **Personal Certificate Store** (Персональное хранилище сертификатов)  > **Далее**. 

   и. Щелкните **Готово**, чтобы импортировать сертификат RA вместе с его закрытым ключом в хранилище **Личное** на локальном компьютере.  

6. Выполните экспорт и импорт сертификата закрытого ключа, выполнив следующие действия: 

   a. Разверните **Certificates (Local Machine)** (Сертификаты (локальный компьютер))  > **Личные** > **Сертификаты**.

   b. Выберите сертификат, импортированный на предыдущем шаге.

   c. Щелкните сертификат правой кнопкой мыши и выберите **Все задачи** > **Экспорт**.

   d. Щелкните **Далее** и введите пароль.

   д. Выберите расположение для экспорта и щелкните **Готово**.

   f. Повторите процедуру, выполнявшуюся на шаге 5, чтобы импортировать сертификат закрытого ключа в хранилище **Личное** на локальном компьютере.

   ж. Скопируйте отпечаток сертификата RA без пробелов. Ниже приведен пример такого отпечатка. 

        RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
    
    > [!NOTE]
    > Вы можете обратиться в [службу поддержи пользователей DigiCert](mailto:enterprise-pkisupport@digicert.com) за помощью в получении сертификата RA из ЦС DigiCert.  

## <a name="prepare-to-install-intune-certificate-connector"></a>Подготовка к установке Intune Certificate Connector
> [!TIP]  
> Этот раздел относится к случаю использования Intune Certificate Connector только с центром сертификации DigiCert. Если вы используете Intune Certificate Connector с центром сертификации Майкрософт и хотите добавить поддержку центра сертификации DigiCert, перейдите к разделу [о настройке соединителя для работы с DigiCert](#configure-the-connector-to-support-digicert) далее.  

1. Выберите и установите на компьютер одну из следующих версий операционной системы Windows:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard.

2. Создайте пользователя с правами администратора и используйте его, чтобы выполнить следующие шаги.

3. Проверьте наличие обновлений для Windows и установите их, если они доступны. После установки обновлений Windows перезагрузите компьютер.

4. Установите .NET Framework 3.5, выполнив следующие действия:

   a. Откройте **Панель управления** > **Программы и компоненты** > **Включение или отключение компонентов Windows**.

   b. Выберите и установите **.NET Framework 3.5**.  

## <a name="install-intune-certificate-connector-for-use-with-digicert"></a>Установка Intune Certificate Connector для работы с DigiCert  

> [!TIP]  
> Если вы используете Intune Certificate Connector с центром сертификации Майкрософт и хотите добавить поддержку центра сертификации DigiCert, перейдите к разделу [о настройке соединителя для работы с DigiCert](#configure-the-connector-to-support-digicert) далее.  

Скачайте последнюю версию Intune Certificate Connector на портале администрирования Intune, а затем выполните эти инструкции.

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Выберите **Конфигурация устройства** > **Соединители сертификатов** >  **+Добавить**.  

3. Щелкните **Download the certificate connector software** (Скачать соединитель сертификатов). Сохраните эту программу в такое расположение, которое будет доступно на том сервере, где вы будете ее устанавливать.  

   ![Скачивание соединителя сертификатов](./media/certificates-digicert-configure/connector-download.png)
   
4. Теперь запустите **NDESConnectorSetup.exe** с повышенными привилегиями на сервере, где нужно установить соединитель. 

5. На странице **Параметры установки** выберите **PFX Distribution** (Распределение PFX).  
   
   ![Выбор распространения PFX](./media/certificates-digicert-configure/digicert-ca-connector-install.png)

   > [!IMPORTANT]
   > Если вы используете Intune Certificate Connector для выдачи сертификатов из ЦС Майкрософт и DigiCert, выберите **Распределение профилей SCEP и PFX**. 

6. Сохраните настройки по умолчанию и завершите настройку соединителя.

## <a name="configure-the-connector-to-support-digicert"></a>Настройка поддержки DigiCert в соединителе

По умолчанию Intune Certificate Connector устанавливается в папке **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc**.

1. Перейдите к папке **NDESConnectorSvc** и откройте файл **NDESConnector.exe.config** в Блокноте.

   a. Замените значение ключа `RACertThumbprint` значением отпечатка сертификата, который вы скопировали ранее. Пример.

        <add key="RACertThumbprint"
        value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   
   b. Сохраните и закройте файл.

2. Откройте **services.msc**.

   a. Выберите **Intune Connector Service** (Служба соединителя Intune).

   b. Остановите, а затем снова запустите службу.

   c. Закройте окно "Службы".

## <a name="set-up-the-intune-administrator-account"></a>Настройка учетной записи администратора службы Intune  

> [!TIP]  
> Если вы используете Intune Certificate Connector с центром сертификации Майкрософт и хотите добавить поддержку центра сертификации DigiCert, перейдите к разделу [о создании профиля доверенного сертификата](#create-a-trusted-certificate-profile) далее.   
 
1. Откройте пользовательский интерфейс соединителя NDES Connector, запустив файл **C:\%Program Files%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe**.  

2. На вкладке **Регистрация** щелкните **Войти**.

3. Укажите учетные данные администратора клиента Intune.

4. Щелкните **Вход** и подтвердите успешность регистрации кнопкой **OK**. Теперь можно закрыть пользовательский интерфейс соединителя NDES Connector.
   
   ![Интерфейс соединителя NDES Connector с сообщением об успешной регистрации](./media/certificates-digicert-configure/certificates-digicert-configure-connector-configure.png)



## <a name="create-a-trusted-certificate-profile"></a>Создание профиля доверенного сертификата

Сертификаты PKCS, которые вы развернете для устройств под управлением Intune, должны быть связаны с доверенным корневым сертификатом. Для настройки такой цепочки создайте профиль доверенного сертификата Intune с корневым сертификатом, полученным из ЦС DigiCert.

1. Получите доверенный корневой сертификат из ЦС DigiCert, выполнив следующие действия:

    a. Войдите на портал администрирования ЦС DigiCert.

    b. Выберите **Manage CAs** (Управление ЦС) из списка **Задачи**. 

    c. Выберите из списка нужный ЦС.  

    d. Щелкните **Download root certificate** (Скачать корневой сертификат), чтобы скачать доверенный корневой сертификат.

2. Создайте профиль доверенного сертификата, выполнив следующие действия на портале Intune.

   a. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

   b. Выберите **Конфигурация устройства** > **Управление** > **Профили** > **Создать профиль**.

   c. Введите **Имя** и **Описание** профиля доверенного сертификата.

   d. Из раскрывающегося списка **Платформа** выберите платформу устройств для этого доверенного сертификата.

   д. Из раскрывающегося списка **Тип профиля** выберите **Доверенный сертификат**.

   f. Перейдите к CER-файлу доверенного корневого ЦС, который вы получили из центра сертификации DigiCert на предыдущем шаге, и щелкните **OK**.

   ж. Выберите конечное хранилище для доверенного сертификата из следующих вариантов расположений (это касается только устройств Windows 8.1 и Windows 10):    
      - **хранилище сертификатов на компьютере — корневое**;  
      - **хранилище сертификатов на компьютере — промежуточное**;  
      - **хранилище сертификатов пользователей — промежуточное**. 

   з. По завершении нажмите **OK**, вернитесь на страницу **Создание профиля** и выберите **Создать**.  
 
Профиль появится в списке профилей на панели **Конфигурация устройства — профили** с типом профиля **Доверенный сертификат**.  Не забудьте назначить этот профиль устройствам, которые будут получать сертификаты. Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройств](../configuration/device-profile-assign.md).


## <a name="get-the-certificate-profile-oid"></a>Получение идентификатора объекта для профиля сертификата  

Идентификатор объекта для профиля сертификата связан с шаблоном профиля сертификата в ЦС DigiCert. Чтобы создать профиль сертификата PKCS в Intune, укажите имя шаблона сертификата в формате идентификатора объекта для профиля сертификата, который связан с шаблоном сертификата в ЦС DigiCert.

1. Войдите на портал администрирования ЦС DigiCert.
2. Выберите **Manage Certificate Profiles** (Управление профилями сертификатов).
3. Выберите профиль сертификата, который вы намерены использовать.
4. Скопируйте идентификатор объекта для профиля сертификата. Он имеет следующий вид.

 
       Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
 

> [!NOTE]
> Если вам потребуется помощь в получении идентификатора объекта для профиля сертификата, свяжитесь со [службой поддержки пользователей DigiCert](mailto:enterprise-pkisupport@digicert.com).

## <a name="create-a-pkcs-certificate-profile"></a>Создание профиля сертификата PKCS

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Перейдите к разделу **Конфигурация устройств** >  **Профили** и щелкните **Создать профиль**.

3. Введите **Имя** и **Описание** профиля сертификата PKCS.  

4. Из раскрывающегося списка **Платформа** выберите поддерживаемую платформу устройств.

5. В раскрывающемся списке **Тип профиля** выберите **Сертификат PKCS**.
 
6. В области **Сертификат PKCS** настройте параметры по данным из следующей таблицы. Эти значения позволяют выдавать сертификаты PKCS из ЦС DigiCert через Intune Certificate Connector. 

   |Параметр сертификата PKCS | Значение | Описание |
   | --- | --- | --- |
   | Центр сертификации | pki-ws.symauth.com | Это значение должно представлять собой полное доменное имя базовой службы ЦС DigiCert без замыкающей косой черты. Если вы не уверены, что у вас есть правильное полное доменное имя базовой службы для подписки ЦС DigiCert, свяжитесь со службой поддержки пользователей DigiCert. <br><br>*После смены Symantec на DigiCert этот URL-адрес не изменился*. <br><br> Если полное доменное имя неверное, Intune Certificate Connector не будет выдавать сертификаты PKCS из ЦС DigiCert.| 
   | Certificate authority name (Имя центра сертификации) | Symantec | Значение **Symantec** должно быть строковым. <br><br> При любых изменениях этого значения Intune Certificate Connector не будет выдавать сертификаты PKCS из ЦС DigiCert.|
   | Имя шаблона сертификата | Идентификатор объекта для профиля сертификата из ЦС DigiCert. Пример. **2.16.840.1.113733.1.16.1.2.3.1.1.61904612**| Это значение нужно указать в качестве идентификатора объекта для профиля сертификата, который был получен [ранее](#get-the-certificate-profile-oid) из шаблона профиля сертификата ЦС DigiCert. <br><br> Если Intune Certificate Connector не удается найти шаблон сертификата, связанный с идентификатором объекта для профиля сертификата в ЦС DigiCert, он не будет выдавать сертификаты PKCS из ЦС DigiCert.|  

   ![Параметры для шаблона ЦС и сертификата](./media/certificates-digicert-configure/certificates-digicert-pkcs-example.png)  

   > [!NOTE]
   > Профиль сертификата PKCS для платформ Windows не нужно связывать с профилем доверенного сертификата. Однако это необходимо сделать для профилей платформ не на базе Windows, например для Android.
7. Завершите настройку профиля в соответствии с потребностями вашей организации, а затем щелкните **OK**, чтобы сохранить этот профиль. 

8. Щелкните **Назначения** и настройте группу, которая получит этот профиль. По крайней мере один пользователь или одно устройство должно входить в назначенную группу.
 
После выполнения предыдущих шагов Intune Certificate Connector будет выдавать сертификаты PKCS из ЦС DigiCert устройствам, управляемым Intune, которые включены в назначенную группу. Эти сертификаты будут доступны в **личном** хранилище сертификатов **текущего пользователя** на устройстве под управлением Intune.

### <a name="supported-attributes-for-the-pkcs-certificate-profile"></a>Поддерживаемые атрибуты профиля сертификатов PKCS

|Атрибут | Форматы, поддерживаемые Intune | Форматы, поддерживаемые ЦС DigiCert Cloud | result |
| --- | --- | --- | --- |
| Имя субъекта |Intune поддерживает имя субъекта только в следующих трех форматах: <br><br> 1. Общее имя <br> 2. Обычное имя с адресом электронной почты. <br> 3. Обычное имя как адрес электронной почты. <br><br> Пример. <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | ЦС DigiCert поддерживает дополнительные атрибуты.  Если вы хотите выбрать дополнительные атрибуты, их нужно определить с фиксированными значениями в шаблоне профиля сертификатов DigiCert.| Мы используем обычное имя или адрес электронной почты из запроса на сертификат PKCS. <br><br> Любые несоответствия в атрибутах между профилем сертификатов Intune и профилем сертификатов DigiCert приведут к тому, что ЦС DigiCert не будет выдавать сертификаты.|
| SAN | Intune поддерживает только следующие значения полей SAN. <br><br> **AltNameTypeEmail** <br> **AltNameTypeUpn** <br> **AltNameTypeOtherName** (зашифрованное значение) | ЦС DigiCert Cloud также поддерживает эти параметры. Если вы хотите выбрать дополнительные атрибуты, их нужно определить с фиксированными значениями в шаблоне профиля сертификатов DigiCert. <br><br> **AltNameTypeEmail**: Если этот тип отсутствует в SAN, Intune Certificate Connector применяет значение параметра **AltNameTypeUpn**.  Если **AltNameTypeUpn** также отсутствует в SAN, тогда Intune Certificate Connector использует значение из имени субъекта, которое имеет формат адреса электронной почты.  Если и таким способом не удается найти этот тип, Intune Certificate Connector не выдает сертификаты. <br><br> Пример: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> **AltNameTypeUpn**: Если этот тип отсутствует в SAN, Intune Certificate Connector применяет значение параметра **AltNameTypeEmail**. Если **AltNameTypeEmail** также отсутствует в SAN, тогда Intune Certificate Connector использует значение из имени субъекта, которое имеет формат адреса электронной почты. Если и таким способом не удается найти этот тип, Intune Certificate Connector не выдает сертификаты.  <br><br> Пример: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> **AltNameTypeOtherName**: Если этот тип отсутствует в SAN, Intune Certificate Connector не выдает сертификаты. <br><br> Пример: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  Обратите внимание, что ЦС DigiCert принимает значение этого поля только в закодированном формате (шестнадцатеричное значение). Любое значение этого поля Intune Certificate Connector преобразовывает в закодированный формат Base64, прежде чем отправлять запрос на сертификат. *Intune Certificate Connector не проверяет, закодировано ли это значение или нет.* | Нет |

## <a name="troubleshooting"></a>Диагностика

Журналы службы Intune Certificate Connector доступны на компьютере соединителя NDES Connector в папке **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs**. Откройте журналы в [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) и выполните поиск исключений или сообщений об ошибках.

| Сообщения о проблемах и ошибках | Инструкции по устранению |
| --- | --- |
| Не удается выполнить вход с помощью учетной записи администратора клиента Intune в пользовательском интерфейсе соединителя NDES Connector. | Это может произойти, если локальный соединитель сертификатов не включен на портале администрирования Intune. Для устранения этой проблемы примените любую из следующих процедур. <br><br> В пользовательском интерфейсе Silverlight: <br> 1. Войдите на [портал администрирования Intune](https://admin.manage.microsoft.com). <br> 2. Выберите **ADMIN** (Администрирование). <br> 3. Выберите **Управление мобильными устройствами** > **Certificate Connector** (Соединитель сертификатов). <br> 4. Щелкните **Configure On-premises Certificate Connector** (Настройка локального соединителя сертификатов). <br> 5. Установите флажок **Enable Certificate Connector** (Включить соединитель сертификатов). <br> 6. Нажмите кнопку **ОК**. <br><br> В интерфейсе пользователя на портале Azure сделайте следующее: <br> 1. Войдите на [портал Azure](https://portal.azure.com). <br> 2. Перейдите к Microsoft Intune. <br> 3. Выберите **Device Configuration** (Настройка устройств) > **Certificate Authority** (Центр сертификации). <br> 4. Выберите **Включить**. <br><br> Выполнив предыдущие шаги в пользовательском интерфейсе Silver Light или на портале Azure, попробуйте войти с той же учетной записью администратора клиента Intune в пользовательском интерфейсе соединителя NDES Connector. |
| Соединитель NDES: certificate could not be found (не удается найти сертификат соединителя NDES). <br><br> System.ArgumentNullException: не может иметь значение NULL. | В Intune Certificate Connector отображается это сообщение об ошибке, если с помощью учетной записи администратора клиента Intune никогда не выполнялся вход в пользовательский интерфейс соединителя NDES. <br><br> Если ошибка повторится, перезапустите соединитель службы Intune. <br><br> 1. Откройте **services.msc**. <br> 2. Выберите **Intune Connector Service** (Служба соединителя Intune). <br> 3. Щелкните правой кнопкой мыши и выберите **Перезапуск**.|
| Соединитель NDES — IssuePfx — общее исключение: <br> System.NullReferenceException. Ссылка на объект не указывает на экземпляр объекта. | Это временная ошибка. Перезапустите соединитель службы Intune. <br><br> 1. Откройте **services.msc**. <br> 2. Выберите **Intune Connector Service** (Служба соединителя Intune). <br> 3. Щелкните правой кнопкой мыши и выберите **Перезапуск**. |
| Поставщик DigiCert — не удалось получить политику DigiCert. <br><br>"The operation has timed out" (Время операции истекло). | Intune Certificate Connector получил сообщение об ошибке, в котором указано, что время ожидания операции истекло при обращении к ЦС DigiCert. Если эта ошибка повторяется, увеличьте время ожидания соединения и повторите попытку. <br><br> Чтобы увеличить время ожидания соединения, сделайте следующее: <br> 1. Перейдите к компьютеру соединителя NDES Connector. <br>2. Откройте файл **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config** в Блокноте. <br> 3. Увеличьте значение времени ожидания в следующем параметре: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Перезапустите службу Intune Certificate Connector. <br><br> Если проблема сохранится, обратитесь в службу поддержки пользователей DigiCert. |
| Поставщик DigiCert — не удалось получить сертификат клиента. | Intune Certificate Connector не удалось получить сертификат авторизации ресурсов из хранилища сертификатов "Личное" на локальном компьютере. Чтобы устранить эту проблему, установите сертификат авторизации ресурсов в хранилище сертификатов "Личное" на локальном компьютере вместе с закрытым ключом. <br><br> Сертификат авторизации ресурсов должен быть получен из ЦС DigiCert. Чтобы получить дополнительные сведения, обратитесь в службу поддержки пользователей DigiCert. | 
| Поставщик DigiCert — не удалось получить политику DigiCert. <br><br>"The request was aborted: Could not create SSL/TLS secure channel." (Не удалось получить политику Symantec "Время ожидания операции истекло. Не удалось создать защищенный канал SSL/TLS."). | Эта ошибка возникает при следующих условиях. <br><br> 1. У службы Intune Certificate Connector недостаточно разрешений для чтения сертификата авторизации ресурсов и закрытого ключа из хранилища сертификатов "Личное" на локальном компьютере. Чтобы устранить эту проблему, проверьте состояние выполнения контекстной учетной записи службы соединителя в файле services.msc. Служба соединителя должна выполняться в контексте NT AUTHORITY\SYSTEM. <br><br> 2. В профиле сертификата PKCS на портале администрирования Intune может быть указано недопустимое полное доменное имя базовой службы ЦС DigiCert. Полное доменное имя имеет формат **pki-ws.symauth.com**. Чтобы устранить эту проблему, обратитесь в службу поддержки пользователей DigiCert и убедитесь, что для подписки используется правильный URL-адрес. <br><br> 3. Intune Certificate Connector не удалось выполнить проверку подлинности в ЦС DigiCert с использованием сертификата авторизации ресурсов, так как невозможно получить закрытый ключ. Чтобы устранить эту проблему, установите сертификат авторизации ресурсов вместе с закрытым ключом в хранилище сертификатов "Личное" на локальном компьютере. <br><br> Если проблема сохранится, обратитесь в службу поддержки пользователей DigiCert. |
| Поставщик DigiCert — не удалось получить политику DigiCert. <br><br>"A request element is not understood" (Элемент запроса не распознан). | Intune Certificate Connector не удалось получить шаблон профиля сертификата DigiCert, так как идентификатор объекта профиля клиента не совпадает с профилем сертификата Intune. Или другой вариант: Intune Certificate Connector не удалось найти шаблон профиля сертификата, который связан с указанным идентификатором объекта профиля клиента в ЦС DigiCert. <br><br> Чтобы устранить эту проблему, получите правильный идентификатор объекта профиля клиента из шаблона сертификата DigiCert в ЦС DigiCert. Затем обновите профиль сертификата PKCS на портале администрирования Intune. <br><br> Получите идентификатор объекта профиля клиента из ЦС DigiCert. <br> 1. Войдите на портал администрирования ЦС DigiCert. <br> 2. Выберите **Manage Certificate Profiles** (Управление профилями сертификатов). <br> 3. Выберите профиль сертификата, который вы намерены использовать. <br> 4. Получите идентификатор объекта для профиля сертификата. Он имеет следующий вид. <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Внесите в профиль сертификата PKCS правильный идентификатор объекта для профиля сертификата, выполнив следующие действия. <br>1. Войдите на портал администрирования Intune. <br> 2. Перейдите к профилю сертификата PKCS и выберите **Изменить**. <br> 3. Внесите идентификатор объекта для профиля сертификата в поле имени шаблона сертификата. <br> 4. Сохраните профиль сертификата PKCS. |
| Поставщик DigiCert — ошибка проверки политики. <br><br> Атрибут отсутствует в списке поддерживаемых DigiCert атрибутов шаблона сертификата. | ЦС DigiCert отображает такое сообщение, когда обнаруживает несоответствие между шаблоном профиля сертификата Symantec и профилем сертификата Intune. Эта проблема чаще всего связана с несоответствием атрибутов **SubjectName** или **SubjectAltName**. <br><br> Для устранения этой проблемы в шаблоне профиля сертификата DigiCert выберите поддерживаемые Intune атрибуты для **SubjectName** и **SubjectAltName**. Чтобы получить дополнительные сведения, изучите поддерживаемые Intune атрибуты в разделе **о параметрах сертификата**. |
| Некоторые пользовательские устройства не получают сертификаты PKCS из ЦС DigiCert. | Такая проблема возникает, если имя участника-пользователя содержит специальные символы, например подчеркивание (пример: `global_admin@intune.onmicrosoft.com`). <br><br> ЦС DigiCert не поддерживает специальные символы для **mail_firstname** и **mail_lastname**. <br><br> Для устранения проблемы сделайте следующее. <br><br> 1. Войдите на портал администрирования ЦС DigiCert. <br> 2. Выберите **Manage Certificate Profiles** (Управление профилями сертификатов). <br> 3. Щелкните профиль сертификата, используемый для Intune. <br> 4. Щелкните ссылку **Customize options** (Параметры настройки). <br> 5. Нажмите кнопку **Advanced options** (Дополнительные параметры). <br> 6. В списке **Certificate fields – Subject DN** (Поля сертификата для DN субъекта) добавьте поле **Common Name (CN)** (Обычное имя) и удалите имеющееся поле a **Common Name (CN)** (Обычное имя). Операции добавления и удаления должны выполняться вместе. <br> 7. Нажмите кнопку **Сохранить**. <br><br> Когда вы выполните описанные выше изменения, профиль сертификата DigiCert будет запрашивать **"CN=<upn>"** вместо **mail_firstname** и **mail_lastname**. |
| Удаленный вручную пользователь уже развернул сертификат с устройства. | Intune повторно развертывает тот же сертификат во время следующего входа в систему или принудительного применения политик. В этом случае соединитель NDES Connector не получает запрос на сертификат PKCS. |

## <a name="next-steps"></a>Дальнейшие шаги

Помимо сведений в этой статье, ознакомьтесь с информацией из статьи [Что такое профили устройств в Microsoft Intune?](../configuration/device-profiles.md), чтобы научиться управлять устройствами организации и их сертификатами.
