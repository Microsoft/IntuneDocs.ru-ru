---
title: Соединитель Symantec в Microsoft Intune
titleSuffix: Microsoft Intune
description: Сведения об интеграции Intune с Symantec Endpoint Protection Mobile для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 60bad9299a3751474ef01220a7c18f16be329448
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782079"
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Соединитель Symantec Endpoint Protection Mobile

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств с помощью условного доступа на основе оценки рисков, проведенной Symantec Endpoint Protection Mobile (SEP Mobile), — решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств, на которых работает SEP Mobile, включая следующее:

- Физическая защита

- Защита сети

- Защита приложений

- Защита от уязвимостей

Вы можете настроить оценку рисков SEP Mobile с помощью политик соответствия устройств Intune, а затем применить политики условного доступа, чтобы разрешить или запретить доступ несовместимых устройств к ресурсам организации с учетом обнаруженных угроз.

> [!NOTE]
> Этот поставщик защиты от мобильных угроз не поддерживается для незарегистрированных устройств.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>Как Intune и SEP Mobile помогают защитить ресурсы вашей организации?

Приложение SEP Mobile для Android или iOS/iPadOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу Symantec для оценки риска мобильных угроз на этом устройстве.

Политика соответствия устройств Intune содержит правило для SEP Mobile, основанное на оценке рисков SEP Mobile. При включении этого правила Intune оценивает соответствие устройства заданной политике.

Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи заблокированных устройств получают от приложения SEP Mobile рекомендации о том, как можно устранить проблемы и восстановить доступ к корпоративным ресурсам.

Intune поддерживает два режима интеграции с SEP Mobile.

- **Базовая настройка**. Это режим доступа только для чтения, позволяющий SEP Mobile видеть устройства в Intune.

- **Полная интеграция**. Этот режим позволяет SEP Mobile передавать в Intune данные по рискам для устройств и инцидентам безопасности.

## <a name="sample-scenarios"></a>Примеры сценариев

Далее приведены некоторые распространенные сценарии.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений

При обнаружении на устройствах вредоносного ПО можно заблокировать до устранения угрозы следующие функции.

- Подключение к корпоративной электронной почте

- Синхронизация корпоративных файлов с помощью приложения OneDrive для работы

- Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Схематическое изображение обнаруженных вредоносных приложений](./media/skycure-mobile-threat-defense-connector/symantec-arch-1.png)

**Доступ восстановлен после исправления:**

![Изображение предоставления доступа после устранения угрозы в случае обнаружения вредоносных приложений](./media/skycure-mobile-threat-defense-connector/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основе угроз для сети

Обнаружение угроз типа **злоумышленник в середине** и защита доступа к сетям Wi-Fi на основе рисков для устройств.

**Блокировка доступа к сети через Wi-Fi:**

![Блокировка доступа к сети через Wi-Fi](./media/skycure-mobile-threat-defense-connector/symantec-arch-3.png)

**Доступ восстановлен после исправления:**

![Доступ предоставляется после устранения угрозы](./media/skycure-mobile-threat-defense-connector/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основе оценки угроз для сети

Обнаружение угроз типа **злоумышленник в середине** и предотвращение синхронизации корпоративных файлов на основе риска для устройств.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/skycure-mobile-threat-defense-connector/symantec-arch-5.png)

**Доступ восстановлен после исправления:**

![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/skycure-mobile-threat-defense-connector/symantec-arch-6.png)

## <a name="supported-platforms"></a>Поддерживаемые платформы

- **Android 4.1 и более поздней версии**.

- **iOS 8 и более поздние версии**

## <a name="pre-requisites"></a>Предварительные условия

- Azure Active Directory Premium

- Подписка на Microsoft Intune

- Подписка Symantec Endpoint Protection Mobile

Дополнительные сведения см. на [веб-сайте Symantec](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Дальнейшие шаги

Следующие шаги помогут завершить интеграцию Intune с SEP Mobile:

- [Настройка интеграции SEP Mobile и Intune](skycure-mtd-connector-integration.md)

- [Добавление и назначение приложений SEP Mobile, Microsoft Authenticator и политики настройки приложений iOS/iPadOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Создание политики соответствия для устройств SEP Mobile в Intune](mtd-device-compliance-policy-create.md)

- [Включение соединителя SEP Mobile MTD в Intune](mtd-connector-enable.md)
