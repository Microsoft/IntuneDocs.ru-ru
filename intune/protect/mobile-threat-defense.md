---
title: Служба защиты мобильных устройств от угроз в Microsoft Intune
titleSuffix: Microsoft Intune
description: Используйте Intune Mobile Threat Defense (MTD) с партнером MTD для защиты доступа к корпоративным ресурсам на основе риска для устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4abc35b625b9aa072e38c02d2fc4160faa916fb3
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72785727"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Что такое интеграция службы защиты мобильных устройств от угроз с Intune?
Intune может интегрировать данные из поставщика Mobile Threat Defense в виде источника информации для политик соответствия устройств и правил условного доступа устройств. Эти сведения можно использовать для защиты корпоративных ресурсов, таких как Exchange и SharePoint, путем блокировки доступа со скомпрометированных мобильных устройств.

Intune может использовать эти же данные в качестве источника для незарегистрированных устройств с помощью политик защиты приложений Intune. Таким образом, администраторы могут использовать эти сведения для защиты корпоративных данных в [защищенных Microsoft Intune приложениях](~/apps/apps-supported-intune-apps.md), а также применять блокировку или выборочную очистку.

## <a name="what-problem-does-this-solve"></a>Какие проблемы это решает?
Интеграция информации из поставщика Mobile Threat Defense поможет защитить корпоративные ресурсы от угроз, нацеленных на мобильные платформы.  

Как правило, организации действуют с упреждением, когда дело касается защиты компьютеров от уязвимостей и атак, однако при этом не уделяют должного внимания мониторингу и защите мобильных устройств. Несмотря на то, что мобильные платформы имеют встроенную защиту, такую как изоляция приложений и проверка приложений для пользователей в магазинах, они остаются уязвимыми для более сложных атак. Сейчас все больше сотрудников используют устройства для работы и доступа к конфиденциальной информации, поэтому данные из поставщика Mobile Threat Defense помогут защитить устройства и ресурсы от постоянно совершенствующихся атак.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Как работают соединители Intune Mobile Threat Defense?

Соединитель Mobile Threat Defense в Intune защищает ресурсы компании, создавая канал связи между Intune и выбранным поставщиком Mobile Threat Defense. Партнеры Intune Mobile Threat Defense предлагают интуитивно понятные, простые в развертывании приложения для мобильных устройств. Эти приложения активно сканируют и анализируют сведения об угрозах в Intune. Intune может использовать эти данные для формирования отчетов или применения правил и политик.  

Пример. Подключенное приложение Mobile Threat Defense сообщает поставщику Mobile Threat Defense о том, что определенный телефон в вашей сети в настоящее время подключен к сети, которая уязвима для атак "злоумышленник в середине". Эта информация оценивается по уровню риска (низкий, средний или высокий). Затем этот уровень сравнивается с допусками, настроенными для уровня риска в Intune. Это позволяет определить, следует ли отозвать доступ к определенным ресурсам, если устройство скомпрометировано.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Какие данные Intune собирает для приложения Mobile Threat Defense?

Если эта возможность включена, Intune собирает данные о перечне приложений с личных и корпоративных устройств и предоставляет к ним доступ поставщикам Mobile Thread Defense (MTD), например Lookout for Work. Вы можете собирать данные об инвентаризации приложений у пользователей устройств iOS.

Эта служба работает по явному согласию; по умолчанию никакие данные об инвентаризации приложений не предоставляются для общего доступа. Администратор Intune должен включить **синхронизацию приложений для устройств с iOS** в параметрах соединителя Mobile Threat Defense, прежде чем начнется обмен данными об инвентаризации приложений.

**Перечень приложений**  
Если включить синхронизацию приложений для устройств iOS, данные об инвентаризации приложений с корпоративных и личных устройств iOS отправляются поставщику услуг MTD. Перечень приложений содержит следующие данные:

- ИД приложения;
- версия приложения;
- короткая версия приложения;
- имя приложения;
- размер пакета приложения;
- динамический размер приложения;
- приложение проверено или нет;
- приложение управляется или нет.

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Примеры сценариев для зарегистрированных устройств с использованием политик соответствия устройств

Если решение Mobile Threat Defense определяет, что устройство заражено:

![Изображение с зараженным устройством в Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-1.png)

Доступ предоставляется после того, как устройство будет исправлено:

![Изображение с предоставленным доступом в Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Примеры сценариев для незарегистрированных устройств с использованием политик защиты приложений Intune

Если решение Mobile Threat Defense определяет, что устройство заражено:<br>
![Изображение с зараженным устройством в Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-3.png)

Доступ предоставляется после того, как устройство будет исправлено:<br>
![Изображение с предоставленным доступом в Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE] 
> Использование нескольких поставщиков Mobile Threat Defense с Intune не поддерживается. Если включено несколько соединителей Mobile Threat Defense, будут установлены все приложения Mobile Threat Defense и все устройства будут проверены на наличие угроз.

## <a name="mobile-threat-defense-partners"></a>Партнеры Mobile Threat Defense

Узнайте, как защитить доступ к ресурсам компании на основе риска для устройства, сети и приложений:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
