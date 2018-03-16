---
title: "Соединитель Check Point SandBlast Mobile для Intune"
titlesuffix: Azure portal
description: "Интеграция Check Point SandBlast Mobile с Intune"
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 10bc23b5b5e0d0d278677ed4bf332787fc16b367
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Соединитель Check Point SandBlast Mobile Threat Defense для Intune

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств посредством условного доступа на основании оценки рисков, проведенной Check Point SandBlast Mobile — решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств, на которых установлено приложение Check Point SandBlast Mobile.

Вы можете настроить политики условного доступа на основе оценки рисков Check Point SandBlast Mobile, реализуемой с помощью политик соответствия устройств Intune. Эти политики также можно использовать для разрешения или запрета доступа несовместимых устройств к ресурсам организации на основании обнаруженных угроз.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Как Intune и Check Point SandBlast Mobile помогают защитить ресурсы вашей организации?

Мобильное приложение Check Point SandBlast Mobile для Android или iOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу Check Point SandBlast для вычисления риска в отношении угроз для мобильного устройства.

Политика соответствия устройств Intune включает правило Check Point SandBlast Mobile для защиты мобильных устройств от угроз, основанное на оценке рисков Check Point SandBlast. При включении этого правила Intune оценивает соответствие устройства заданной политике. Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи заблокированных устройств получают от мобильного приложения Check Point SandBlast Mobile рекомендации по устранению проблемы и восстановлению доступа к корпоративным ресурсам.

<!-- ## Sample scenarios 
closing syntax for comment above is missing. Please insert closing syntax at intended location. -->

Далее приведены некоторые распространенные сценарии.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать до устранения угрозы следующие функции.

-   Подключение к корпоративной электронной почте

-   Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

-   Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Блокировка Check Point MTD при обнаружении вредоносных программ](./media/checkpoint-MTD-2.PNG)

**Доступ восстановлен после исправления:**

![Предоставлен доступ Check Point MTD](./media/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и защита доступа к сетям Wi-Fi на основе рисков для устройств.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка Check Point MTD доступа к сети через Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Доступ восстановлен после исправления:**

![Предоставлен доступ Check Point MTD к сети Wi-Fi](./media/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и предотвращение синхронизации корпоративных файлов на основе риска для устройств.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка Check Point MTD доступа к SharePoint Online](./media/checkpoint-MTD-6.PNG)

**Доступ восстановлен после исправления:**

![Предоставлен доступ Check Point MTD к SharePoint Online](./media/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Поддерживаемые платформы

-   **Android 4.1 и более поздней версии**.

-   **iOS 8 и более поздние версии**

## <a name="pre-requisites"></a>Предварительные условия

-   Azure Active Directory Premium

-   Подписка на Microsoft Intune

-   Подписка на Check Point SandBlast Mobile Threat Defense
    -   Дополнительные сведения см. на [веб-сайте CheckPoint SandBlast](https://www.checkpoint.com/).

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция CheckPoint SandBlast с Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Настройка приложения CheckPoint SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Создание политики соответствия требованиям CheckPoint SandBlast Mobile](mtd-device-compliance-policy-create.md)

- [Включение соединителя CheckPoint SandBlast Mobile MTD](mtd-connector-enable.md)
