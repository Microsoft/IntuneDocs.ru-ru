---
title: Соединитель Better Mobile Threat Defense в Intune
titleSuffix: Intune on Azure
description: Настройте соединитель Better Mobile Threat Defense в Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 7/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.openlocfilehash: 8eeb55ca9e2c698d2d9e1814e9ea17f779326732
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52178500"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Соединитель Better Mobile Threat Defense в Intune

Вы можете управлять доступом с мобильных устройств к корпоративным ресурсам, используя условный доступ на основе оценки рисков. Такую возможность дает вам Better Mobile — решение Mobile Threat Defense (MTD), интегрируемое с Microsoft Intune. Оценка рисков основана на телеметрии, собираемой с устройств с запущенным приложением Better Mobile.

Вы можете настроить политики условного доступа на основе оценки рисков Better Mobile, реализуемой с помощью политик соответствия устройств Intune. Эти политики также позволяют разрешать или блокировать доступ к корпоративным ресурсам с устройств, не соответствующих требованиям в зависимости от обнаруженных угроз.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Каким образом Intune и Better Mobile помогают защитить ресурсы вашей организации?

Приложение Better Mobile устанавливается и запускается на мобильных устройствах. Оно собирает данные телеметрии по файловой системе, сетевому стеку, устройствам и приложениям (при наличии) и отправляет эти данные в облачную службу Better Mobile для оценки на устройстве риска мобильных угроз.

Политика соответствия устройств Intune включает правило Mobile Threat Defense, основанное на оценке рисков Better Mobile. При включении этого правила Intune оценивает соответствие устройства заданной политике. Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи также получают от приложения Better Mobile, установленного на устройстве, рекомендации по устранению проблемы и восстановлению доступа к корпоративным ресурсам.

## <a name="sample-scenarios"></a>Примеры сценариев

Далее приведены некоторые распространенные сценарии.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать следующие действия до устранения угрозы:

-   Подключение к корпоративной электронной почте

-   Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

-   Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Обнаружены вредоносные приложения](./media/better_mobile_maliciousapps_blocked.png)

**Доступ восстановлен после исправления:**

![Обнаружены вредоносные приложения, доступ предоставлен](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети

Обнаружение угроз для вашей сети, таких как атаки **злоумышленник в середине**, и защита доступа к сети Wi-Fi на основе рисков, связанных с устройствами.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка доступа к сети через Wi-Fi](./media/better_mobile_network_wifi_blocked.png)

**Доступ восстановлен после исправления:**

![Доступ предоставляется после устранения угрозы](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз для вашей сети, таких как атаки **злоумышленник в середине**, и блокирование синхронизации корпоративных файлов на основании риска для устройства.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/better_mobile_network_spo_blocked.png)

**Доступ восстановлен после исправления:**

![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Поддерживаемые платформы

-   **Android 4.1 и более поздней версии**.

-   **Устройства iOS 8.0 и более поздних версий**

## <a name="prerequisites"></a>Предварительные условия

-   Azure Active Directory Premium

-   Подписка на Microsoft Intune

-   Подписка на Better Mobile Threat Defense

    -   Дополнительные сведения см. на [веб-сайте Better Mobile](https://www.better.mobi/).

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция Better Mobile с Intune](better-mobile-mtd-connector-integration.md)

- [Настройка приложений Better Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Создание политики соответствия устройств Better Mobile](mtd-device-compliance-policy-create.md)

- [Включение MTD-соединителя Better Mobile](mtd-connector-enable.md)