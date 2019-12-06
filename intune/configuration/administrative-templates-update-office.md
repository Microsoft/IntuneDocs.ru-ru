---
title: Обновление Office 365 с помощью административных шаблонов в Microsoft Intune в Azure | Документация Майкрософт
description: Обновляйте приложения Office 365 до последней версии, используя административные шаблоны в Microsoft Intune, и выбирайте в этих шаблонах частоту проверки обновлений Office. Просматривайте разделы реестра устройств, которые обновляются при применении политики Intune для обновления Office.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf872387d6e6f4f91af9f074f54695b081b79119
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74549113"
---
# <a name="use-update-channel-and-target-version-settings-to-update-office-365-with-microsoft-intune-administrative-templates"></a>Использование параметров канала обновления и целевой версии для обновления Office 365 с помощью административных шаблонов Microsoft Intune

В Intune можно использовать [шаблоны Windows 10 для настройки параметров групповой политики](administrative-templates-windows.md). В этой статье показано, как обновить Office 365 с помощью административного шаблона в Intune. Кроме того, здесь содержатся рекомендации по проверке успешного применения политик. Эти сведения также помогут при устранении неполадок.

В этом сценарии вы создадите в Intune административный шаблон, который обновляет Office 365 на ваших устройствах.

Дополнительные сведения об административных шаблонах см. в статье о [шаблонах Windows 10 для настройки параметров групповой политики](administrative-templates-windows.md).

Область применения:

- Windows 10 и более поздней версии
- Office 365

## <a name="prerequisites"></a>Предварительные условия

Не забудьте [включить автоматические обновления Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/configure-update-settings-for-office-365-proplus) для приложений Office. Это можно сделать с помощью групповой политики или шаблона Intune Office 2016 ADMX:

![Настройка параметра "Включить автоматическое обновление" для Office в административном шаблоне Intune](./media/administrative-templates-update-office/admx-enable-automatic-updates.png)

## <a name="set-the-update-channel-in-the-intune-administrative-template"></a>Настройка канала обновления в административном шаблоне Intune

1. В [административном шаблоне Intune](administrative-templates-windows.md#create-a-template) перейдите к параметру **Канал обновления** и введите нужный канал. Например, выберите `Semi-Annual Channel`:

    ![Настройка параметра "Канал обновления" для Office в административном шаблоне Intune](./media/administrative-templates-update-office/admx-enable-update-channel-setting.png)

    > [!NOTE]
    > Рекомендуется выполнять обновление чаще. Канал обновления раз в полгода используется только в качестве примера.

2. Не забудьте [назначить политику](device-profile-assign.md) для устройств с Windows 10. Чтобы протестировать политику раньше, вы также можете синхронизировать ее следующим образом:

    - [синхронизация политики в Intune](../remote-actions/device-sync.md);
    - [синхронизация политики на устройстве вручную](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows#sync-from-settings-app).

## <a name="check-the-intune-registry-keys"></a>Проверка разделов реестра Intune

После назначения политики и синхронизации устройства можно проверить применение политики:

1. Откройте приложение **Редактор реестра** на устройстве.
2. Перейдите по пути политики Intune: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

    > [!TIP]
    > `<Provider ID>` в разделе реестра изменится. Чтобы найти идентификатор поставщика для устройства, откройте приложение **Редактор реестра** и перейдите в расположение `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\AdmxInstalled`. Отобразится идентификатор поставщика.

    После применения политики вы увидите следующие разделы реестра:

    - `L_UpdateBranch`
    - `L_UpdateTargetVersion`

    В следующем примере видно, что `L_UpdateBranch` имеет значение `<enabled /><data id="L_UpdateBranchID" value="Deferred" />`. Это значение означает, что для него задан канал Semi-Annual Channel:

    ![Пример раздела реестра L_Updatebranch административного шаблона](./media/administrative-templates-update-office/admx-update-branch-registry-key.png)

    > [!TIP]
    > В статье [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager) (Управление Office 365 профессиональный плюс с помощью Configuration Manager) содержится список значений и их описание. Значения реестра основаны на выбранном канале распространения:
    >
    >- Monthly Channel: значение — Current.
    >- Monthly Channel (Targeted): значение — Current.
    >- Semi-Annual Channel: значение — Current.
    >- Semi-Annual Channel (Targeted): значение — FirstReleaseDeferred.
    >- Insider Fast: значение — InsiderFast.

На этом этапе политика Intune успешно применена к устройству.

## <a name="check-the-office-registry-keys"></a>Проверка разделов реестра Office

1. Откройте приложение **Редактор реестра** на устройстве.
2. Перейдите по пути политики Office: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`.

    Вы увидите следующие разделы реестра:

    - `UpdateChannel`: динамический ключ, который изменяется в зависимости от настроенных параметров.
    - `CDNBaseUrl`: задается при установке Office 365 на устройстве.

3. Проверьте значение `UpdateChannel`. Значение указывает, как часто обновляется Office. В статье [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager) (Управление Office 365 профессиональный плюс с помощью Configuration Manager) содержится список значений и их описание.

    В следующем примере показано, что `UpdateChannel` имеет значение `http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60` (**ежемесячно**):

    ![Пример раздела реестра Office UpdateChannel административного шаблона](./media/administrative-templates-update-office/admx-update-channel-office-registry-key.png)

    Этот пример означает, что политика еще не применена, так как по-прежнему установлено значение **ежемесячно**, а не **на полгода**.

Этот раздел реестра обновляется, когда задача **Планировщик задач** > **Office Automatic Updates 2.0** (Автоматическое обновление Office 2.0) выполняется или когда пользователь входит в устройство. Для подтверждения откройте задачу **Office Automatic Updates 2.0** (Автоматическое обновление Office 2.0) > **Триггеры**. В зависимости от триггеров обновление раздела реестра `UpdateChannel` может занять по крайней мере один день.

## <a name="force-office-automatic-updates-to-run"></a>Принудительное выполнение автоматического обновления Office

Чтобы проверить политику, можно принудительно применить параметры политики на устройстве. Ниже описана процедура обновления реестра. Как всегда, будьте внимательны при обновлении реестра.

1. Очистите раздел реестра:

    1. Перейдите в расположение `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Updates`.
    2. Дважды щелкните раздел `UpdateDetectionLastRunTime`, удалите данные значения и нажмите кнопку **ОК**.

2. Выполните задачу автоматического обновления Office:

    1. Откройте приложение **Планировщик задач** на устройстве.
    2. Разверните узел **Библиотека планировщика задач** > **Microsoft** > **Office**.
    3. Выберите **Office Automatic Updates 2.0** (Автоматическое обновление Office 2.0) > **Запустить**:

        ![Открытие планировщика задач и запуск задачи автоматического обновления Office](./media/administrative-templates-update-office/admx-task-scheduler-office-automatic-updates.png)

        Дождитесь завершения задачи. Это может занять несколько минут.

3. В приложении **Редактор реестра** перейдите в расположение `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`. Проверьте значение `UpdateChannel`.

    Его необходимо заменить на значение, заданное в политике. В нашем примере должно быть установлено значение `http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114`.

На этом этапе канал обновления Office успешно изменен на устройстве. Вы можете открыть приложение Office 365 для пользователя, который получает это обновление, чтобы проверить состояние обновления.

## <a name="force-the-office-synchronization-to-update-account-information"></a>Принудительная синхронизация Office для обновления информации об учетной записи  

Вы также можете принудительно установить обновление последней версии для Office. Следующие шаги следует выполнять, только если требуется получить подтверждение или если на устройствах нужно быстро установить обновление последней версии из этого канала. В противном случае дожидайтесь, пока Office выполнит задание автоматического обновления.

### <a name="step-1-force-the-office-version-to-update"></a>Шаг 1. Принудительное обновление версии Office

1. Убедитесь, что версия Office поддерживает выбранный вами канал обновления. В статье [Журнал обновлений для Office 365 профессиональный плюс (перечислены по дате)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date) перечислены номера сборок, которые поддерживают различные каналы обновления.

2. В [административном шаблоне Intune](administrative-templates-windows.md#create-a-template) перейдите к параметру **Целевая версия** и введите нужную версию.

    Параметр **Целевая версия** выглядит следующим образом:

    ![Настройка параметра "Целевая версия" для Office в административном шаблоне Intune](./media/administrative-templates-update-office/admx-enable-target-version-setting.png)

> [!IMPORTANT]
>
> - Обязательно назначьте политику.
> - Изменения существующей политики влияют на всех назначенных пользователей.
> - При тестировании этой функции рекомендуется создать политику тестирования и назначить ее тестовой группе пользователей.

### <a name="step-2-check-the-office-version"></a>Шаг 2. Проверка версии Office

Рекомендуется использовать эти шаги для проверки политики перед ее развертыванием для всех пользователей.

1. В приложении **Редактор реестра** перейдите в расположение `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

2. Проверьте значение `L_UpdateTargetVersion`. Как только политика будет применена, значение будет соответствовать введенной вами версии, например `<enabled /><data id="L_UpdateTargetVersionID" value="16.0.10730.20344" />`.

    На этом этапе политика Intune успешно применена к устройству.

3. Затем можно принудительно обновить Office. Откройте приложение Office, например Excel. Выберите "Обновить сейчас" (возможно, в меню **Учетная запись**).

    Обновление займет несколько минут. Чтобы убедиться, что Office пытается получить введенную вами версию:

      1. На устройстве перейдите в расположение `C:\Program Files (x86)\Microsoft Office\Updates\Detection\Version`.
      2. Откройте файл `VersionDescriptor.xml` и перейдите к разделу `<Version>`. Доступная версия должна совпадать с версией, введенной в политике Intune, например:

          ![Проверка раздела версии в XML-файле дескриптора версий Office](./media/administrative-templates-update-office/office-version-descriptor-xml-example.png)

4. После установки обновления приложение Office должно отобразить новую версию (например, в меню **Учетная запись**).

## <a name="next-steps"></a>Дальнейшие шаги

[Раздел об обновлении значений каналов для клиентов Office 365](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#change-the-update-channel-after-you-enable-office-365-clients-to-receive-updates-from-configuration-manager)

[Общие сведения о службе облачной политики Office для Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service)

[Использование шаблонов Windows 10 для настройки параметров групповой политики в Microsoft Intune](administrative-templates-windows.md)
