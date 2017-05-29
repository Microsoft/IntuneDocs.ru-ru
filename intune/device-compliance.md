---
title: "Соответствие устройства"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: из этой статьи вы узнаете о соответствии устройств в Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2aec7463b9a2b3bdaa78281fca0bbb39dcd3f884
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Что такое соответствие устройств в предварительной версии Intune Azure?

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Политики соответствия устройств Intune определяют правила и параметры, которым должно соответствовать устройство, чтобы оно рассматривалось как совместимое согласно политикам условного доступа Intune и EMS. Политики соответствия устройств можно также использовать для отслеживания и устранения проблем совместимости у устройств. 

В их число могут входить следующие правила.

- Использование пароля для доступа к устройствам
- Шифрование
- Снята ли на устройстве защита или имеется ли административный доступ
- Минимально допустимая версия ОС
- Максимально допустимая версия ОС
- Должно ли устройство находиться на уровне защиты мобильных устройств от угроз или ниже этого уровня

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Как использовать политику соответствия устройств?

### <a name="using-ems-conditional-access"></a>Использование условного доступа EMS
Политику соответствия можно использовать совместно с условным доступом EMS для предоставления доступа к электронной почте и другим корпоративным ресурсам только тем устройствам, которые отвечают определенным правилам политики соответствия.

### <a name="not-using-ems-conditional-access"></a>Неиспользование условного доступа EMS
Кроме того, политики соответствия устройств можно использовать независимо от условного доступа EMS.
При независимом использовании политики соответствия происходит оценка целевых устройств и вывод сведений о них с указанием состояния соответствия. Например, вы можете получить отчет о количестве незашифрованных устройств либо о количестве устройств со снятой защитой или с административным доступом. Однако если политики соответствия используются независимо друг от друга, доступ к корпоративным ресурсам не ограничивается.

Политика соответствия развертывается для пользователей. При развертывании политики соответствия для пользователя его устройства проверяются на соответствие. Дополнительные сведения о том, сколько времени требуется мобильным устройствам для получения политики после развертывания, см. в статье "Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune".

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Разница между классической консолью администрирования Intune и порталом предварительной версии Intune Azure

Если вы используете классическую консоль администрирования Intune, обратите внимание на различия, которые нужно учитывать при переходе на новый рабочий процесс с политиками соответствия устройств на портале Azure.

-   На портале Azure политики соответствия создаются отдельно для каждой поддерживаемой платформы. В консоли администрирования Intune одна политика соответствия была общей для всех поддерживаемых платформ.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Миграция с классической консоли Intune на портал предварительной версии Azure Intune

Политики соответствия устройства, созданные в [классической консоли Intune](https://manage.microsoft.com), не будут отображаться на новом [портале Intune Azure](https://portal.azure.com). Тем не менее они будут по-прежнему назначаться пользователям, а управление ими будет осуществляться через классическую консоль Intune.

Если вы хотите воспользоваться новыми возможностями соответствия устройств на портале Intune Azure, на нем необходимо создать политики соответствия устройств. Если пользователю, которому назначена политика соответствия устройств на классическом портале Intune, назначить новую политику соответствия устройств на портале Intune Azure, последняя будет иметь более высокий приоритет, чем созданная в классической консоли Intune.

##  <a name="next-steps"></a>Дальнейшие действия

[Общие сведения о политиках соответствия устройств](device-compliance-get-started.md)


<!---### See also

Conditional access--->

