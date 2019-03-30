---
title: Используйте StageNow журналов на устройствах Android Zebra в Microsoft Intune — Azure | Документация Майкрософт
description: При использовании StageNow на устройствах Android с помощью Microsoft Intune см. распространенные проблемы и способы их устранения. Также узнайте, как получить журналы и примеры того, как для чтения журналов для успеха или ошибки.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490547"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Устранение неполадок и см. в разделе потенциальные проблемы на устройствах Android Zebra в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

В Microsoft Intune, можно использовать [расширения Mobility Zebra (MX) для управления устройствами Android Zebra](android-zebra-mx-overview.md). При использовании Zebra устройств, необходимо создание профилей в StageNow для управления параметрами и отправьте их в Intune. Intune использует StageNow приложения для применения параметров на устройствах. Приложение StageNow также создает подробный файл журнала на устройстве, которое используется для устранения неполадок.

Данная функция применяется к:

- Android

К примеру можно создать профиль в StageNow Настройка устройства. При создании профиля StageNow последний шаг создает файл для тестирования профиля. Этот файл с помощью StageNow приложения на устройстве, будет использовано.

Еще один пример: Создание профиля в StageNow и протестировать его. В Intune добавить профиль StageNow и назначьте его Zebra устройств. При проверке состояния назначенного профиля, профиля показано общее состояние.

Дополнительные сведения можно получить из файла журнала StageNow, который сохраняется на устройстве, каждый раз, применяется профиль StageNow в обоих случаях.

Некоторые проблемы, не относятся к содержимому StageNow профиля, а не отражено в журналах.

В этой статье показано, как читать журналы StageNow, а также список других возможных проблем с Zebra устройств, которые могут не отражаться в журналах.

[Использование устройств и управления ими Zebra с расширениями Mobility Zebra](android-zebra-mx-overview.md) содержит дополнительные сведения об этой функции.

## <a name="get-the-logs"></a>Получить журналы

### <a name="use-the-stagenow-app-on-the-device"></a>Использование StageNow приложения на устройстве
При проверке профиля непосредственно с помощью StageNow на компьютере, а не с помощью [Intune, чтобы развернуть профиль](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), StageNow приложение на устройстве сохраняет журналы из теста. Чтобы получить файл журнала, используйте **Дополнительные (...)**  параметр в приложении StageNow на устройстве.

### <a name="get-logs-using-android-debug-bridge"></a>Получение журналов с помощью моста отладки Android
Чтобы получить журналы после профиль уже развернут с помощью Intune, подключите устройство к компьютеру с помощью [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb) (открывается веб-сайт Android).

На устройстве журналы сохраняются в `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Получить журналы из сообщения электронной почты
Чтобы получить журналы после профиль уже развернут с помощью Intune, конечные пользователи могут вам по электронной почте журналы, используя приложение электронной почты на устройстве. На устройстве Zebra, откройте приложение корпоративного портала, и [отправлять журналы](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Также с помощью функции отправки журналов создает PowerLift инцидента идентификатор, который можно ссылаться в том случае, если обращения в службу поддержки Майкрософт.

## <a name="read-the-logs"></a>Считывает данные журналов

При просмотре журналов, возникает ошибка всякий раз, когда вы видите `<characteristic-error>` тега. Сведения об ошибках записываются в `<parm-error>` тега > `desc` свойство.

## <a name="error-types"></a>Типы ошибок

Zebra устройства включают различные уровнями уведомлений об ошибках:

- CSP не поддерживается на устройстве. Например устройство не мобильной связи устройства и не имеет руководителя сотовой связи.
- Соответствует версии MX или OSX. Каждый поставщик служб Шифрования с контролем версий. Полная поддержка в матрице, см. в разделе [Zebra в документации](http://techdocs.zebra.com/mx/) (открывается в Zebra веб-сайта).
- Устройство сообщает другой проблемы или ошибки.

## <a name="examples"></a>Примеры

Например у вас есть следующий входной профиль:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

В журнале XML идентична входных данных. Это соответствующий результат означает, что профиль, успешно применен к устройству без ошибок:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

В другом примере у вас есть следующие входные данные:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

В журнале отображается ошибка, так как он содержит `<characteristic-error>` тега. В этом случае профиль выполнявшие попытку установить пакет Android (APK), не существует по указанному пути:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="other-potential-issues-with-zebra-devices"></a>Другие потенциальные проблемы с устройствами Zebra

В этом разделе перечислены других возможных проблем, которые могут отображаться при использовании устройств Zebra с администратора устройства. Эти проблемы не передаются в журналах StageNow.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView устарела

Старые устройства в систему с помощью приложения корпоративного портала, пользователи могут видеть, что сообщение, что компонент System WebView устарела и требуется обновить. Если для устройства Google Play установлено, подключите его к Интернету и проверить наличие обновлений. Если на устройстве нет установленным Google Play, получить обновленную версию компонента и применить его к устройствам. Или обновить ОС, выданный Zebra последнюю устройства.

### <a name="management-actions-take-a-long-time"></a>Действия по управлению слишком долго

Если сервисы Google Play недоступны, некоторые задачи занять до 8 часов. [Приложение портала компании ограничений Intune для Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (открывается другой веб-сайт Майкрософт) может быть полезным.

### <a name="device-spoofing-suspected-shows-in-intune"></a>«Устройство спуфинг потенциально» показаны в Intune

Эта ошибка означает, что Intune подозревает, что, не - Zebra Android устройство сообщает собственную модель и производитель как Zebra устройство.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Приложение корпоративного портала старше, чем Минимальная требуемая версия

Intune может обновлять Минимальная требуемая версия приложения корпоративного портала. Если Google Play не установлен на устройстве, приложение корпоративного портала не обновляются автоматически. Если Минимальная требуемая версия более новая, чем установленная версия, приложение корпоративного портала перестанет работать. Обновления для последних приложение корпоративного портала с помощью [для загрузки неопубликованных приложений на устройствах Zebra](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Дальнейшие шаги

[Доски обсуждений Zebra](https://developer.zebra.com/community/home/discussions) (открывается в Zebra веб-сайта)

[Использование устройств и управления ими Zebra с расширениями Zebra мобильных устройств в Intune](android-zebra-mx-overview.md)
