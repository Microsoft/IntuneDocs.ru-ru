---
title: Использование ПИН-кода для входа на устройства Windows 10 с помощью Microsoft Intune в Azure | Документация Майкрософт
description: Используйте Windows Hello для бизнеса, чтобы пользователи могли входить на устройства с помощью ПИН-кода, отпечатка пальца и т. д. С помощью этих параметров создайте профиль конфигурации защиты личных данных на устройствах Intune для Windows 10 и назначьте профиль группам пользователей и группам устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e4f2c76e2d490bf5b3002723ca41a851e0a591d
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235486"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Использование Windows Hello для бизнеса на устройствах Windows 10 с Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows Hello для бизнеса — это метод входа на устройства Windows путем замены паролей, смарт-карт и виртуальных смарт-карт. Intune содержит встроенные параметры, позволяющие администраторам настраивать и использовать Windows Hello для бизнеса. Например, вы можете использовать эти параметры, чтобы:

- включить Windows Hello для бизнеса для устройств и пользователей;
- установить требования к ПИН-коду устройства, включая минимальную или максимальную длину ПИН-кода;
- разрешить жесты (например, отпечаток пальца), которые пользователи могут (или не могут) использовать для входа на устройства.

Эта возможность применима к устройствам с:

- Windows 10 и более поздней версии
- Windows 10 Mobile
- Windows Holographic for Business

Intune использует "профили конфигурации" для создания и настройки этих параметров для вашей организации. Добавив эти компоненты в профиле, отправьте или разверните эти параметры для групп пользователей или устройств в вашей организации.

В этой статье описано, как создать профиль конфигурации устройства. Список всех параметров и их назначение см. в статье [Windows 10 (and newer) device settings to enable Windows Hello for Business in Intune](identity-protection-windows-settings.md) (Параметры устройства Windows 10 (и более поздних версий) для включения Windows Hello для бизнеса в Intune).

## <a name="create-the-device-profile"></a>Создание профиля устройства

1. На [портале Azure](https://portal.azure.com) выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя**. Введите описательное имя для нового профиля.
    - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите **Windows 10 и более поздних версий**. Windows Hello для бизнеса — поддерживается только на устройствах под управлением Windows 10 и более поздних версий.
    - **Тип профиля**. Выберите **Защита удостоверений**.
    - **Настройка Windows Hello для бизнеса**. Выберите, как вы хотите настроить Windows Hello для бизнеса. Доступны следующие параметры:

        - **Не настроено**. [Подготовка Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) на устройстве. При назначении профилей защиты идентификации только пользователям по умолчанию используется контекст устройства **Не настроен**.
        - **Отключено**. Если вы не хотите использовать Windows Hello для бизнеса, выберите этот параметр. Этот параметр отключает Windows Hello для бизнеса для всех пользователей.
        - **Включен**. Выберите этот параметр, чтобы [подготовить к работе]((https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning)) и настроить параметры Windows Hello для бизнеса в Intune. Введите параметры, которые вы хотите настроить. См. полный список параметров и сведения об их назначении:

            - [Windows 10 (and newer) device settings to enable Windows Hello for Business in Intune](identity-protection-windows-settings.md) (Параметры устройства Windows 10 (и более поздних версий) для включения Windows Hello для бизнеса в Intune).

4. По завершении нажмите **ОК** > **Создать**, чтобы сохранить изменения.

Созданный профиль отобразится в списке профилей. Затем [назначьте](device-profile-assign.md) этот профиль требуемым группам пользователей и устройств.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>Дальнейшие шаги

- См. полный список параметров и сведения об их назначении [здесь](identity-protection-windows-settings.md).
- [Назначьте профиль](device-profile-assign.md) и [отслеживайте его состояние](device-profile-monitor.md).
