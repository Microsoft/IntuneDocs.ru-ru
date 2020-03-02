---
title: Устранение неполадок при использовании профилей сертификатов SCEP для подготовки сертификатов с помощью Microsoft Intune | Документация Майкрософт
description: Устранение неполадок при использовании SCEP устройствами, чтобы запрашивать сертификаты для использования с Intune, включая обмен данными между устройствами и NDES, NDES и центрами сертификации, а также между Intune Certificate Connector и службой Intune.
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
ms.openlocfilehash: 4496a5bbc6d5ee5134dc4e6a795494710ea6865d
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515226"
---
# <a name="overview-for-troubleshooting-scep-certificate-profiles-with-microsoft-intune"></a>Общие сведения об устранении неполадок профилей сертификатов SCEP с помощью Microsoft Intune

Использование профилей сертификатов SCEP может быть проблематичным для устранения неполадок в Intune. Информация, приведенная в этой статье, позволит выполнить указанные ниже действия:

- получить сведения об архитектуре и потоке обмена данными процесса SCEP;
- ограничить место существования проблемы в потоке обмена данными;
- определить файлы журнала ключей, указанные в последующих статьях, посвященных устранению неполадок профилей сертификатов.

Сведения в этой статье и связанных статьях по устранению неполадок сертификатов SCEP относятся к использованию профилей сертификатов SCEP с устройствами Android, iOS, iPad и Windows. Аналогичные сведения для macOS недоступны в данный момент.

Сведения об устранении неполадок службы регистрации сертификатов для сетевых устройств (NDES) см. в следующих статьях по адресу support.microsoft.com:

- [Verify NDES configuration on-premises for SCEP certificates in Intune](https://support.microsoft.com/help/4490130/ndes-configuration-on-premises-for-scep-certificates-in-intune) (Проверка локальной конфигурации NDES для сертификатов SCEP в Intune).
- [Устранение неполадок конфигурации NDES для использования с профилями сертификатов Microsoft Intune.]( https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune)

Прежде чем продолжать, убедитесь, что вы выполнили [предварительные требования для использования профилей сертификатов SCEP](certificates-scep-configure.md#prerequisites-for-using-scep-for-certificates), включая развертывание корневого сертификата с помощью профиля доверенного сертификата.

## <a name="scep-communication-flow-overview"></a>Общие сведения о потоке обмена данными SCEP

На следующем рисунке показан обзор процесса подключения SCEP в Intune.

![Поток профиля сертификата SCEP](../protect/media/troubleshoot-scep-certificate-profiles/scep-certificate-profile-flow.png)

1. [Развертывание профиля сертификата SCEP](troubleshoot-scep-certificate-profile-deployment.md). Intune создает строку запроса, для которой требуется конкретный пользователь, тип сертификата и конкретное назначение сертификата.

2. [Обмен данными между устройством и сервером NDES](troubleshoot-scep-certificate-device-to-ndes.md). Устройство использует универсальный код ресурса (URI) для NDES из профиля для связи с сервером NDES, чтобы он мог предоставить запрос защиты.

3. [Обмен данными между NDES и модулем политики](troubleshoot-scep-certificate-ndes-policy-module.md). NDES пересылает запрос модулю политики Intune Certificate Connector на сервере, который проверяет запрос.

4. [Обмен данными между NDES и центром сертификации](troubleshoot-scep-certificate-ndes-policy-module.md). NDES передает допустимые запросы на выдачу сертификата в центр сертификации (ЦС).

5. [Доставка сертификата на устройство](troubleshoot-scep-certificate-delivery.md). Сертификат доставляется на устройство.

6. [Создание отчетов о развертывании в Intune](troubleshoot-scep-certificate-reporting.md). Соединитель сертификатов Intune сообщает о событии выдачи сертификата в Intune.

## <a name="log-files"></a>Файлы журнала

Чтобы выявить проблемы для рабочего процесса связи и подготовки сертификатов, проверьте файлы журнала инфраструктуры сервера и устройств. В последующих разделах для устранения неполадок в профилях сертификатов SCEP содержатся ссылки на файлы журналов, упоминаемые в этом разделе.

- [Журналы инфраструктуры и сервера](#logs-for-on-premises-infrastructure)

Журналы устройств зависят от платформы устройства:  

- [iOS и iPadOS](#logs-for-ios-and-ipados-devices);
- [Android](#logs-for-android-devices)
- [Windows](#logs-for-windows-devices)

### <a name="logs-for-on-premises-infrastructure"></a>Журналы для локальной инфраструктуры
  
Локальная инфраструктура, поддерживающая использование профилей сертификатов SCEP для развертывания сертификатов, включает Microsoft Intune Certificate Connector, NDES, запущенный на сервере Windows, и центр сертификации.

Файлы журналов для этих ролей включают средство просмотра событий Windows, консоли сертификатов и различные файлы журналов, относящиеся к Intune Certificate Connector, NDES или другой роли и операциям, которые являются частью локальной инфраструктуры.

В следующем списке содержатся журналы или консоли, на которые ссылаются в последующих статьях по устранению неполадок SCEP. 

- **NDESConnector_date_time.svclog**:

  В этом журнале показано взаимодействие между Microsoft Intune Certificate Connector и облачной службой Intune. Для просмотра этого файла журнала можно использовать [средство просмотра трассировки службы](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

  Связанный раздел реестра: *HKLM\SW\Microsoft\MicrosoftIntune\NDESConnector\ConnectionStatus*

  Расположение: на сервере с NDES по адресу *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **CertificateRegistrationPoint_date_time.svclog**:

  В этом журнале отображается модуль политики NDES, получающий и проверяющий запросы сертификатов. Для просмотра этого файла журнала можно использовать [средство просмотра трассировки службы](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

  Расположение: на сервере с NDES по адресу *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **NDESPlugin.log**:

  В этом журнале показана передача запросов на сертификаты в точку регистрации сертификатов и результирующая проверка этих запросов.

  Расположение: на сервере с NDES по адресу *%program_files%\Microsoft Intune\NDESPolicyModule\logs*

- **Журналы IIS**:

  В журналах IIS показаны запросы на сертификаты с мобильных устройств, входящих в NDES.

  Расположение: на сервере с NDES по адресу *c:\inetpub\logs\LogFiles\W3SVC1*

- **Журнал приложений Windows**:

  Этот журнал полезен при исследовании проблем IIS, например пула приложений SCEP.

  Расположение: на сервере с NDES. Запустите **eventvwr.msc**, чтобы открыть средство просмотра событий Windows.




### <a name="logs-for-android-devices"></a>Журналы для устройств Android

Для устройств под управлением Android используйте файл журнала приложений **корпоративного портала Android**, **OMADM.log**. Прежде чем приступать к сбору и анализу журналов, включите параметр [Подробное ведение журналов](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android), а затем воспроизведите проблему.

Сведения о сборе данных журнала OMADM.logs с устройства см. в статье [Upload and email logs using a USB cable](/intune-user-help/send-logs-to-your-it-admin-using-cable-android) (Передача журналов и их отправка электронной почтой с помощью USB-кабеля).

Дополнительные сведения о передаче журналов и их отправке электронной почтой см. в [этом разделе](/intune-user-help/send-logs-to-your-it-admin-by-email-android#upload-and-email-logs-from-microsoft-intune-app).

### <a name="logs-for-ios-and-ipados-devices"></a>Журналы для устройств iOS и iPadOS

Для устройств под управлением iOS/iPadOS используются журналы отладки и **Xcode**, который работает на компьютере Mac:

1. Подключите устройство iOS/iPadOS к Mac, а затем перейдите в раздел **Приложения** > **Служебные программы**, чтобы открыть консольное приложение. 

2. В разделе **Action** (Действие) выберите **Include Info Messages** (Включить информационные сообщения) и **Include Debug Messages** (Включить сообщения об отладке):

   ![Выбор параметров журнала](../protect/media/troubleshoot-scep-certificate-profiles/message-options.png)

3. Воспроизведите проблему, а затем сохраните журналы в текстовом файле:
   1. Выберите **Изменить** > **Выбрать все**, чтобы выбрать все сообщения на текущем экране, а затем выберите **Изменить** > **Копировать**, чтобы скопировать сообщения в буфер обмена. 
   2. Откройте приложение TextEdit, вставьте скопированные журналы в новый текстовый файл, а затем сохраните файл.


Журнал корпоративного портала для устройств iOS и iPadOS не содержит сведений о профилях сертификатов SCEP.

### <a name="logs-for-windows-devices"></a>Журналы для устройств Windows

Для устройств под управлением Windows используйте журналы событий Windows, чтобы определить проблемы регистрации или управления устройствами в Intune.

На устройстве откройте **Просмотр событий** > **Журналы приложений и служб** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider**:

![Журналы событий Windows](../protect/media/troubleshoot-scep-certificate-profiles/windows-event-log.png)

## <a name="next-steps"></a>Дальнейшие шаги

Ознакомьтесь со статьей о [развертывании профилей сертификатов SCEP](troubleshoot-scep-certificate-profile-deployment.md). 
