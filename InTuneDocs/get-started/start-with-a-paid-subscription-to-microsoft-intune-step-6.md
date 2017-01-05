---
title: "Развертывание политик и приложений | Microsoft Intune"
description: "Вы можете включить параметры политики и развернуть приложения, которые будут применяться сразу после регистрации устройств в системе управления."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 56f7d1578ba6b193c6547686675e0fd4fde5f378


---

# <a name="create-policies-and-publish-apps"></a>Создание политик и публикация приложений
Прежде чем начать регистрацию приложений в Intune, можно включить параметры политики и приложения, которые будут развернуты сразу после регистрации устройств в системе управления. Политики Intune предоставляют параметры, позволяющие контролировать безопасность на мобильных устройствах, поддерживать параметры брандмауэра Windows и Endpoint Protection для компьютеров и развертывать приложения. Вы можете настроить политику, добавить и развернуть приложения, чтобы устройства получили параметры и приложения сразу после регистрации в Intune.

Политики и приложения зависят от платформы.

## <a name="manage-device-settings"></a>Управление параметрами устройства

 Настройка параметров политики устройств и управление ими осуществляется в каждой платформе. Политики можно настроить для следующих платформ:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android и Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune);
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (компьютеры и мобильные устройства)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune);
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows для совместной работы](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune);
- [компьютеры Windows с программным клиентом Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune).

Дополнительные сведения см. в статье [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Добавление и развертывание приложений

Добавить приложения в Intune, а затем развернуть их на управляемые устройства можно двумя способами:
- **обязательная установка** — приложения автоматически устанавливают приложение на управляемые устройства;
- **доступная установка** — приложения отображаются на корпоративном портале Intune, благодаря чему пользователи могут выбрать, требуется ли установить их на устройства.

### <a name="add-apps"></a>Добавление приложений

Сначала необходимо сделать приложения доступными в Intune одним из следующих способов:
- [Добавление приложений для зарегистрированных устройств](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [добавление приложений для компьютеров с программным клиентом Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

### <a name="deploy-apps"></a>Развертывание приложений

Теперь, когда приложение доступно в Intune, его можно развернуть на управляемых устройствах:
- [Развертывание приложений на устройствах](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune).
- Развертывание приложений, приобретенных по корпоративной программе:
    - [iOS — программа корпоративных закупок](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune);
    - [Магазин Windows для бизнеса](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune);
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    После настройки приложений для развертывания их можно [настраивать](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) и [отслеживать](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Организация пользователей и устройств**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Настройка корпоративного портала** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->

