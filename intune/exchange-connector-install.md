---
title: "Настройка соединителя Exchange для локальной службы EAS с помощью Intune"
titleSuffix: Azure portal
description: "Использование соединителя для обеспечения обмена данными между Intune и локальным сервером Exchange Server"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39fb4b4b91eb6769eb1d5d95736cbbde141c6812
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Настройка локального соединителя Exchange для Intune в Microsoft Intune Azure

В локальных средах Exchange Server можно использовать локальный соединитель Intune Exchange, который позволяет управлять доступом устройств к почтовым ящикам локальной среды Exchange на основе сведений о наличии у устройств регистрации в Intune и их соответствии политикам соответствия Intune. Локальный соединитель Exchange также обеспечивает обнаружение мобильных устройств, которые подключаются к локальной среде Exchange Server, за счет синхронизации существующих записей Exchange Active Sync (EAS) с Intune.

> [!IMPORTANT]
> Intune поддерживает только одно подключение локального соединителя Exchange любого типа на подписку.

Чтобы настроить соединение для обмена данными между Microsoft Intune и локальной средой Exchange Server, выполните следующие действия:

1.  Скачайте локальный соединитель Intune для Exchange с портала Azure.
2.  Установите и настройте локальный соединитель Intune для Exchange.
3.  Проверьте подключение к Exchange.

## <a name="on-premises-exchange-connector-requirements"></a>Требования к локальному соединителю Exchange
В следующей таблице указаны требования к компьютеру, на котором устанавливается локальный соединитель Exchange.

|Требование|Дополнительные сведения|
|---------------|--------------------|
|Операционные системы|Intune поддерживает локальный соединитель Exchange на компьютере под управлением любого 64-разрядного выпуска Windows Server 2008 с пакетом обновления 2 (SP2), Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2.<br /><br />Соединитель не поддерживается ни в какой установке Server Core.|
|Microsoft Exchange|Локальный соединитель требует использования Microsoft Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии либо старой выделенной среды Exchange Online. Чтобы определить, используется ли в вашей выделенной среде Exchange Online **новая** или **устаревшая** конфигурация, обратитесь к своему менеджеру по работе с клиентами.|
|Центр управления мобильными устройствами| [Установите Intune в качестве центра управления мобильными устройствами](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Оборудование|Компьютер, на котором устанавливается соединитель, должен иметь ЦП с частотой 1,6 ГГц, 2 ГБ ОЗУ и 10 ГБ свободного дискового пространства.|users-add.md
|Синхронизация Active Directory|Прежде чем использовать любой соединитель для подключения Intune к Exchange Server, необходимо [настроить синхронизацию Active Directory](users-add.md), чтобы локальные пользователи и группы безопасности синхронизировались с имеющимся экземпляром Azure Active Directory.|
|Дополнительное программное обеспечение|На компьютере, на котором размещен соединитель, необходимо выполнить полную установку платформы Microsoft .NET Framework 4.5 и Windows PowerShell 2.0.|
|Network (Сеть)|Компьютер, на котором устанавливается соединитель, должен входить в домен, имеющий отношение доверия с доменом, где размещен сервер Exchange Server.<br /><br />Для компьютера необходимо настроить доступ к службе Intune через брандмауэры и прокси-серверы на портах 80 и 443. Домены, используемые Intune, включают manage.microsoft.com, &#42;manage.microsoft.com и &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Требования к командлетам Exchange

Необходимо создать учетную запись пользователя Active Directory, которую будет использовать соединитель Intune Exchange. Она должна иметь разрешение на выполнение следующих обязательных командлетов Windows PowerShell Exchange.


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics;
 -   Get-ActiveSyncDevice;
 -   Get-ExchangeServer;
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient;
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings.
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Загрузка пакета установки программного обеспечения локального соединителя Exchange

1. В поддерживаемой локальным соединителем Exchange операционной системе Windows Server войдите на [портал Azure](http://portal.azure.com), используя учетную запись с правами администратора локальной среды Exchange Server и лицензией на использование Exchange Server.

2. Выберите пункт **Другие службы** в меню слева и введите **Intune** в текстовом поле фильтра.

3. Щелкните **Intune** и на открывшейся панели мониторинга Intune выберите **Локальный доступ**.

4. В колонке **Локальный доступ — соединитель Exchange ActiveSync** в разделе **Установка** выберите **Скачайте локальный соединитель**.

5.  Локальный соединитель Exchange находится в сжатой ZIP-папке, которую можно открыть или сохранить. В диалоговом окне **Загрузка файла** выберите **Сохранить**, чтобы сохранить сжатую папку в безопасное расположение.

    > [!IMPORTANT]
    > Не переименовывайте и не перемещайте файлы в папке локального соединителя Exchange. Перемещение или переименование содержимого папки прервет его установку.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Установка и настройка локального соединителя Exchange Intune
Чтобы установить локальный соединитель Exchange, выполните следующие действия. Локальный соединитель Exchange можно установить для подписки Intune только один раз и только на один компьютер. При попытке настройки дополнительного локального соединителя Exchange исходное подключение заменяется новым.

1.  В поддерживаемой операционной системе для локального соединителя извлеките файлы из папки **Exchange_Connector_Setup.zip** в безопасное место.

2.  После извлечения файлов дважды щелкните файл **Exchange_Connector_Setup.exe**, чтобы установить локальный соединитель Exchange.

    > [!IMPORTANT]
    > Если конечная папка находится не в безопасном расположении, после установки локального соединителя следует удалить файл сертификата **WindowsIntune.accountcert**.

3.  В диалоговом окне **Соединитель Microsoft Intune Exchange** выберите либо **Локальный сервер Microsoft Exchange**, либо **Размещенный сервер Microsoft Exchange**.

  ![Выбор типа Exchange Server](./media/intune-sa-exchange-connector-config.png)

  Если выбран локальный сервер Exchange Server, укажите имя сервера или полное доменное имя сервера Exchange Server, на котором размещена роль **сервера клиентского доступа**.

  Если выбран размещенный сервер Exchange Server, укажите адрес сервера Exchange Server. Поиск URL-адреса размещенного сервера Exchange Server

    1. Откройте Outlook Web App для Office 365.

    2. Щелкните значок **?** в левом верхнем углу экрана и выберите пункт **О программе**.

    3. Найдите значение **Внешний POP-сервер** .

    4. Щелкните **Прокси-сервер**, чтобы указать параметры прокси-сервера для размещенного сервера Exchange Server.
        1. Щелкните **Использовать прокси-сервер при синхронизации данных мобильных устройств**.

        2. Введите **имя прокси-сервера** и **номер порта** , которые будут использоваться для доступа к серверу.

        3. Если для доступа к прокси-серверу требуется указать пользовательские учетные данные, выберите **Использовать учетные данные для подключения к прокси-серверу**. Затем введите данные **домена/пользователя** и **пароль**.

        4. Нажмите кнопку **ОК**.

    5. В поля **Пользователь (домен или пользователь)** и **Пароль** введите учетные данные, необходимые для подключения к серверу Exchange.

    6.  Введите административные учетные данные, необходимые для отправки уведомлений на пользовательский почтовый ящик Exchange Server. Эти уведомления можно настроить с помощью политик условного доступа в Intune.

        Убедитесь, что служба автоматического обнаружения и веб-службы Exchange настроены на сервере клиентского доступа Exchange. Дополнительные сведения см. в разделе [Сервер клиентского доступа](https://technet.microsoft.com/library/dd298114.aspx).

    7.  В поле **Пароль** укажите пароль учетной записи для доступа Intune к серверу Exchange Server.

    8. Выберите **Подключить**.

    > [!NOTE]
    > Настройка соединения может занять несколько минут.

Во время настройки соединитель Exchange сохраняет параметры прокси-сервера для обеспечения доступа к Интернету. Если параметры прокси-сервера изменятся, необходимо будет перенастроить соединитель Exchange, чтобы применить обновленные параметры прокси-сервера к соединителю Exchange.

После того как соединитель Exchange установит подключение, мобильные устройства, связанные с пользователями, которые управляются соединителем, автоматически синхронизируются и добавляются в него. Процесс синхронизации может занять некоторое время.

> [!NOTE]
> Если был установлен локальный соединитель Exchange и в определенный момент подключение к Exchange было удалено, необходимо переустановить локальный соединитель Exchange с компьютера, на котором он был установлен.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Поддержка высокой доступности локального соединителя Exchange 
Когда соединитель Exchange создает подключение к серверу Exchange, используя указанный CAS, такой соединитель может обнаруживать другие CAS. Если основной CAS становится недоступным, происходит отработка отказа соединителя на другой CAS (при его доступности), пока не станет доступным основной CAS. По умолчанию этот компонент включен. Эту функцию можно отключить с помощью следующей процедуры:
1. На сервере, где установлен соединитель Exchange, перейдите в папку %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. В текстовом редакторе откройте файл **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Чтобы отключить эту функцию, измените &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; на &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;.    


## <a name="monitor-the-exchange-connector-activity"></a>Наблюдение за активностью соединителя Exchange

После успешной настройки соединителя Exchange можно просмотреть состояние подключения и последней успешной попытки синхронизации. Проверка подключения для локального соединителя Exchange:

1. На панели мониторинга Intune выберите **Локальный доступ**.
2. В разделе **Управление** выберите **Локальный доступ к Exchange**, чтобы проверить состояние подключения.

Также можно проверить время и дату последней успешной попытки синхронизации.

### <a name="system-center-operations-manager-scom-management-pack"></a>Пакет управления System Center Operations Manager (SCOM)

Начиная с выпуска Intune 1710, вы можете использовать [пакет управления SCOM для соединителя Exchange и Intune](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Он предоставляет дополнительные способы мониторинга соединителя Exchange для устранения неполадок.

## <a name="next-steps"></a>Дальнейшие шаги
[Создание политики условного доступа для локального сервера Exchange](conditional-access-exchange-create.md)
