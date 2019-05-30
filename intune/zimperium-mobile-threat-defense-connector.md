---
title: Соединитель MTD Zimperium в Intune
titleSuffix: Intune on Azure
description: Здесь приведены сведения об интеграции Intune с Zimperium Mobile Threat Defense для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b05e9e5b3933e9fbd8ca3f1f03ffd93d2522893e
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046837"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Соединитель Mobile Threat Defense Zimperium с Intune

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств посредством условного доступа на основании оценки рисков, проведенной Zimperium, — решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств, на которых выполняется приложение Zimperium.

Вы можете настроить политики условного доступа на основе оценки рисков, выполненной Zimperium с применением политик соответствия устройств требованиям Intune. Политика оценки рисков может разрешать или блокировать доступ не соответствующих требованиям устройств к корпоративным ресурсам в зависимости от обнаруженных угроз.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Как Intune и Zimperium помогают защитить ресурсы вашей организации?

Мобильное приложение Zimperium для Android или iOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройств и приложений (при наличии), и отправляет их в облачную службу Zimperium для оценки риска в отношении угроз для мобильного устройства.

Политика соответствия устройств Intune включает правило для защиты мобильных устройств от угроз Zimperium, основанное на оценке рисков Zimperium. При включении этого правила Intune оценивает соответствие устройства заданной политике. Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи заблокированных устройств получают от мобильного приложения Zimperium рекомендации по устранению проблемы и восстановлению доступа к корпоративным ресурсам.

## <a name="sample-scenarios"></a>Примеры сценариев

Ниже приведены некоторые сценарии интеграции Zimperium с Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать до устранения угрозы следующие функции.

-   Подключение к корпоративной электронной почте

-   Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

-   Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Схематическое изображение обнаруженных вредоносных приложений](./media/Maliciousapps_blocked_Zimperium.png)

**Доступ восстановлен после исправления:**

![Схематическое изображение предоставления доступа после устранения угрозы](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети

Обнаружение угроз типа  **злоумышленник в середине**  и защита доступа к сетям Wi-Fi на основе рисков для устройств.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка доступа к сети через Wi-Fi](./media/network_wifi_blocked_Zimperium.png)

**Доступ восстановлен после исправления:**

![Доступ предоставляется после устранения угрозы](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз типа  **злоумышленник в середине**  и предотвращение синхронизации корпоративных файлов на основе риска для устройств.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/network_spo_blocked_Zimperium.png)

**Доступ восстановлен после исправления:**

![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Поддерживаемые платформы

-   **Android 4.1 и более поздней версии**.

-   **iOS 8 и более поздние версии**

## <a name="prerequisites"></a>Предварительные условия

-   Azure Active Directory Premium

-   Подписка на Microsoft Intune

-   Подписка на службу Mobile Threat Defense Zimperium

    -   Дополнительные сведения см. на  [веб-сайте Zimperium](https://www.zimperium.com/zips-mobile-ips).

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция Zimperium с Intune](zimperium-mtd-connector-integration.md)

- [Настройка приложений Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Создание политики соответствия устройств Zimperium](mtd-device-compliance-policy-create.md)

- [Включение соединителя MTD Zimperium](mtd-connector-enable.md)
