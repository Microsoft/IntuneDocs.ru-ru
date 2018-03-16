---
title: "Политики соответствия устройств Microsoft Intune"
titleSuffix: 
description: "Сведения о соответствии устройств в Microsoft Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb3ec168844708d80c83909ab6c58a52ca62e53c
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
# <a name="get-started-with-microsoft-intune-device-compliance-policies"></a>Начало работы с политиками соответствия устройств Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Политики соответствия устройств Intune определяют правила и параметры, которым должно соответствовать устройство, чтобы программа Intune расценивала его как соответствующее.

В их число могут входить следующие правила.

- Использование пароля для доступа к устройствам

- Encryption

- Снята ли на устройстве защита или имеется ли административный доступ

- Минимально допустимая версия ОС

- Максимально допустимая версия ОС

- Должно ли устройство находиться на уровне защиты мобильных устройств от угроз или ниже этого уровня

Вы также можете использовать политики соответствия для отслеживания состояния соответствия на устройствах.

## <a name="device-compliance-requirements"></a>Требования соответствия устройств

Требования соответствия — это такие правила, как требование шифрования или установки ПИН-кода устройства. Это правило можно указать, как обязательное или необязательное для политики соответствия.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

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

- Intune

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

Когда устройство регистрируется в Intune, происходит регистрация в Azure AD, при которой в атрибуты устройства в Azure AD добавляется дополнительная информация. Один из основных параметров устройства — его состояние соответствия, которое используется политиками условного доступа для запрета или разрешения доступа к электронной почте и другим корпоративным ресурсам.

- См. дополнительные сведения о [процессе регистрации Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Назначение итогового состояния для профиля конфигурации устройства

Если устройству назначено несколько профилей конфигурации, по крайней мере два из которых имеют разные состояния соответствия, необходимо назначить одно итоговое состояние соответствия. Назначение производится на основе концептуального уровня серьезности, задаваемого для каждого состояния соответствия. Ниже указаны уровни серьезности для каждого состояния соответствия.


|Состояние  |Статус  |
|---------|---------|
|Pending     |1|
|успешно     |2|
|Failed     |3|
|Ошибка     |4|

Итоговое состояние для двух или более профилей конфигурации назначается путем выбора наивысшего уровня серьезности всех профилей, назначенных устройству.

Допустим, устройству назначено три профиля: один с состоянием "Ожидается" (серьезность = 1), один с состоянием "Успешно" (серьезность = 2) и один с состоянием "Ошибка" (серьезность = 4). Состояние "Ошибка" имеет наивысший уровень серьезности, поэтому оно назначается как итоговое состояние соответствия для всех трех профилей.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>Назначение состояния InGracePeriod для заданной политики соответствия требованиям

Состояние InGracePeriod для политики соответствия требованиям — это значение, которое определяется на основе периода отсрочки для устройства и фактического состояния устройства, связанного с назначенной политикой соответствия требованиям. 

В частности, если устройство имеет состояние NonCompliant для назначенной политики соответствия требованиям и:

- устройству не назначен период отсрочки, для политики соответствия требованиям задается значение NonCompliant;
- устройство имеет период отсрочки, который истек, для политики соответствия требованиям задается значение NonCompliant;
- устройство имеет период отсрочки, который находится в будущем, для политики соответствия требованиям задается значение InGracePeriod.

В таблице ниже обобщаются описанные выше особенности.


|Фактическое состояние соответствия|Значение назначенного периода отсрочки|Действующее состояние соответствия|
|---------|---------|---------|
|NonCompliant |Период отсрочки не назначен |NonCompliant |
|NonCompliant |Вчерашняя дата|NonCompliant|
|NonCompliant |Завтрашняя дата|InGracePeriod|

Дополнительные сведения об отслеживании политик соответствия устройств см. в статье [Мониторинг политик соответствия устройств Intune](compliance-policy-monitor.md).

### <a name="assigning-a-resulting-compliance-policy-status"></a>Назначение итогового состояния для политики соответствия требованиям

Если устройству назначено несколько политик соответствия требованиям, по крайней мере две из которых имеют разные состояния соответствия, необходимо назначить одно итоговое состояние соответствия. Назначение производится на основе концептуального уровня серьезности, задаваемого для каждого состояния соответствия. Ниже указаны уровни серьезности для каждого состояния соответствия. 

|Состояние  |Статус  |
|---------|---------|
|Неизвестно     |1|
|NotApplicable     |2|
|Соответствие|3|
|InGracePeriod|4|
|NonCompliant|5|
|Ошибка|6|

Итоговое состояние для двух или более политик соответствия требованиям определяется путем выбора наивысшего уровня серьезности всех политик, назначенных устройству.
 
Допустим, устройству назначено три политики соответствия требованиям: одна с состоянием Unknown (серьезность = 1), одна с состоянием Compliant (серьезность = 3) и одна с состоянием InGracePeriod (серьезность = 4). Состояние InGracePeriod имеет наивысший уровень серьезности, поэтому оно назначается как итоговое состояние соответствия для всех трех политик.  

##  <a name="ways-to-use-device-compliance-policies"></a>Способы использования политик соответствия устройств

### <a name="with-conditional-access"></a>С условным доступом
Политику соответствия с условным доступом можно использовать для предоставления доступа к электронной почте и другим корпоративным ресурсам только тем устройствам, которые отвечают определенным правилам политики.

### <a name="without-conditional-access"></a>Без условного доступа
Политики соответствия устройств также можно использовать независимо от условного доступа. При независимом использовании политики соответствия происходит оценка целевых устройств и вывод сведений о них с указанием состояния соответствия. Например, вы можете получить отчет о количестве незашифрованных устройств либо о количестве устройств со снятой защитой или с административным доступом. Однако если политики соответствия используются независимо друг от друга, доступ к корпоративным ресурсам не ограничивается.

Политика соответствия развертывается для пользователей. При развертывании политики соответствия для пользователя его устройства проверяются на соответствие. Дополнительные сведения о том, сколько времени требуется мобильным устройствам для получения политики после ее развертывания, см. в разделе [Устранение неполадок с профилями устройств в Microsoft Intune](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

#### <a name="actions-for-non-compliance"></a>Действия при несоответствии

Действия при несоответствии позволяют настроить упорядоченную по времени последовательность действий, которые применяются к устройствам, не соответствующим критериям политики соответствия требованиям. Дополнительные сведения см. в разделе [Автоматические действия при несоответствии](actions-for-noncompliance.md).

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Использование политик соответствия устройств: классический портал Intune и портал Azure;

Обратите внимание на основные отличия — это поможет вам перейти на новый процесс работы с политиками соответствия устройств на портале Azure.

- На портале Azure политики соответствия создаются отдельно для каждой поддерживаемой платформы.
- На классическом портале Intune для всех поддерживаемых платформ использовалась одна общая политика соответствия устройств.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Перенос политик соответствия устройств с классического портала Intune на портал Azure

Политики соответствия устройств, созданные на [классическом портале Intune](https://manage.microsoft.com), не отображаются на новом [портале Azure для Intune](https://portal.azure.com). Но их по-прежнему можно будет назначать пользователям и контролировать с классического портале Intune.

Если вы хотите воспользоваться новыми возможностями портала Azure в этой области, вам нужно будет создать политики соответствия устройств уже на нем. Если пользователю, которому назначена политика соответствия устройств на классическом портале Intune, назначить новую политику соответствия устройств на портале Azure, последняя будет иметь более высокий приоритет, чем созданная на классическом портале Intune.

##  <a name="next-steps"></a>Дальнейшие шаги

- Создайте политику соответствия устройств для следующих платформ.

   - [Android](compliance-policy-create-android.md)
   - [Android for Work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Сведения о сущностях политики для хранилища данных Intune см. в статье [Справочник по сущностям политики](reports-ref-policy.md).
