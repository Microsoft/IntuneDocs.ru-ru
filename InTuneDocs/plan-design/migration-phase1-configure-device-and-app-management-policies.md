---
title: "Настройка политик соответствия устройств и управления приложениями во время миграции Intune | Документация Майкрософт"
description: "В этой статье представлена процедура настройки политик соответствия устройств и управления приложениями во время миграции Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 5904b117ccab9046d2afde4a761b4724431a6302
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Этап 1. Настройка политик соответствия устройств и управления приложениями

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

При миграции в Intune важнее всего зарегистрировать все устройства и обеспечить их соответствие политикам. С помощью политик устройств можно управлять корпоративными устройствами для одного пользователя, личными (BYOD) и общими устройствами, такими как киоски, POS-компьютеры, планшеты, которые используют несколько студентов в аудитории или устройства без пользователя (только iOS).

На каждой платформе устройств предусмотрены собственные параметры, но политики устройств Intune совместимы со всеми платформами устройств благодаря следующим возможностям управления мобильными устройствами:

-   Регулирование количества устройств, которые регистрирует каждый пользователь.

-   Управление параметрами устройств (например, шифрование на уровне устройства, длина пароля, использование камеры).

-   Предоставление приложений, профилей электронной почты и VPN.

-   Оценки критериев уровня устройства для политик соответствия требованиям безопасности.

> [!IMPORTANT]
> Политики управления устройствами назначаются группам пользователей, а не отдельным устройствам или пользователям. Политики можно применить к группе пользователей, а затем и к устройству пользователя или к группе устройств, а затем к участникам группы.

## <a name="task-list-for-device-compliance-policies"></a>Список задач для политик соответствия устройств

### <a name="task-1-add-device-groups-optional"></a>Задача 1. Добавление групп устройств (необязательно)

[Классический портал Intune](https://manage.microsoft.com/) позволяет создавать группы устройств для выполнения различных задач администрирования на основе удостоверения устройства, а не удостоверения пользователя.

Группы устройств подходят для управления устройствами без выделенных пользователей, такими как устройства, используемые в режиме киоска, устройства, которые совместно используют вахтовые рабочие, или устройства, назначенные определенному расположению.

Настроив группы устройств до регистрации устройства, вы можете использовать категории устройств для автоматической группировки устройств при регистрации, чтобы автоматически получать политики устройств для групп.

-   Узнайте, [как добавлять группы устройств](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5).

-   Узнайте, [как настроить категории устройств](https://docs.microsoft.com/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Задача 2. Использование профилей доступа к ресурсам (сертификаты Wi-Fi, VPN и электронной почты)

Профили доступа к ресурсам подготавливают сертификаты и конфигурации доступа к зарегистрированным устройствам.

Как уже было сказано в разделе об оценке требований к MDM, для развертывания сертификатов VPN, Wi-Fi и электронной почты (при использовании проверки подлинности на основе сертификатов) необходимо настроить [инфраструктуру PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles).

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Прямой импорт профилей доступа к ресурсам (необязательно)

Если в решении MDM предусмотрен механизм экспорта профилей электронной почты, Wi-Fi и VPN в формат XML, вы можете использовать XML-файл и просто импортировать его в Intune с помощью OMA-URI, чтобы создать пользовательские профили на устройствах с iOS, Android и Windows.

-   Узнайте, как можно добавить пользовательскую политику для устройств с [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune), [Android](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune) и [Windows](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Задача 3. Создание и развертывание профилей конфигурации устройства

Вам нужно создать профиль конфигурации устройства, чтобы применить параметры уровня устройства, например отключение камеры, магазин приложений, настройка режима использования одного приложения, начальный экран и т. д.

- Узнайте о [профилях конфигурации устройств](https://docs.microsoft.com/intune-azure/configure-devices/how-to-create-device-profiles).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Прямой импорт политики конфигурации iOS (необязательно)

-   **Профили iOS Apple Configurator (iOS 7.1 и более поздних версий).** Если имеющееся решение MDM использует профили Apple Configurator (MOBILECONFIG-файлы), Intune может импортировать их напрямую как пользовательские политики конфигурации.

-   **Политики конфигурации мобильных приложений iOS.** Если имеющееся решение MDM использует политики конфигурации мобильных приложений iOS, Intune может импортировать их напрямую при условии соответствия формату XML, заданному в списке свойств Apple.

- Узнайте, как можно добавить пользовательскую политику для [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Задача 4. Создание и развертывание политик соответствия устройств (необязательно)

Политики соответствия устройств оценивают параметры безопасности и позволяют получить отчеты о соответствии устройств корпоративным стандартам. Политики соответствия устройств оценивают следующие факторы безопасности:

-   Длина ПИН-кода

-   состояние снятой защиты;

-   Версия ОС

Дополнительные сведения о параметрах соответствия устройств см. в следующих ресурсах.

-   Узнайте о [политиках соответствия устройств](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Узнайте, [как создавать политики соответствия устройств](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Задача 5. Публикация и развертывание приложений

Используя Intune MDM, вы можете подготовить приложения. Для этого можно задать требование их автоматической установки или сделать их доступными на корпоративном портале.

-   Узнайте, [как добавлять приложения](https://docs.microsoft.com/intune/deploy-use/add-apps).

-   Узнайте, [как развертывать приложения](https://docs.microsoft.com/intune/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Задача 6. Обеспечение регистрации устройств

При регистрации управление осуществляется за счет подготовки контроля над устройством.

-   Узнайте, [как подготовиться к регистрации корпоративных и личных пользовательских устройств](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

-   Узнайте, [как регистрировать корпоративные устройства](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices).

Если необходимо зарегистрировать общее устройство или устройство без пользователя, вы можете использовать [учетную запись диспетчера регистрации устройств (DEM)](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>Дальнейшие действия 

[Этап 1. Настройка политик защиты приложений (необязательно)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

