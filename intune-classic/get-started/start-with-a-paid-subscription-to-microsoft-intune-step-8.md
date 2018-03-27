---
title: Обеспечение регистрации устройств
description: Задание центра MDM и обеспечение регистрации для устройств iOS, Windows, Android и Mac.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e9572181fb15ec97e7ae4c11a8ab2e4fe4cc9b30
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="enable-enrollment-for-mobile-devices"></a>Включение регистрации для мобильных устройств

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В этом разделе описывается, как администратор Intune может включить регистрацию мобильных устройств. Справку по использованию Intune на телефоне см. в разделе [Использование управляемых устройств для выполнения задач](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).

Чтобы настроить управление мобильными устройствами с помощью Intune, необходимо сначала задать *центр управления мобильными устройствами*, который идентифицирует службу, позволяющую управлять устройствами, связанными с учетной записью. В этом руководстве предполагается, что вместо System Center Configuration Manager будет использоваться служба Intune. Задав центр управления мобильными устройствами, можно включить управление для платформ устройств и зарегистрировать устройства с помощью приложения корпоративного портала.

## <a name="enable-device-enrollment"></a>Обеспечение регистрации устройств

1. **Превращение Intune в центр управления мобильными устройствами**. В [консоли администрирования Intune](https://manage.microsoft.com/) щелкните **Администратор** > **Управление мобильными устройствами** и в разделе **Задачи** выберите **Set MDM Authority** (Выбрать в качестве центра MDM).  

2. Выберите **Да** в диалоговом окне "Центр MDM" .

    ![Консоль администрирования. Настройка MDM в Intune](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>Выбор способа регистрации устройств

Intune может управлять устройствами различными способами в зависимости от требований вашей компании. "Принеси свое устройство" (BYOD), корпоративные устройства, "выбери свое устройство" (CYOD) и устройства в полноэкранном режиме — это лишь несколько доступных сценариев регистрации.

Выполните следующие действия, чтобы [выбрать способ регистрации мобильных устройств](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Включение MDM для вашей платформы устройств
Регистрацию необходимо включить для устройств iOS, Mac и Android for Work, чтобы установить отношения между поставщиком платформы и клиентом Intune. Для устройств Windows и Android не требуются дополнительные действия, но можно упростить регистрацию устройств Windows для пользователей, создав специальную запись реестра DNS.

Включите регистрацию устройств для платформы устройств, которой необходимо управлять. В зависимости от используемой платформы есть различные требования:

- [iOS и macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune);
- [Windows 10 и Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [ПК Windows](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (программный клиент Intune)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

После включения регистрации пользователи могут скачать приложение корпоративного портала на устройство и завершить процесс регистрации устройства.

### <a name="enable-company-owned-device-enrollment"></a>Обеспечение регистрации устройств, принадлежащих компании
Вы также можете реализовать различные сценарии [регистрации устройств, принадлежащих компании](/intune-classic/deploy-use/manage-corporate-owned-devices), включая следующие:
- [программа регистрации устройств Apple](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune);
- [помощник по настройке регистрации Apple Configurator](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune);
- [прямая регистрация с помощью Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune);
- [диспетчер регистрации устройств](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

### <a name="next-steps"></a>Дальнейшие шаги
Поздравляем! Вы завершили последний шаг *краткого руководства по Intune*. Теперь, когда начальная настройка завершена, рассмотрите возможность включения дополнительных функций MDM.

>[!div class="step-by-step"]
>[&larr; **Регистрация устройств**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Задачи, выполняемые после настройки** &rarr;](.\post-configuration-tasks.md)  
