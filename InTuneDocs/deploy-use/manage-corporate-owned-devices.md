---
title: "Управление корпоративными устройствами | Документы Майкрософт"
description: "Регистрация корпоративных устройств различными способами в зависимости от типа устройства, способа его покупки и потребностей организации."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 58270feb34185441406abc15e1f889c2924722e8


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Регистрация корпоративных устройств с помощью Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Корпоративные устройства можно регистрировать для управления с помощью Intune различными способами в зависимости от типа устройства, способа его приобретения и потребностей организации. Для регистрации корпоративных устройств и управления ими, например при использовании сценария "Принеси свое устройство" (BYOD) можно также установить приложение корпоративного портала.

## <a name="enroll-corporate-owned-ios-devices"></a>Регистрация корпоративных устройств iOS

При использовании сценариев "Выбери свое устройство" (CYOD) рекомендуется использовать методы регистрации корпоративных устройств. В среде CYOD организация оплачивает выбранное пользователем устройство, а управляет этим устройством организация.

Если пользователям на выбор предлагаются устройства iOS, регистрацию можно предварительно настроить таким образом, чтобы служба Intune управляла устройством с момента его включения пользователем. Служба Intune поддерживает регистрацию устройств с помощью [ программы регистрации устройств Apple (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) или средства Apple Configurator на компьютере Mac для [прямой](ios-direct-enrollment-in-microsoft-intune.md) регистрации или регистрации с использованием [помощника по настройке](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Изучите дополнительные сведения о [регистрации корпоративных устройств iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Создание учетной записи диспетчера регистрации устройств

Для управления многочисленными мобильными устройствами организации можно создать учетную запись диспетчера регистрации устройств с одним пользователем. Когда учетная запись диспетчера регистрации устройств будет создана, назначенный менеджер сможет зарегистрировать более 15 устройств для регистрации обычными пользователями.

Учетная запись диспетчера регистрации устройств позволяет регистрировать только устройства, которые не используются отдельным, конкретным пользователем. Эти типы устройств хорошо подходят для приложений в сфере розничной торговли или коммунального обслуживания, но являются неприемлемым вариантом для доступа к электронной почте или корпоративным ресурсам.

Изучите дополнительные сведения о [регистрации корпоративных устройств с помощью учетной записи диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Регистрация корпоративных устройств с Windows 10 Корпоративная

Если в организации используется Azure Active Directory Premium или Microsoft Enterprise Mobility Suite, вы можете [регистрировать устройства с Windows 10 Корпоративная](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Когда пользователь добавляет на устройство рабочую или учебную учетную, устройство автоматически помечается как "корпоративное".

## <a name="import-imei-numbers"></a>Импорт номеров IMEI

Многие производители мобильных устройств используют уникальные номера IMEI (международные идентификаторы мобильного оборудования). Вы можете импортировать номера IMEI для устройств, принадлежащих вашей организации. Когда устройство попадает под управление Intune, оно помечается как корпоративное.

Изучите дополнительные сведения о [маркировке корпоративных устройств с помощью номеров IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Обозначение устройства как корпоративного

Intune распознает устройство как "корпоративное", если выполняется одно из следующих условий.

 - Устройство было [зарегистрировано с помощью учетной записи диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (все платформы).
 - Устройство было зарегистрировано с помощью [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) или [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (только iOS).
 - Изготовитель устройства [предварительно объявил его с помощью номера IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (все платформы с номерами IMEI).
 - Устройство зарегистрировано в [Azure Active Directory или Enterprise Mobility Suite как устройство с Windows 10 Корпоративная](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (только Windows 10).

Когда устройство помечено как корпоративное, в столбце **Тип собственности** для записи этого устройства в консоли администрирования отображается значение **Корпоративное**. 



<!--HONumber=Dec16_HO2-->


