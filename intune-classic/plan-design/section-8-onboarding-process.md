---
title: "Процесс адаптации Intune | Документы Майкрософт"
description: "Эта статья содержит все сведения, которые необходимо учитывать при адаптации чисто облачного решения Intune в своей среде."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 562e24af8058df56f1b952c82fefe62d38388ec3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="intune-implementation"></a>Внедрение Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

На этапе адаптации вы внедрите Intune в свою рабочую среду. Этот процесс состоит из установки и настройки Intune и внешних зависимостей (при необходимости) с учетом ваших [требований к вариантам использования](section-3-determine-use-case-requirements.md), рассмотренных в предыдущих разделах данного руководства.

Следующий раздел содержит обзор процесса внедрения Intune, включающего в себя требования и высокоуровневые задачи.

>[!TIP]
> Дополнительные сведения о процессе внедрения Intune см. в разделе [Дополнительные ресурсы](additional-resources.md).

## <a name="intune-requirements"></a>Требования для Intune

Ниже приведены основные требования к автономной версии Intune:

-   Подписка EMS/Intune

-   Подписка Office 365 (для приложений Office и приложений с управлением на основе политик MAM)

-   Сертификат APNs Apple (для включения управления платформой устройств iOS)

-   Azure AD Connect (для синхронизации службы каталогов)

-   Локальный соединитель Intune для Exchange (ЦС для локальной организации Exchange, если это необходимо)

-   Intune Certificate Connector (для развертывания сертификата SCEP, если это необходимо)

>[!TIP]
> Дополнительные сведения о требованиях к автономной версии Intune см. [здесь](/intune-classic/get-started/what-to-know-before-you-start-microsoft-intune).

## <a name="intune-implementation-process"></a>Процесс внедрения Intune

### <a name="overview-of-implementation-tasks"></a>Обзор задач внедрения

Ниже приведен обзор каждой из задач по внедрению Intune.

#### <a name="task-1-add-intune-subscription"></a>Задача 1. Добавление подписки Intune

Как указано в предыдущем разделе о требованиях, нужна подписка EMS или Intune. Если у вашей организации нет такой подписки, обратитесь в корпорацию Майкрософт или службу технической поддержки учетных записей Майкрософт и сообщите, что хотите приобрести Enterprise Mobility + Security (EMS) или Intune.

-   Дополнительные сведения о том, [как приобрести Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Задача 2. Подписка на Office 365

Этот шаг не является обязательным. Как указано в предыдущем разделе о требованиях, если планируется использовать Exchange Online и управлять мобильными приложениями Office с помощью политики MAM, нужна подписка Office 365. Если у вашей организации нет такой подписки, обратитесь в корпорацию Майкрософт или службу технической поддержки учетных записей Майкрософт и сообщите, что хотите приобрести Office 365.

-   Дополнительные сведения о том, [как приобрести Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Задача 3. Добавление групп пользователей в Azure AD

В зависимости от требований и сценариев вариантов использования для развертывания Intune вам может понадобиться добавить пользователей или группы безопасности в AD или AAD. Вам следует просмотреть текущих пользователей и группы безопасности в Active Directory или Azure Active Directory и определить, полностью ли они соответствуют вашим потребностям. Новые пользователи и группы безопасности наиболее часто добавляются в Active Directory и синхронизируются в Azure Active Directory через Azure AD Directory Connect.

-   Дополнительные сведения о том, [как добавить пользователей или групп в Intune](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Задача 4. Назначение пользовательских лицензий Intune и Office 365

Всем пользователям, на которых будет нацелено развертывание EMS/Intune и Office 365, потребуется назначить лицензию. Это можно сделать на портале Центра администрирования Office 365.

-   Дополнительные сведения о том, [как назначить лицензии Intune](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Задача 5. Задание центра управления мобильными устройствами в Intune

Перед началом установки, настройки, регистрации устройств и управления ими с помощью Intune следует задать Intune в качестве центра управления устройствами. Для выполнения этой задачи используется рабочая область администратора на портале администрирования Intune.

-   Дополнительные сведения о том, [как задать центр управления устройствами](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Задача 6. Включение платформ устройств

По умолчанию в консоли администрирования Intune включено большинство платформ устройств, за исключением устройств Apple (iOS и Mac). Прежде чем можно будет регистрировать устройства iOS в Intune и управлять ими, требуется включить эту платформу устройств. Включение платформы устройств iOS состоит из трех шагов: создание и скачивание сертификата APNs с последующей отправкой его в Intune.

-   Дополнительные сведения [о том, как настроить управление устройствами в iOS и Mac.]/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Задача 7. Добавление и развертывание политик условий

Microsoft Intune поддерживает добавление и развертывание политик условий. Для этого используется рабочая область политики на портале администрирования Intune. Добавьте нужные политики условий и разверните их в целевых группах с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о том, [как добавить и развернуть политики условий](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Задача 8. Добавление и развертывание политик конфигурации

Microsoft Intune поддерживает добавление и развертывание политик конфигурации двух типов — общих и настраиваемых. Для этого используется рабочая область политики на портале администрирования Intune. Добавьте нужные политики конфигурации и разверните их в целевых группах с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о том, [как добавить и развернуть политики конфигурации](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Задача 9. Добавление и развертывание профилей ресурсов

Microsoft Intune поддерживает профили электронной почты, Wi-Fi и VPN. Для добавления и развертывания этих профилей используется рабочая область политики на портале администрирования Intune. Добавьте нужные профили электронной почты, Wi-Fi и VPN и разверните их в целевых группах с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о том, [как обеспечить доступ к ресурсам организации с помощью Intune](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Задача 10. Добавление и развертывание приложений

Microsoft Intune поддерживает развертывание веб-приложений, бизнес-приложений и приложений, опубликованных в магазине. Кроме того, поддерживается управление приложениями с интегрированным пакетом SDK Intune путем их сопоставления с политиками MAM. Для добавления и развертывания приложений используется рабочая область приложения на портале администрирования Intune. Для добавления политик MAM используется рабочая область политики на портале администрирования Intune. Добавьте нужные приложения и разверните их в целевых группах с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о [добавлении и развертывании приложений](/intune-classic/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Задача 11. Добавление и развертывание политик соответствия

Microsoft Intune поддерживает политики соответствия требованиям. Для добавления и развертывания этих политик используется рабочая область политики на портале администрирования Intune. Добавьте нужные политики соответствия и разверните их в целевых группах с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о [политиках соответствия требованиям](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Задача 12. Включение политик условного доступа

Microsoft Intune поддерживает условный доступ для Exchange Online и локальной организации Exchange, SharePoint Online, Skype для бизнеса Online и Dynamics CRM Online. Для включения соответствующих политик используется рабочая область политики на портале администрирования Intune. Включите и настройте нужные политики условного доступа с учетом [требований и вариантов использования для развертывания Intune](section-3-determine-use-case-requirements.md).

-   Дополнительные сведения об [условном доступе](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Задача 13. Регистрация устройств

Intune поддерживает платформы настольных и мобильных устройств Windows, iOS, Mac OS, Android. Зарегистрируйте нужные платформы мобильных устройств с учетом требований и вариантов использования для развертывания Intune.

-   Дополнительные сведения о том, [как зарегистрировать устройства](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Для получения дополнительных сведений о процессе внедрения Intune ознакомьтесь с этим [модулем семинара по Intune в Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676).

## <a name="next-section"></a>Следующий раздел

В следующем разделе приведены рекомендации по [тестированию и проверке развертывания Intune](section-9-test-and-validation.md).

