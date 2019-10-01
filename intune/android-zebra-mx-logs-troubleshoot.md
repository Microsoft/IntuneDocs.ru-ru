---
title: Использование журналов Стаженов на устройствах Android черно в Microsoft Intune в Azure | Документация Майкрософт
description: См. раздел распространенные проблемы и способы их устранения при использовании Стаженов на устройствах Android с Microsoft Intune. Также Узнайте, как получить журналы, и ознакомьтесь с примерами того, как считать журналы успешными или ошибками.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6110476aace30daa27450326aea3f4abd4fb3ea0
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "71303888"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Устранение неполадок и просмотр потенциальных проблем на устройствах Android черно в Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

В Microsoft Intune можно использовать [расширения черно Mobility Service (MX) для управления устройствами Android черно](android-zebra-mx-overview.md). При использовании устройств черно вы создаете профили в Стаженов для управления параметрами и их отправки в Intune. Intune использует приложение Стаженов для применения параметров на устройствах. Приложение Стаженов также создает подробный файл журнала на устройстве, которое используется для устранения неполадок.

Данная функция применяется к:

- Android

Например, вы создаете профиль в Стаженов для настройки устройства. При создании профиля Стаженов на последнем шаге создается файл для проверки профиля. Этот файл используется в приложении Стаженов на устройстве.

В другом примере вы создадите профиль в Стаженов и проверите его. В Intune вы добавляете профиль Стаженов, а затем назначаете его устройствам черно. При проверке состояния назначенного профиля в профиле отображается состояние высокого уровня.

В обоих случаях можно получить дополнительные сведения из файла журнала Стаженов, который сохраняется на устройстве каждый раз при применении профиля Стаженов.

Некоторые проблемы не связаны с содержимым профиля Стаженов и не отражаются в журналах.

В этой статье показано, как прочитать журналы Стаженов и список других потенциальных проблем с устройствами черно, которые могут не отражаться в журналах.

[Использование и управление устройствами черно с помощью расширений мобильности черно](android-zebra-mx-overview.md) содержит дополнительные сведения об этой функции.

## <a name="get-the-logs"></a>Получение журналов

### <a name="use-the-stagenow-app-on-the-device"></a>Использование приложения Стаженов на устройстве
При тестировании профиля непосредственно с помощью Стаженов на компьютере в вместо того, чтобы использовать [Intune для развертывания профиля](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), приложение стаженов на устройстве сохраняет журналы из теста. Чтобы получить файл журнала, используйте параметр **More (...)** в приложении стаженов на устройстве.

### <a name="get-logs-using-android-debug-bridge"></a>Получение журналов с помощью Android Debug Bridge
Чтобы получить журналы после развертывания профиля с помощью Intune, подключите устройство к компьютеру с [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb) (открывает веб-сайт Android).

На устройстве журналы сохраняются в `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Получение журналов из электронной почты
Чтобы получить журналы после развертывания профиля с помощью Intune, конечные пользователи могут отправлять по электронной почте журналы с помощью приложения электронной почты на устройстве. На устройстве черно откройте приложение корпоративный портал и [отправьте журналы](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). При использовании функции отправки журналов также создается идентификатор инцидента Поверлифт, на который можно сослаться при обращении в службу поддержки Майкрософт.

## <a name="read-the-logs"></a>Чтение журналов

При просмотре журналов возникает ошибка при появлении тега `<characteristic-error>`. Сведения об ошибке записываются в `<parm-error>` Tag > `desc`.

## <a name="error-types"></a>Типы ошибок

Устройства черно включают различные уровни отчетов об ошибках:

- CSP не поддерживается на устройстве. Например, устройство не является мобильным и не имеет диспетчера сотовой сети.
- Несоответствие версии MX или OSX. Каждый CSP имеет версию. Полную таблицу поддержки см. в [документации по черно](http://techdocs.zebra.com/mx/) (открывается веб-сайт черно).
- Устройство сообщает о возникновении другой проблемы или ошибки.

## <a name="examples"></a>Примеры

Например, у вас есть следующий входной профиль:

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

В журнале XML-код идентичен входным данным. Соответствующие выходные данные обозначаются тем, что профиль успешно применен к устройству без ошибок:

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

В другом примере имеются следующие входные данные:

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

В журнале отображается ошибка, так как она содержит тег `<characteristic-error>`. В этом сценарии профиль попытался установить пакет Android (APK), который не существует по указанному пути:

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

## <a name="other-potential-issues-with-zebra-devices"></a>Другие потенциальные проблемы с устройствами черно

В этом разделе перечислены другие возможные проблемы, с которыми можно столкнуться при использовании устройств черно с администратором устройств. Эти проблемы не отображаются в журналах Стаженов.

### <a name="android-system-webview-is-out-of-date"></a>Дата Android System WebView устарела

Когда старые устройства входят с помощью приложения корпоративный портал, пользователи могут видеть сообщение о том, что компонент System WebView устарел и нуждается в обновлении. Если устройство установлено Google Play, подключите его к Интернету и проверьте наличие обновлений. Если на устройстве не установлено Google Play, получите обновленную версию компонента и примените ее к устройствам. Или обновите последнюю версию ОС устройства, выпущенную черно.

### <a name="management-actions-take-a-long-time"></a>Действия по управлению занимают много времени

Если службы Google Play недоступны, выполнение некоторых задач займет до 8 часов. [Ограничения приложения корпоративный портал Intune для Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (открывает другой веб-сайт корпорации Майкрософт), возможно, является хорошим ресурсом.

### <a name="device-spoofing-suspected-shows-in-intune"></a>В Intune отображаются сведения о подозрении на подмену устройства.

Эта ошибка означает, что Intune подозреваете, что черно устройство Android сообщает о своей модели и изготовителе как устройство черно.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>корпоративный порталное приложение старше минимальной требуемой версии

Intune может обновить минимальную требуемую версию корпоративный портал приложения. Если Google Play не установлен на устройстве, корпоративный порталное приложение не обновляется автоматически. Если минимальная требуемая версия новее установленной версии, корпоративный портал приложение перестает работать. Обновление до последней корпоративный портал приложения, использующего загрузку [неопубликованных приложений на устройствах черно](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Дальнейшие шаги

Доски [обсуждений черно](https://developer.zebra.com/community/home/discussions) (открывает веб-сайт черно)

[Использование устройств Zebra с Zebra Mobility Extensions и управление ими в Intune](android-zebra-mx-overview.md)
