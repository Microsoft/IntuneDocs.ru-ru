---
title: Устранение неполадок с профилями устройств, подключенными к сети Wi-Fi, и просмотр их журналов в Microsoft Intune — Azure | Документация Майкрософт
description: Обнаружение и устранение неполадок в профилях конфигурации устройств Android, iOS и Windows, подключенных к сети Wi-Fi, в Microsoft Intune. Сведения о просмотре журналов, распространенных проблемах и их возможных решениях.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77f5787509438ec3280f29be8449d78979806042
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74542667"
---
# <a name="troubleshoot-wi-fi-device-configuration-profiles-in-microsoft-intune"></a>Устранение неполадок в профилях конфигурации устройств, подключенных к сети Wi-Fi, в Microsoft Intune

В Intune вы можете создавать профили конфигурации устройств, которые содержат параметры подключения к сети Wi-Fi. Эти параметры позволяют подключить пользовательские устройства Android, iOS и Windows к сети организации.

В этой статье описан успешно примененный к устройствам профиль Wi-Fi. Здесь также содержатся сведения о журнале, описание распространенных проблем и другая информация. Приведенные здесь сведения помогут вам устранить неполадки в профилях Wi-Fi.

Дополнительные сведения о профилях Wi-Fi см. в статье [Добавление и использование параметров Wi-Fi для устройств в Microsoft Intune](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Подготовка к работе

В примерах этой статьи используется проверка подлинности профилей Intune с помощью сертификатов SCEP. Кроме того, здесь предполагается, что профили доверенного корневого сертификата и SCEP работают надлежащим образом на устройстве.

## <a name="android"></a>Android

В этом разделе описана процедура установки профилей конфигурации на устройстве Android для пользователя.

### <a name="end-user-experience-example"></a>Пример процедуры установки для пользователя

В этом сценарии используется устройство Nokia 6.1. Перед установкой профиля Wi-Fi на устройстве установите профили доверенного корневого сертификата и SCEP.

1. Пользователи получают уведомление для установки профиля доверенного корневого сертификата:

    > [!div class="mx-imgBorder"]
    > ![Пример уведомления приложения Корпоративного портала на устройстве Android для установки профиля доверенного корневого сертификата](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-trusted-root.png)

2. В следующем уведомлении содержится запрос на установку профиля сертификата SCEP:

    > [!div class="mx-imgBorder"]
    > ![Пример уведомления приложения Корпоративного портала на устройстве Android для установки профиля сертификата SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-scep-certificate.png)

    > [!TIP]
    > При использовании устройства Android, управляемого администратором, может быть указано несколько сертификатов. При отмене или удалении профиля сертификата сам сертификат остается на устройстве. В этом случае выберите самый новый сертификат. Обычно им будет последний сертификат в списке.
    >
    > Подобная ситуация не возникает на устройствах Android для бизнеса и Samsung Knox. Дополнительные сведения см. в статье [Управление устройствами с рабочим профилем Android в Intune](../enrollment/android-enterprise-overview.md) и разделе [Устройства Android KNOX](../protect/remove-certificates.md#android-knox-devices).

3. Затем пользователи получают уведомление для установки профиля Wi-Fi:

    > [!div class="mx-imgBorder"]
    > ![Пример уведомления приложения Корпоративного портала на устройстве Android для установки профиля сертификата SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-install-wifi-profile.png)

4. После завершения подключение Wi-Fi отобразится как сохраненная сеть:

    > [!div class="mx-imgBorder"]
    > ![Подключение Wi-Fi, отображаемое как сохраненная сеть](./media/troubleshoot-wi-fi-profiles/android-end-user-saved-networks.png)

### <a name="review-company-portal-app-logs"></a>Просмотр журналов приложения Корпоративного портала

В Android файл **Omadmlog.log** содержит подробное описание действий профиля Wi-Fi, установленного на устройстве. У вас может быть до пяти файлов журнала Omadmlog. Обязательно получите метку времени последней синхронизации. Используя ее, вы сможете найти соответствующие записи в журнале.

В следующем примере [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace) используется, чтобы прочитать журналы и выполнить поиск по запросу wifimgr:

> [!div class="mx-imgBorder"]
> ![Подключение Wi-Fi, отображаемое как сохраненная сеть](./media/troubleshoot-wi-fi-profiles/android-cmtrace-filter-wifimgr.png)

В приведенном ниже журнале отображаются результаты поиска и успешно примененный профиль Wi-Fi:

```log
2019-08-01T19:22:46.7340000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.7490000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:46.8100000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:46.8209999    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.8240000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected ca certificate with alias: 'user:205xxxxx.0' and thumbprint '<thumbprint>'.
2019-08-01T19:22:47.0990000    VERB    com.microsoft.omadm.platforms.android.certmgr.CertificateChainBuilder    15118    04142    Complete certificate chain built with Complete certs.
2019-08-01T19:22:47.1010000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    1 cert(s) matched criteria: User<ID>[i:<ID>,17CECEA1D337FAA7D167AD83A8CC7A8FCBF9xxxx;eku:1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2]
2019-08-01T19:22:47.1090000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    0 cert(s) excluded by criteria:
2019-08-01T19:22:47.1110000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected client cert with alias 'User<ID>' and requestId 'ModelName=<ModelName>%2FLogicalName_<LogicalName>;Hash=-912418295'.
2019-08-01T19:22:47.4120000    VERB    com.microsoft.omadm.Services    15118    04142    Successfully applied, enabled and saved wifi profile '<profile ID>'
2019-08-01T19:22:47.4240000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.4910000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.4970000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5080000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.5820000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.5900000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5910000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04142    Applied profile <profile ID>

```

## <a name="ios"></a>iOS

После установки на устройстве профиль Wi-Fi будет отображаться в разделе **Management Profile** (Профиль управления):

> [!div class="mx-imgBorder"]
> ![Профиль управления на устройстве iOS](./media/troubleshoot-wi-fi-profiles/ios-management-profile.png)

> [!div class="mx-imgBorder"]
> ![Подключение Wi-Fi, отображаемое как сеть Wi-Fi на устройстве iOS](./media/troubleshoot-wi-fi-profiles/ios-wifi-connection-in-management-profile.png)

### <a name="review-the-ios-console-and-device-logs"></a>Просмотр журналов консоли и устройств iOS

На устройствах iOS журнал приложения Корпоративного портала не содержит сведений о профилях Wi-Fi. Подробные сведения об установке профилей Wi-Fi можно просмотреть в журналах консоли или устройства:

1. Подключите устройство iOS к Mac. Выберите **Applications** (Приложения) > **Utilities** (Служебные программы) и откройте консольное приложение
2. В разделе **Action** (Действие) выберите **Include Info Messages** (Включить информационные сообщения) и **Include Debug Messages** (Включить сообщения об отладке):

    > [!div class="mx-imgBorder"]
    > ![Параметры включения информационных сообщений и сообщений об отладке в консольном приложении iOS](./media/troubleshoot-wi-fi-profiles/ios-console-app-include-info-messages-debug-messages.png)

3. Воспроизведите сценарий и сохраните журналы в текстовом файле:

    1. Выберите все сообщения на текущем экране: **Edit** (Изменить) > **Select All** (Выбрать все).
    2. Скопируйте сообщения: **Edit** (Изменить) > **Copy** (Копировать).
    3. Вставьте данные журнала в текстовый редактор и сохраните файл.

4. Найдите сохраненный файл журнала, чтобы просмотреть подробные сведения. После успешной установки профиля выходные данные будут выглядеть, как приведенный ниже журнал:

    ```log
    Line 390870: debug    11:19:58.994815 -0400    profiled    Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM in domain ManagingProfileToManagedProfile to system\
    Line 390872: debug    11:19:58.995210 -0400    profiled    Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.wifi.Contoso in domain ManagedProfileToManagingProfile to system\
    Line 392346: default    11:19:59.360460 -0400    profiled    Profile \'93www.windowsintune.com.wifi.Contoso\'94 installed.\
    ```

## <a name="windows"></a>Windows

После установки профиля Wi-Fi на устройстве откройте **Параметры** > **Учетные записи** > **Доступ к рабочей или учебной учетной записи**. Выберите свою учетную запись, а затем нажмите кнопку **Информация**.

> [!div class="mx-imgBorder"]
> ![Выбор параметра доступа к рабочей или учебной учетной записи и нажатие кнопки информации на устройстве Windows](./media/troubleshoot-wi-fi-profiles/windows-access-work-school-info.png)

В разделе **Areas managed by Microsoft** (Области, управляемые корпорацией Майкрософт) отображается **Wi-Fi**, как показано ниже:

> [!div class="mx-imgBorder"]
> ![Отображение Wi-Fi для Windows в разделе областей, управляемых корпорацией Майкрософт](./media/troubleshoot-wi-fi-profiles/windows-wifi-areas-managed-by-microsoft.png)

Чтобы увидеть подключение Wi-Fi, выберите **Параметры** > **Network & Internet** (Сеть и Интернет)  > **Wi-Fi**:

> [!div class="mx-imgBorder"]
> ![Подключение Wi-Fi, отображаемое как известная сеть в параметрах в Windows](./media/troubleshoot-wi-fi-profiles/windows-wifi-connection-known-networks.png)

### <a name="review-event-viewer-logs"></a>Просмотр журналов в средстве "Просмотр событий"

На устройствах Windows сведения о профилях Wi-Fi регистрируются в средстве "Просмотр событий":

1. Откройте приложение **Просмотр событий**.
2. В меню **Представление** выберите **Отобразить аналитический и отладочный журналы**.
3. Разверните **Журналы приложений и служб** > **Майкрософт** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Администратор**.

Выходные данные будут аналогичны приведенным ниже журналам:

```log
Log Name:      Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
Source:        Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider
Date:          8/7/2019 8:01:41 PM
Event ID:      1506
Task Category: (1)
Level:         Information
Keywords:      (2)
User:          SYSTEM
Computer:      <Computer Name>
Description:
WiFiConfigurationServiceProvider: Node set value, type: (0x4), Result: (The operation completed successfully.).
```

## <a name="common-issues"></a>Распространенные проблемы

### <a name="issue-1-the-wi-fi-profile-isnt-deployed-to-the-device"></a>Проблема 1. Профиль Wi-Fi не развернут на устройстве

- Убедитесь, что профиль Wi-Fi назначен правильной группе:

    1. В [Центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) выберите **Устройства** > **Профили конфигурации**.
    2. Выберите свой профиль, а затем — **Назначения**. Убедитесь, что выбранные группы указаны правильно.
    3. В диспетчере конечных точек выберите **Устранение неполадок и поддержка**. Просмотрите сведения в разделе **Назначения**.

- В диспетчере конечных точек выберите **Устранение неполадок и поддержка**. Убедитесь, что устройство может синхронизироваться с Intune, проверив время **последней синхронизации**.

- Если профиль Wi-Fi связан с профилями доверенного корневого сертификата и SCEP, разверните оба профиля на устройстве. Профиль Wi-Fi зависит от этих профилей.

- На устройствах с Windows 10 и новее просмотрите журнал диагностических сведений MDM:

  1. Откройте **Учетные записи** > **Учетные записи** > **Доступ к рабочей или учебной учетной записи**.
  2. Выберите свою рабочую или учебную учетную запись, а затем нажмите кнопку **Информация**.
  3. В нижней части страницы **Параметры** выберите **Создать отчет**.
  4. Откроется окно с путем к файлам журнала. Выберите **Экспорт**.
  5. Перейдите по пути `\Users\Public\Documents\MDMDiagnostics` и просмотрите отчет:

      > [!div class="mx-imgBorder"]
      > ![Пример диагностических сведений MDM, отображающий конфигурацию профиля WiFi на устройствах с Windows 10](./media/troubleshoot-wi-fi-profiles/windows-mdm-diagnostic-info.png)

  > [!TIP]
  > Дополнительные сведения см. в статье [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (Диагностика ошибок MDM в Windows 10).

- На устройствах Android без установленных профилей доверенного корневого сертификата и SCEP в файле Omadmlog приложения Корпоративного портала отобразится следующая запись:

  ``` log
  2019-08-01T19:18:13.5120000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04105    Skipping Wifi profile <profile ID> because it is pending certificates.
  ```

  - Если на устройстве Android имеются совместимые профили доверенного корневого сертификата и SCEP, профиль Wi-Fi может отсутствовать. Эта проблема возникает, когда поставщик **CertificateSelector** из приложения Корпоративного портала не находит сертификат, соответствующий указанным критериям. Эти критерии могут быть указаны в шаблоне сертификата или в профиле SCEP.

    Если соответствующий сертификат не найден, это свидетельствует о том, что сертификаты на устройстве не установлены. Профиль Wi-Fi не применяется по причине отсутствия правильного сертификата. В этом случае в файле Omadmlog приложения Корпоративного портала отобразится следующая запись:

    ` Skipping Wifi profile <profile ID> because it is pending certificates.`

    В следующем примере журнала показаны сертификаты, исключаемые из-за того, что для расширенного использования ключа (EKU) задан критерий **Любая цель**. Но сертификаты, назначенные устройству, не содержат параметр EKU:

    ```log
    2018-11-27T21:10:37.6390000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID1> and requestId <requestID1> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID2> and requestId <requestID2> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    0 cert(s) matched criteria:
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    2 cert(s) excluded by criteria:
    2018-11-27T21:10:37.6400000    INFO       com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager       14210                00948     Skipping Wifi profile <profile ID> because it is pending certificates.
    ```

    В следующем примере показано введение EKU **любой цели** для профиля SCEP. Но он не введен в шаблон сертификата в Центре сертификации. Чтобы устранить эту проблему, добавьте параметр **Любая цель** в шаблон сертификата. Как вариант, можно также удалить параметр **Любая цель** из профиля SCEP.

    > [!div class="mx-imgBorder"]
    > ![Добавление параметра "Любая цель" в шаблон сертификата в Центре сертификации на устройстве Android](./media/troubleshoot-wi-fi-profiles/android-add-any-purpose-eku.png)

    > [!div class="mx-imgBorder"]
    > ![Добавление параметра "Любая цель" в профиль конфигурации сертификата SCEP в Intune](./media/troubleshoot-wi-fi-profiles/android-any-purpose-scep-device-config-profile.png)

  - Убедитесь, что на устройстве Android в полной цепочке сертификатов находятся все необходимые сертификаты. В противном случае профиль Wi-Fi нельзя будет установить на устройстве. Дополнительные сведения см. в разделе [Missing intermediate certificate authority](https://developer.android.com/training/articles/security-ssl#MissingCa) (Отсутствие промежуточного Центра сертификации) (откроется веб-сайт Android).
  - Отфильтруйте содержимое файла Omadmlog по ключевым словам, чтобы найти сведения, например, какой сертификат используется в профиле Wi-Fi и успешно ли применен профиль.

    Например, используйте [CMTrace](https://docs.microsoft.com/sccm/core/support/cmtrace) для чтения журналов. В строке поиска выполните фильтрацию по запросу wifimgr:

    > [!div class="mx-imgBorder"]
    > ![Указание в CMTrace фильтра для поиска профилей конфигурации WiFiMgr на устройствах Android](./media/troubleshoot-wi-fi-profiles/cmtrace-filter-wifimgr.png)

    Выходные данные выглядят, как в следующем журнале:

    > [!div class="mx-imgBorder"]
    > ![Пример выходных данных журнала CMTrace, отображающих успешное применение профиля конфигурации Wi-Fi Intune на устройствах](./media/troubleshoot-wi-fi-profiles/cmtrace-sample-log-output.png)

    Если в журнале отображается ошибка, скопируйте метку времени ошибки и отмените фильтрацию журнала. Затем используйте параметр "Найти" с меткой времени, чтобы просмотреть сведения о действиях, предшествовавших ошибке.

### <a name="issue-2-the-wi-fi-profile-is-deployed-to-the-device-but-the-device-cant-connect-to-the-network"></a>Проблема 2. Профиль Wi-Fi развернут на устройстве, но устройство не может подключиться к сети

Как правило, эта проблема вызвана чем-то за пределами Intune. Приведенные ниже задачи могут помочь в обнаружении и устранении проблем с подключением:

- Вручную подключитесь к сети с помощью сертификата с теми же критериями, что и в профиле Wi-Fi.

  Если вам удалось установить подключение, посмотрите свойства сертификата в этом подключении. Затем обновите профиль Wi-Fi Intune, указав те же свойства сертификата.
- Ошибки подключения обычно регистрируются в журнале сервера Radius. Например, в нем должны отображаться сведения о попытке устройства подключиться с помощью профиля Wi-Fi.

## <a name="need-more-help"></a>Требуется дополнительная помощь?

- Перейдите на [форум пользователей Intune](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc) или [получите поддержку от корпорации Майкрософт](../fundamentals/get-support.md).

- Дополнительные сведения о профилях Wi-Fi в Microsoft Intune см. в статьях о:

  - добавлении параметров Wi-Fi для устройств под управлением [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md) и [Windows 10 и более поздних версий](wi-fi-settings-windows.md);
  - [настройке NDES для развертываний сертификатов SCEP в Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-How-to-configure-NDES-for-SCEP-certificate/ba-p/455125);
  - устранении неполадок [развертывания профиля сертификата SCEP](https://support.microsoft.com/help/4526725/troubleshooting-scep-profile-deployment-to-android-devices-in-intune) и [конфигурации NDES](https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune).

- Последние новости, сведения и технические советы можно найти в официальных блогах:
  - [Блог группы поддержки Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
  - [Блог разработчиков Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/bg-p/enterprisemobilityandsecurity)

## <a name="next-steps"></a>Дальнейшие шаги

[Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md)
