---
title: Добавление параметров файла предпочтений на устройства macOS в Microsoft Intune в Azure | Документация Майкрософт
titleSuffix: ''
description: Добавьте файл XML или plist, содержащий ключевые сведения о приложении. Используйте профиль конфигурации устройства файл предпочтения, чтобы изменить ключевые сведения в файле списка свойств и назначить его устройствам macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ed04c1bf135793da9cece9debc2c7cdd481601a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74691694"
---
# <a name="add-a-property-list-file-to-macos-devices-using-microsoft-intune"></a>Добавление файла списка свойств на устройства macOS с помощью Microsoft Intune

С помощью Microsoft Intune можно добавить файл списка свойств (plist) для устройств macOS или приложений на устройствах macOS.

Данная функция применяется к:

- устройства macOS версии 10.7 и новее

Файлы списка свойств обычно содержат сведения о macOS приложениях. Дополнительные сведения см. в разделе [о файлах со списком свойств информации](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (веб-сайт Apple) и [пользовательских параметрах полезных данных](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).

В этой статье перечислены и описаны различные параметры файла списка свойств, которые можно добавить на устройства macOS. В рамках решения по управлению мобильными устройствами (MDM) Используйте эти параметры, чтобы добавить идентификатор набора приложений (`com.company.application`) и добавить его PLIST-файл.

Эти параметры можно добавить в профиль конфигурации устройства в Intune, а затем назначить или развернуть на устройствах c macOS.

## <a name="before-you-begin"></a>Подготовка к работе

[Создайте профиль](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Что необходимо знать

- Эти параметры не проверяются. Не забудьте проверить изменения перед назначением профиля устройствам.
- Если вы не знаете, как ввести ключ приложения, измените параметр в приложении. Затем просмотрите файл настроек приложения с помощью [Xcode](https://developer.apple.com/xcode/) , чтобы увидеть, как настроен параметр. Компания Apple рекомендует удалить неуправляемые параметры с помощью Xcode перед импортом файла.
- Только некоторые приложения работают с управляемыми настройками и могут не позволить управлять всеми параметрами.
- Не забудьте отправить файлы списка свойств, предназначенные для настройки канала устройства, а не параметры канала пользователя. Файлы списка свойств предназначены для всего устройства.

## <a name="preference-file"></a>Файл предпочтений

- **Имя домена предпочтений**. файлы списка свойств обычно используются для веб-браузеров (Microsoft ребра), [Microsoft защитника Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac)и пользовательских приложений. При создании домена предпочтений также создается идентификатор пакета. Введите идентификатор пакета, например `com.company.application`. Например, введите `com.Contoso.applicationName`, `com.Microsoft.Edge` или `com.microsoft.wdav`.
- **Файл списка свойств**: выберите файл со списком свойств, связанный с вашим приложением. Убедитесь, что это файл `.plist` или `.xml`. Например, отправьте файл `YourApp-Manifest.plist` или `YourApp-Manifest.xml`.
- **Содержимое файла**: сведения о ключе в файле списка свойств. Если необходимо изменить сведения о ключе, откройте файл списка в другом редакторе, а затем повторно отправьте файл в Intune.

Щелкните **OK** > **Создать**, чтобы сохранить изменения. Созданный профиль отобразится в списке профилей.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но он пока ничего не делает. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

Дополнительные сведения о файлах предпочтений для Microsoft ребр см. [в статье Настройка параметров политики Microsoft ребра в macOS](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac).
