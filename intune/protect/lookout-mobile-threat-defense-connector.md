---
title: Соединитель Lookout MTD в Microsoft Intune
titleSuffix: Microsoft Intune
description: Сведения об интеграции Intune с Lookout Mobile Threat Defense (MTD) для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0123647fb1e8a1d52506ad0753906f974103aad
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502209"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Соединитель Lookout Mobile Endpoint Security с Intune

Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств на основании оценки рисков, проведенной Lookout, решением для защиты от угроз на мобильных устройствах, интегрированным с Microsoft Intune. Оценка рисков основана на данных телеметрии, собранных с устройств службой Lookout и включающих в себя следующее:
- Уязвимости операционной системы
- Установленные вредоносные приложения
- Вредоносные сетевые профили

Вы можете настроить политики условного доступа на основании оценки рисков, выполненной Lookout посредством политик соответствия Intune. Параметры позволяют разрешить или запретить доступ несовместимых устройств в зависимости от обнаруженных угроз.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Как Intune и Lookout Mobile Endpoint Security помогают защитить ресурсы организации?
Приложение **Lookout for work** устанавливается и выполняется на мобильных устройствах. Оно регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу защиты от угроз на устройстве Lookout для вычисления риска в отношении угроз для мобильного устройства. Вы можете изменить классификации уровней риска для угроз в консоли Lookout, исходя из своих потребностей.  

Политика соответствия в Intune содержит правило для службы защиты мобильных устройств от угроз Lookout, основанное на оценке рисков Lookout. При включении этого правила Intune оценивает соответствие устройства заданной политике.

Если устройство определяется как несоответствующее, можно заблокировать его доступ к таким ресурсам, как Exchange Online и SharePoint Online. Пользователи заблокированных устройств получают сведения о том, что нужно сделать, чтобы устранить проблему и восстановить доступ. Соответствующее руководство запускается в приложении Lookout for Work.

## <a name="supported-platforms"></a>Поддерживаемые платформы  
При регистрации в Intune для Lookout поддерживаются следующие платформы:
* **Android 4.1 и более поздней версии**.  
* **iOS 8 и более поздние версии**  

Дополнительные сведения о поддержке платформы и языка см. на [веб-сайте Lookout](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Предварительные условия
* Корпоративная подписка на Lookout Mobile Endpoint Security  
* Подписка на Microsoft Intune
* Azure Active Directory Premium
* Enterprise Mobility and Security (EMS) E3 или E5 с лицензиями, назначенными пользователям.  

Дополнительные сведения см. в разделе [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Примеры сценариев

Ниже приведены распространенные сценарии при использовании службы Mobile Endpoint Security с Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений
При обнаружении на устройствах вредоносного ПО можно заблокировать следующие возможности до устранения угрозы:
* Подключение к корпоративной электронной почте
* Синхронизация корпоративных файлов с помощью приложения OneDrive для работы
* Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ:**

![Схематическое изображение блокирования доступа политикой из-за вредоносных приложений](./media/lookout-mobile-threat-defense-connector/malicious-apps-blocked.png)

**Доступ восстановлен после исправления:**

![Схематическое изображение предоставления доступа к устройствам после устранения угрозы](./media/lookout-mobile-threat-defense-connector/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основании оценки угрозы для сети
Обнаружение угроз для вашей сети, таких как атаки "злоумышленник в середине", и защита доступа к сети Wi-Fi на основе рисков, связанных с устройствами.

**Блокировка доступа к сети через Wi-Fi:**

![Изображение блокирования доступа к Wi-Fi из-за угроз для сети](./media/lookout-mobile-threat-defense-connector/network-wifi-blocked.png)

**Доступ восстановлен после исправления:**

![Схематическое изображение предоставления доступа политикой условного доступа после устранения угрозы](./media/lookout-mobile-threat-defense-connector/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основании оценки угрозы для сети

Обнаружение угроз для вашей сети, таких как атаки "злоумышленник в середине", и блокирование синхронизации корпоративных файлов на основании риска для устройства.

**Блокирование SharePoint Online при обнаружении сетевых угроз:**

![Схематическое изображение блокирования доступа к SharePoint Online](./media/lookout-mobile-threat-defense-connector/network-spo-blocked.png)


**Доступ восстановлен после исправления:**

![Схематическое изображение предоставления доступа после устранения сетевой угрозы](./media/lookout-mobile-threat-defense-connector/network-spo-unblocked.png)

## <a name="next-steps"></a>Дальнейшие шаги
Ниже приведены основные шаги, которые необходимо выполнить для реализации этого решения.
1. [Настройка интеграции с Lookout](lookout-mtd-connector-integration.md)
2. [Включение Mobile Endpoint Security в Intune](mtd-connector-enable.md)
3. [Добавление и назначение приложения Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4. [Настройка политики соответствия устройств Lookout](mtd-device-compliance-policy-create.md)
