---
title: Настройка Wandera Mobile Security с использованием Intune
titleSuffix: Intune on Azure
description: Как настроить Wandera Mobile Security с использованием Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств.
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
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f82a64cdb66528e3e1d3a81fd6119c4a99dff504
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782255"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Соединитель Wandera Mobile Threat Defense в Intune  

Управляйте условным доступом к корпоративным ресурсам с мобильных устройств на основе оценки рисков, проведенной Wandera. Wandera — это решение Mobile Threat Defense (MTD), которое интегрируется с Microsoft Intune.  Оценка рисков основана на данных телеметрии, собранных с устройств службой Wandera. Такие данные включают:
- Уязвимости операционной системы
- Установленные вредоносные приложения
- Вредоносные сетевые профили
- сведения о криптоджекинге.

Вы можете настроить политики *условного доступа* на основе оценки рисков, выполненной Wandera с применением политик соответствия устройств требованиям Intune. Политика оценки рисков может разрешать или блокировать доступ не соответствующих требованиям устройств к корпоративным ресурсам в зависимости от обнаруженных угроз.  

> [!NOTE]
> Этот поставщик защиты от мобильных угроз не поддерживается для незарегистрированных устройств.

## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Как Intune и Wandera Mobile Threat Defense помогают защитить ресурсы организации  

Мобильное приложение Wandera можно без труда установить с помощью Microsoft Intune. Приложение собирает сведения о файловой системе, сетевом стеке, а также данные телеметрии устройств и приложений (при возможности). Этот информация синхронизируется с облачной службой Wandera для оценки риска угроз для мобильных устройств. Вы можете настроить классификации уровней риска в соответствии со своими потребностями в консоли Wandera RADAR.

Политика соответствия требованиям в Intune включает правило для MTD, основанное на выполняемой Wandera оценке рисков. При включении этого правила Intune оценивает соответствие устройства заданной политике.

Для устройств, которые не соответствуют требованиям, доступ к таким ресурсам, как Office 365, может быть заблокирован. Пользователи заблокированных устройств получают от приложения Wandera рекомендации о том, как можно устранить проблемы и восстановить доступ.

## <a name="supported-platforms"></a>Поддерживаемые платформы  

При регистрации в Intune для Wandera поддерживаются следующие платформы:

- Android 5.0 и более поздние версии  
- iOS 10.2 и более поздних версий.  

Дополнительные сведения о платформах и устройствах см. на [веб-сайте Wandera](https://www.wandera.com/mobile-threat-defense/).

## <a name="prerequisites"></a>Предварительные условия  

- Подписка на Microsoft Intune  
- Azure Active Directory  
- Wandera Mobile Threat Defense (прежнее название: Wandera Secure)  

Дополнительные сведения см. на странице [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Примеры сценариев

Ниже приведены распространенные сценарии при использовании Wandera MTD с Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений  

При обнаружении на устройствах вредоносного ПО можно заблокировать использование основных приложений на устройствах, пока угроза не будет устранена. Такая блокировка охватывает:  
- Подключение к корпоративной электронной почте  
- Синхронизация корпоративных файлов с помощью приложения OneDrive для работы  
- Доступ к приложениям организации  

**Блокировка при обнаружении вредоносных программ**:

![Схематическое изображение обнаруженных вредоносных приложений](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Доступ предоставляется после устранения угрозы**: 

![Схематическое изображение предоставления доступа после устранения угрозы](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основе угроз для сети  

Выявляйте сетевые угрозы, такие как атаки "злоумышленник в середине", и защищайте доступ к сети Wi-Fi на основе сведений о рисках, связанных с устройствами.  

**Блокировка доступа к сети через Wi-Fi**:  

![Блокировка доступа к сети через Wi-Fi](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Доступ предоставляется после устранения угрозы**:  

![Восстановление доступа после исправления](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основе оценки угроз для сети

Обнаруживайте угрозы для сети, такие как атаки типа "злоумышленник в середине", и запрещайте синхронизацию корпоративных файлов на основе риска устройства.

**Блокировка SharePoint Online при обнаружении сетевых угроз**:  

![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Доступ предоставляется после устранения угрозы**:  

![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция Wandera с Intune](wandera-mtd-connector-integration.md)
- [Настройка приложений Wandera](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Создание политики соответствия устройств Wandera](mtd-device-compliance-policy-create.md)
- [Включение соединителя Wandera MTD](mtd-connector-enable.md)
