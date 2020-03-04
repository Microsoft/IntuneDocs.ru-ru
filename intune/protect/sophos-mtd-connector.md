---
title: Использование Sophos Mobile с Intune
titleSuffix: Intune on Azure
description: Как использовать Sophos Mobile в Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств.
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
ms.openlocfilehash: 816968d512b73a8592c7a86b39c41057aa99e827
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782052"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Соединитель Sophos Mobile Threat Defense в Intune
Вы можете управлять доступом с мобильных устройств к корпоративным ресурсам, используя условный доступ на основе оценки рисков. Такую возможность дает вам Sophos Mobile — решение Mobile Threat Defense (MTD), интегрируемое с Microsoft Intune. Оценка рисков основана на телеметрии, собираемой с устройств с запущенным приложением Sophos Mobile.
Вы можете настроить политики условного доступа на основе оценки рисков Sophos Mobile, реализуемой с помощью политик соответствия устройств Intune. Эти политики также позволяют разрешать или блокировать доступ к корпоративным ресурсам с устройств, не соответствующих требованиям в зависимости от обнаруженных угроз.

> [!NOTE]
> Этот поставщик защиты от мобильных угроз не поддерживается для незарегистрированных устройств.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Как Intune и Sophos Mobile помогают защитить ресурсы вашей организации?
Приложение Sophos Mobile для Android или iOS/iPadOS регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройств и приложений (при наличии), и отправляет их в облачную службу Sophos Mobile для оценки риска в отношении угроз для мобильного устройства.
Политика соответствия устройств Intune включает правило Sophos Mobile Threat Defense, основанное на оценке рисков Sophos Mobile. При включении этого правила Intune оценивает соответствие устройства заданной политике. Если устройство определяется как несоответствующее, его доступ к таким ресурсам, как Exchange Online и SharePoint Online, блокируется. Пользователи также получают от приложения Sophos Mobile, установленного на устройстве, рекомендации по устранению проблемы и восстановлению доступа к корпоративным ресурсам.  

## <a name="sample-scenarios"></a>Примеры сценариев
Далее приведены некоторые распространенные сценарии.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Управление доступом на основании оценки угроз от вредоносных приложений
При обнаружении на устройствах вредоносного ПО можно заблокировать следующие действия до устранения угрозы:
- Подключение к корпоративной электронной почте
- Синхронизация корпоративных файлов с помощью приложения OneDrive для работы
- Доступ к приложениям организации

**Блокировка при обнаружении вредоносных программ**:
 
![Схематическое изображение обнаруженных вредоносных приложений](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Доступ предоставляется после устранения угрозы**:  
![Схематическое изображение предоставления доступа после устранения угрозы](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Управление доступом на основе угроз для сети  
Обнаружение угроз для вашей сети, таких как атаки злоумышленник в середине, и защита доступа к сети Wi-Fi на основе рисков, связанных с устройствами.  

**Блокировка доступа к сети через Wi-Fi**:  
![Блокировка доступа к сети через Wi-Fi](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Доступ предоставляется после устранения угрозы**:   
![Доступ предоставляется после устранения угрозы](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Управление доступом к SharePoint Online на основе оценки угроз для сети  
Обнаружение угроз для вашей сети, таких как атаки злоумышленник в середине, и блокирование синхронизации корпоративных файлов на основании риска для устройства.  

**Блокировка SharePoint Online при обнаружении сетевых угроз**:   
![Блокировка SharePoint Online при обнаружении сетевых угроз](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Доступ предоставляется после устранения угрозы**:  
![Пример предоставления доступа к Sharepoint после устранения угрозы](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Поддерживаемые платформы  
- Android 5.0 и более поздние версии
- iOS 11.0 и более поздние версии

## <a name="prerequisites"></a>Предварительные условия  
- Azure Active Directory Premium
- Подписка на Microsoft Intune 
- Подписка на Sophos Mobile Threat Defense

Дополнительные сведения см. на [веб-сайте Sophos](https://www.sophos.com/en-us/products/mobile-control.aspx).

## <a name="next-steps"></a>Дальнейшие шаги  
- [Интеграция Sophos с Intune](sophos-mtd-connector-integration.md)
- [Настройка приложений Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Создание политики соответствия устройств Sophos](mtd-device-compliance-policy-create.md)
- [Включение соединителя Sophos MTD](mtd-connector-enable.md)
