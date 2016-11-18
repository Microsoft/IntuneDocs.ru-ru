---
title: "Управление корпоративными устройствами | Microsoft Intune"
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
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 7577cbab528d88635e8551bf8de1ffd49becaa84


---

# <a name="enroll-corporateowned-devices-by-using-intune"></a>Регистрация корпоративных устройств с помощью Intune

Корпоративные устройства можно регистрировать для управления с помощью Intune различными способами в зависимости от типа устройства, способа его приобретения и потребностей организации. Для регистрации корпоративных устройств и управления ими, например при использовании сценария "Принеси свое устройство" (BYOD) можно также установить приложение корпоративного портала.

## <a name="enroll-corporateowned-ios-devices"></a>Регистрация корпоративных устройств iOS

При использовании сценариев "Выбери свое устройство" (CYOD) рекомендуется использовать методы регистрации корпоративных устройств. В среде CYOD организация оплачивает выбранное пользователем устройство, а управляет этим устройством организация.

Если пользователям на выбор предлагаются устройства iOS, регистрацию можно предварительно настроить таким образом, чтобы служба Intune управляла устройством с момента его включения пользователем. Служба Intune поддерживает регистрацию устройств с помощью [ программы регистрации устройств Apple (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) или средства Apple Configurator на компьютере Mac для [прямой](ios-direct-enrollment-in-microsoft-intune.md) регистрации или регистрации с использованием [помощника по настройке](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Изучите дополнительные сведения о [регистрации корпоративных устройств iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Создание учетной записи диспетчера регистрации устройств

Для управления многочисленными мобильными устройствами организации можно создать учетную запись диспетчера регистрации устройств с одним пользователем. Когда учетная запись диспетчера регистрации устройств будет создана, назначенный менеджер сможет зарегистрировать более 15 устройств для регистрации обычными пользователями.

Учетная запись диспетчера регистрации устройств позволяет регистрировать только устройства, которые не используются отдельным, конкретным пользователем. Эти типы устройств хорошо подходят для приложений в сфере розничной торговли или коммунального обслуживания, но являются неприемлемым вариантом для доступа к электронной почте или корпоративным ресурсам.

Изучите дополнительные сведения о [регистрации корпоративных устройств с помощью учетной записи диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporateowned-windows-10-enterprise-devices"></a>Регистрация корпоративных устройств с Windows 10 Корпоративная

Если в организации используется Azure Active Directory Premium или Microsoft Enterprise Mobility Suite, вы можете [регистрировать устройства с Windows 10 Корпоративная](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Когда пользователь добавляет на устройство рабочую или учебную учетную, устройство автоматически помечается как "корпоративное".

## <a name="import-imei-numbers"></a>Импорт номеров IMEI

Многие производители мобильных устройств используют уникальные номера IMEI (международные идентификаторы мобильного оборудования). Вы можете импортировать номера IMEI для устройств, принадлежащих вашей организации. Когда устройство попадает под управление Intune, оно помечается как корпоративное.

Изучите дополнительные сведения о [маркировке корпоративных устройств с помощью номеров IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporateowned"></a>Обозначение устройства как корпоративного

В списке устройств параметр **Владение** имеет значение **Корпоративное**. Корпоративное устройство имеет одну из этих характеристик:

 - Устройство было [зарегистрировано с помощью учетной записи диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - Устройство было зарегистрировано с помощью [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) или [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md).
 - Изготовитель устройства [предописал его с помощью номера IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).
 - Устройство зарегистрировано в [Azure Active Directory или Enterprise Mobility Suite как устройство с Windows 10 Корпоративная](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).



<!--HONumber=Nov16_HO2-->


