---
title: "Политики соответствия устройств Intune"
titleSuffix: Azure portal
description: "Из этой статьи вы узнаете о соответствии устройств в Microsoft Intune\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa78383233950e342c5ab0f83095bba3c8fda1f9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Начало работы с политиками соответствия устройств Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Что такое соответствие устройств в Intune?

Политики соответствия устройств Intune определяют правила и параметры, которым должно соответствовать устройство, чтобы программа Intune расценивала его как соответствующее.

В их число могут входить следующие правила.

- Использование пароля для доступа к устройствам

- Шифрование

- Снята ли на устройстве защита или имеется ли административный доступ

- Минимально допустимая версия ОС

- Максимально допустимая версия ОС

- Должно ли устройство находиться на уровне защиты мобильных устройств от угроз или ниже этого уровня

Вы также можете использовать политики соответствия для отслеживания состояния соответствия на устройствах.

### <a name="device-compliance-requirements"></a>Требования соответствия устройств

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

##  <a name="pre-requisites"></a>Предварительные условия

Чтобы использовать политики соответствия устройств в Intune, необходимы следующие подписки.

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Поддерживаемые платформы:

-   Android

-   iOS

-   macOS (предварительная версия)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Для отправки своего состояния соответствия устройства должны быть зарегистрированы в Intune.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Политики соответствия устройств Intune в Azure AD

Когда устройство регистрируется в Intune, происходит регистрация в Azure AD, при которой в атрибуты устройства в Azure AD добавляется дополнительная информация. Один из основных параметров устройства — его состояние соответствия, которое используется политиками условного доступа для запрета или разрешения доступа к электронной почте и другим корпоративным ресурсам.

- См. дополнительные сведения о [процессе регистрации Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Способы использования политик соответствия устройств

### <a name="with-conditional-access"></a>С условным доступом
Политику соответствия с условным доступом можно использовать для предоставления доступа к электронной почте и другим корпоративным ресурсам только тем устройствам, которые отвечают определенным правилам политики.

### <a name="without-conditional-access"></a>Без условного доступа
Политики соответствия устройств также можно использовать независимо от условного доступа. При независимом использовании политики соответствия происходит оценка целевых устройств и вывод сведений о них с указанием состояния соответствия. Например, вы можете получить отчет о количестве незашифрованных устройств либо о количестве устройств со снятой защитой или с административным доступом. Однако если политики соответствия используются независимо друг от друга, доступ к корпоративным ресурсам не ограничивается.

Политика соответствия развертывается для пользователей. При развертывании политики соответствия для пользователя его устройства проверяются на соответствие. Дополнительные сведения о том, сколько времени требуется мобильным устройствам для получения политики после развертывания, см. в статье "Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune".

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Использование политик соответствия устройств: классический портал Intune и портал Azure;

Обратите внимание на основные отличия — это поможет вам перейти на новый процесс работы с политиками соответствия устройств на портале Azure.

- На портале Azure политики соответствия создаются отдельно для каждой поддерживаемой платформы.
- На классическом портале Intune для всех поддерживаемых платформ использовалась одна общая политика соответствия устройств.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Перенос политик соответствия устройств с классического портала Intune на портал Azure

Политики соответствия устройств, созданные на [классическом портале Intune](https://manage.microsoft.com), не появятся на новом [портале Azure для Intune](https://portal.azure.com). Но их по-прежнему можно будет назначать пользователям и контролировать с классического портале Intune.

Если вы хотите воспользоваться новыми возможностями портала Azure в этой области, вам нужно будет создать политики соответствия устройств уже на нем. Если пользователю, которому назначена политика соответствия устройств на классическом портале Intune, назначить новую политику соответствия устройств на портале Azure, последняя будет иметь более высокий приоритет, чем созданная на классическом портале Intune.

##  <a name="next-steps"></a>Дальнейшие действия

Создайте политику соответствия устройств для следующих платформ.

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
