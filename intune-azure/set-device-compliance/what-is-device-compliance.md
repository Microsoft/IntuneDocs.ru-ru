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
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b245dac28f88e7eab70dfa9d759b15e155f8a7df


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Что такое соответствие устройств в предварительной версии Intune Azure?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Для защиты корпоративных данных необходимо проследить за тем, чтобы устройства, используемые для доступа к корпоративным приложениям и данным, соответствовали определенным правилам. Эти правила могут включать использование ПИН-кода для доступа к устройствам и шифрование данных, хранящихся на устройствах. Набор таких правил называется **политикой соответствия**.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Как использовать политику соответствия устройств?
Политики соответствия можно использовать совместно с условным доступом для предоставления доступа к электронной почте и другим службам только тем устройствам, которые отвечают правилам политики соответствия.

Кроме того, политику соответствия можно использовать независимо от условного доступа.
При независимом использовании политики соответствия происходит оценка целевых устройств и вывод сведений о них с указанием состояния соответствия. Например, вы можете получить отчет о количестве незашифрованных устройств либо о количестве устройств со снятой защитой или с административным доступом. Однако если политики соответствия используются независимо друг от друга, доступ к корпоративным ресурсам не ограничивается.

Политика соответствия развертывается для пользователей. При развертывании политики соответствия для пользователя его устройства проверяются на соответствие. Дополнительные сведения о том, сколько времени требуется мобильным устройствам для получения политики после развертывания, см. в статье "Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune".

##  <a name="concepts"></a>Основные понятия
Ниже приведены некоторые термины и основные понятия, которые помогут вам разобраться, как использовать политики соответствия.

### <a name="compliance-requirements"></a>Требования соответствия
Требования соответствия — это такие правила, как требование шифрования или установки ПИН-кода устройства. Это правило можно указать, как обязательное или необязательное для политики соответствия.

<!---### Actions for noncompliance

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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Различия между классической консолью администрирования Intune и Intune на портале Azure


Если вы раньше использовали классическую консоль администрирования Intune, обратите внимание на различия, которые нужно учитывать при переходе на новый рабочий процесс соответствия устройств на портале Azure.


-   На портале Azure политики соответствия создаются отдельно для каждой поддерживаемой платформы. В консоли администрирования Intune одна политика соответствия была общей для всех поддерживаемых платформ.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Дальнейшие действия

[Get started with device compliance in Intune Azure preview](get-started-with-device-compliance.md) (Начало работы с соответствием устройств в предварительной версии Intune Azure)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO3-->


