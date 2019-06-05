---
title: Создание профилей устройств iOS или macOS в Microsoft Intune — Azure | Документация Майкрософт
description: Добавьте или создайте профиль устройства iOS или macOS и настройте параметры для AirPrint, макета начального экрана, уведомлений приложения, общего устройства, единого входа и фильтрации веб-содержимого в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c85c936e49c277b54b542f372f97b247d6a37
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373805"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Добавление параметров для функций устройств iOS или macOS в Intune

Intune включает в себя множество функций и параметров, которые помогают администраторам управлять устройствами iOS и macOS. Например, администраторы могут:

- предоставлять пользователям доступ к принтерам AirPrint в вашей сети;
- добавлять приложения и папки на начальный экран, включая добавление новых страниц;
- разрешать уведомление приложений и выбирать, как они будут отображаться;
- настраивать экран блокировки так, чтобы отображались сообщение или ярлык, особенно для общих устройств;
- предоставлять пользователям безопасный единый вход в систему для обмена учетными данными между приложениями;
- фильтровать веб-сайты, которые используют язык для взрослых, а также разрешать или блокировать определенные веб-сайты.

Эти функции настраиваются администратором и доступны в Intune. Intune использует "профили конфигурации" для создания и настройки этих параметров для вашей организации. После добавления этих компонентов в профиль вы сможете отправлять или развертывать профиль в устройства iOS и macOS в вашей организации.

В этой статье описано, как создать профиль конфигурации устройства. Вы сможете также просмотреть все доступные параметры для устройств iOS и macOS в этих статьях:[iOS device feature settings in Intune](ios-device-features-settings.md) (Параметры функции устройства iOS в Intune) и [macOS device feature settings in Intune](macos-device-features-settings.md) (Параметры функции устройства macOS в Intune).

## <a name="create-a-device-profile"></a>Создание профиля устройства

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя**. Введите описательное имя для нового профиля.
    - **Описание**. Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите платформу:
        - **iOS**
        - **macOS**
    - **Тип профиля**. Выберите **Возможности устройств**.
    - **Параметры**: Введите параметры, которые вы хотите настроить. См. полный список параметров и сведения об их назначении:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. По завершении нажмите кнопку **ОК** и выберите **Создать**, чтобы сохранить изменения.

Созданный вами профиль отобразится в списке. Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).

## <a name="next-steps"></a>Дальнейшие действия

Созданный профиль готов к назначению. Далее [назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).

См. все параметры функции устройства в статьях [iOS device feature settings in Intune](ios-device-features-settings.md) (Параметры функции устройства iOS в Intune) и [macOS device feature settings in Intune](macos-device-features-settings.md) (Параметры функции устройства macOS в Intune).
