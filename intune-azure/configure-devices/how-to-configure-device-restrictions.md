---
title: "Настройка ограничений для устройств Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: сведения о настройке параметров и функций на управляемых устройствах с помощью Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: b593b2ddd756bc5bf7700eca4f2544b87008a8ab
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Настройка параметров ограничений для устройств iOS в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ограничения устройств позволяют управлять параметрами и функциями разных категорий, включая безопасность, браузер, оборудование и общий доступ к данным. Например, можно создать профиль ограничения устройства, который запрещает доступ к камере пользователям устройств iOS.

Эта статья содержит базовые сведения о настройке профилей ограничения устройств, а также ссылки на статьи со сведениями об особенностях устройств, работающих под управлением разных платформ.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Создание профиля устройства с параметрами ограничения для устройства

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Другое** > **Intune**.
3. В колонке **Intune** выберите **Настройка устройств**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создание профиля**.
4. В колонке **Создание профиля** введите **Имя** и **Описание** для профиля ограничения устройства.
5. В раскрывающемся списке **Платформа** выберите платформу устройства, к которой необходимо применить настроенные параметры. Сейчас для параметров ограничения устройства можно выбрать одну из следующих платформ:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 и более поздние версии**
    - **Windows 10 и более поздние версии**.
6. В раскрывающемся списке **Тип профиля** выберите **Ограничения устройств**. Если вы хотите создать профиль ограничений для устройств Windows 10 для совместной работы, например Surface Hub, выберите **Ограничения для устройств (Windows 10 для совместной работы)**.
7. Доступные для настройки параметры будут отличаться в зависимости от выбранной платформы. Дополнительные сведения о параметрах для каждой платформы см. по ссылкам ниже.
    - [Параметры Android](device-restrictions-for-android.md)
    - [Параметры iOS](device-restrictions-for-ios.md)
    - [Параметры macOS](device-restrictions-for-macos.md)
    - [Параметры Windows Phone 8.1](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Параметры Windows 10](device-restrictions-for-windows-10.md)
    - [Параметры Windows 10 для совместной работы](device-restrictions-for-windows-10-team.md)
8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.
Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройствам](how-to-assign-device-profiles.md).

## <a name="example-of-device-restriction-settings"></a>Пример параметров ограничения для устройств

В этом примере вы создадите политику ограничений устройства, которая блокирует использование встроенной камеры на устройствах Android.

![Как отключить камеру на устройствах Android](./media/disable-android-camera.png)


