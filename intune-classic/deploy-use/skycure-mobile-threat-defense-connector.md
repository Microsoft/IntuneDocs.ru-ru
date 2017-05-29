---
title: "Соединитель службы защиты мобильных устройств от угроз Skycure | Документация Майкрософт"
description: "Защита доступа к ресурсам организации на основе риска для устройств, сети и приложений с помощью соединителя службы защиты мобильных устройств от угроз Skycure и Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 15b00957f694863bb10ee32162eb20fc39bcda88
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="skycure-mobile-threat-defense-connector"></a>Соединитель службы защиты мобильных устройств от угроз Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств посредством условного доступа на основании оценки рисков, проведенной Skycure, решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств, на которых работает Skycure, включая следующее.

-   Физическая защита

-   Защита сети

-   Защита приложений

-   Защита от уязвимостей

Вы можете настроить политики условного доступа на основе оценки рисков Skycure, реализуемой с помощью политик соответствия устройств Intune. Эти политики также можно использовать для разрешения или запрета доступа несовместимых устройств к корпоративным ресурсам на основании обнаруженных угроз.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Как Intune и Skycure помогают защитить ресурсы вашей организации?

Мобильное приложение Skycure для Android или iOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу Skycure для вычисления риска в отношении угроз для мобильного устройства.

Политика соответствия устройств Intune включает правило для защиты мобильных устройств от угроз Skycure, основанное на оценке рисков Skycure. При включении этого правила Intune оценивает соответствие устройства заданной политике.

Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи заблокированных устройств получают рекомендации от мобильного приложения Skycure для устранения проблемы и восстановления доступа к корпоративным ресурсам.

Intune поддерживает два режима интеграции с Skycure.

-   **Базовая настройка** — режим только для чтения, позволяющий Skycure видеть устройства в Intune.

-   **Полная интеграция** — режим, который позволяет Skycure сообщать в Intune данные по рискам для устройств и инцидентам безопасности.

## <a name="sample-scenarios"></a>Примеры сценариев

Далее приведены некоторые распространенные сценарии.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать до устранения угрозы следующие функции.

-   Подключение к корпоративной электронной почте

-   Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

-   Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Обнаружены вредоносные приложения](../media/mtp/skycure-arch-1.png)

**Доступ предоставлен после устранения угрозы:**

![Обнаружены вредоносные приложения, доступ предоставлен](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и защита доступа к сетям Wi-Fi на основе рисков для устройств.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка доступа к сети через Wi-Fi](../media/mtp/skycure-arch-3.png)

**Доступ предоставлен после устранения угрозы:**

![Доступ предоставляется после устранения угрозы](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и предотвращение синхронизации корпоративных файлов на основе риска для устройств.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка SharePoint Online при обнаружении сетевых угроз](../media/mtp/skycure-arch-5.png)

**Доступ предоставлен после устранения угрозы:**

![Пример предоставления доступа к Sharepoint после устранения угрозы](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a>Поддерживаемые платформы

-   **Android 4.1 и более поздней версии**.

-   **iOS 8 и более поздние версии**

## <a name="pre-requisites"></a>Предварительные условия

-   Azure Active Directory Premium

-   Подписка Microsoft Intune

-   Подписка на службу защиты мобильных устройств от угроз Skycure

Дополнительные сведения см. на [веб-сайте Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Дальнейшие действия

Что нужно сделать для интеграции Intune с Skycure:

1.  [Настройка единого входа Azure Active Directory для Skycure /intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Скачать политику конфигурации приложения Skycure для iOS](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [добавить приложения Skycure, Microsoft Authenticator и политику конфигурации приложения для iOS;](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [развернуть приложения Skycure, Microsoft Authenticator и политику конфигурации приложения для iOS;](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [настроить интеграцию Skycure и Intune;](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Включение службы защиты мобильных устройств от угроз Skycure в Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [создать в Intune политику соответствия для службы защиты мобильных устройств от угроз Skycure.](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

