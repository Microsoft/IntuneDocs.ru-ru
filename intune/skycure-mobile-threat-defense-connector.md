---
title: Соединитель Symantec в Microsoft Intune
titlesuffix: ''
description: Сведения об интеграции Intune с Symantec Endpoint Protection Mobile для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/09/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 577eff3a5f3965065a4066973ea8c61160ab4563
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Соединитель Symantec Endpoint Protection Mobile

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств с помощью условного доступа на основе оценки рисков, проведенной Symantec Endpoint Protection Mobile (SEP Mobile) — решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств, на которых работает SEP Mobile, включая следующее:

-   Физическая защита

-   Защита сети

-   Защита приложений

-   Защита от уязвимостей

Вы можете настроить оценку рисков SEP Mobile с помощью политик соответствия устройств Intune, а затем применить политики условного доступа для разрешения или запрета доступа несовместимых устройств к ресурсам организации с учетом обнаруженных угроз.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>Как Intune и SEP Mobile помогают защитить ресурсы вашей организации?

Приложение SEP Mobile для Android или iOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу Symantec для оценки риска мобильных угроз на этом устройстве.

Политика соответствия устройств Intune содержит правило для SEP Mobile, основанное на оценке рисков SEP Mobile. При включении этого правила Intune оценивает соответствие устройства заданной политике.

Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи заблокированных устройств получают от приложения SEP Mobile рекомендации о том, как можно устранить проблемы и восстановить доступ к корпоративным ресурсам.

Intune поддерживает два режима интеграции с SEP Mobile.

-   **Базовая настройка**. Это режим доступа только для чтения, позволяющий SEP Mobile видеть устройства в Intune.

-   **Полная интеграция**. Этот режим позволяет SEP Mobile передавать в Intune данные по рискам для устройств и инцидентам безопасности.

## <a name="sample-scenarios"></a>Примеры сценариев

Далее приведены некоторые распространенные сценарии.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать до устранения угрозы следующие функции.

-   Подключение к корпоративной электронной почте

-   Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

-   Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Обнаружены вредоносные приложения](./media/symantec-arch-1.png)

**Доступ восстановлен после исправления:**

![Доступ предоставляется после устранения угрозы в случае обнаружения вредоносных приложений](./media/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и защита доступа к сетям Wi-Fi на основе рисков для устройств.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка доступа к сети через Wi-Fi](./media/symantec-arch-3.png)

**Доступ восстановлен после исправления:**

![Доступ предоставляется после устранения угрозы](./media/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз типа **злоумышленник в середине** и предотвращение синхронизации корпоративных файлов на основе риска для устройств.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/symantec-arch-5.png)

**Доступ восстановлен после исправления:**

![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/symantec-arch-6.png)

## <a name="supported-platforms"></a>Поддерживаемые платформы

-   **Android 4.1 и более поздней версии**.

-   **iOS 8 и более поздние версии**

## <a name="pre-requisites"></a>Предварительные условия

-   Azure Active Directory Premium

-   Подписка на Microsoft Intune

-   Подписка Symantec Endpoint Protection Mobile

Дополнительные сведения см. на [веб-сайте Symantec](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Дальнейшие шаги

Следующие шаги помогут завершить интеграцию Intune с SEP Mobile:

- [Настройка интеграции SEP Mobile и Intune](skycure-mtd-connector-integration.md)

- [Добавление и назначение приложений SEP Mobile, Microsoft Authenticator и политики настройки приложений iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Создание политики соответствия для устройств SEP Mobile в Intune](mtd-device-compliance-policy-create.md)

- [Включение соединителя SEP Mobile MTD в Intune](mtd-connector-enable.md)
