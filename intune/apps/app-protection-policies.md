---
title: Создание и развертывание политик защиты приложений
titleSuffix: Microsoft Intune
description: В этой статье описывается, как создать и назначить политики защиты приложений (APP) в Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940389"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Как создать и назначить политики защиты приложений

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Сведения о создании и назначении политик защиты приложений в Microsoft Intune для пользователей. В этой статье также описывается, как вносить изменения в существующие политики.

## <a name="before-you-begin"></a>Подготовка к работе

Политики защиты приложений могут применяться к приложениям на устройствах, которыми управляет или не управляет Intune. Подробное описание использования политик защиты приложений, а также описание поддерживаемых этими политиками сценариев см. в разделе [Что такое политики защиты приложений Microsoft Intune?](app-protection-policy.md)

Список поддерживаемых приложений MAM см. в статье [Список приложений MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Сведения о добавлении бизнес-приложений вашей организации в Microsoft Intune и подготовке их к использованию политик защиты приложений см. в разделе [Добавление приложений в Microsoft Intune](apps-add.md).

## <a name="create-an-app-protection-policy"></a>Создание политики защиты приложений
1. На портале Intune выберите **Клиентские приложения** > **Политики защиты приложений**. Откроется страница сведений **Политики защиты приложений**, в которой можно создавать и изменять политики.
2. Нажмите **Создать политику**.

   ![Снимок экрана: колонка "Добавить политику"](./media/app-protection-policies/app-protection-add-policy.png)

3. Укажите имя политики, добавьте краткое описание и выберите тип платформы. Для каждой платформы можно создать несколько политик.

4. Нажмите **Приложения**, чтобы открыть колонку **Приложения**, где приводится список доступных приложений. Выберите в списке одно или несколько приложений, которые вы хотите сопоставить с создаваемой политикой. Для создания политики необходимо выбрать хотя бы одно приложение.  

5. После выбора приложений нажмите **Выбрать**, чтобы сохранить выбор.

6. В колонке **Добавить политику** выберите **Настроить необходимые параметры**, чтобы открыть **Параметры**.

   Существует три категории параметров политик.
   - **Защита данных** — эта группа включает элементы управления защиты от потери данных (DLP), включая ограничения вырезания, копирования, вставки и сохранения в другом формате. Эти параметры определяют, как пользователи взаимодействуют с данными в приложениях.
   - **Требования доступа** — эта группа содержит параметры ПИН-кода на уровне приложения, которые определяют, каким образом конечный пользователь получает доступ к приложениям в рабочем контексте.  
   - **Условный запуск** — эта группа содержит такие параметры, как минимальные настройки операционной системы, обнаружение взломанных устройств и устройств с административным доступом, а также автономные льготные периоды.

   Чтобы вы быстрее могли приступить к работе, параметры политики снабжены значениями по умолчанию. Если значения по умолчанию удовлетворяют вашим требованиям, никаких изменений вносить не нужно.

   > [!TIP]
   > Эти параметры политики применяются только при использовании приложения в рабочем контексте. Когда конечный пользователь применяет приложение в личных целях, эти политики на него не распространяются. Обратите внимание на то, что при создании файла он считается личным. 

7. Нажмите кнопку **ОК**, чтобы сохранить конфигурацию. Вы вернетесь в колонку **Добавить политику**.
8. Щелкните **Создать** для создания политики и сохранения параметров.

Новые политики, которые вы создаете, не будут развернуты для пользователей, пока вы не сделаете это явным образом. Чтобы развернуть политику, см. раздел [Развертывание политики для пользователей](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Развертывание политики для пользователей

1. Выберите политику на панели **Политики защиты приложений**.

2. На панели ***Защита приложений Intune** выберите **Назначения**, чтобы открыть панель **Защита приложений Intune — Назначения**. На вкладке *Включить* выберите **Выбрать группы для включения**. 

   ![Снимок экрана: область "Назначения" с меню "Выбрать группы для включения"](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Отображается список всех групп безопасности в вашем **Azure Active Directory**. Выберите группы пользователей, к которым должна применяться эта политика, а затем нажмите кнопку **Выбрать**. 

    ![Снимок экрана: область "Добавить группы пользователей" со списком пользователей Azure AD](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Включив и исключив группы, установите флажок **Сохранить** чтобы сохранить конфигурацию и развернуть политику для пользователей. Если вы выберете **Отмена** до сохранения конфигурации, все изменения, внесенные на вкладках *Включение* и *Исключение* будут потеряны.   
 
     ![Снимок экрана. Варианты сохранения и отмены](./media/app-protection-policies/save-assignment.png)
  
Вы создали политику и развернули ее для пользователей.

Эта политика распространяется только на пользователей с назначенными лицензиями Microsoft Intune. Пользователи в выбранной группе безопасности, у которых нет назначенной лицензии Intune, не попадают под действие политики.

>[!IMPORTANT]
> При управлении устройствами с помощью Intune с Configuration Manager политика применяется только к пользователям, находящимся непосредственно в выбранной вами группе. Члены дочерних групп, вложенных в выбранную вами группу, не затрагиваются.

Конечные пользователи могут загрузить приложения из магазина App Store или Google Play. Дополнительные сведения см. на странице
* [Что происходит при управлении приложением Android с помощью политик защиты приложений](../fundamentals/end-user-mam-apps-android.md)
* [Что происходит при управлении приложением iOS с помощью политик защиты приложений](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Изменение существующих политик
Вы можете изменить существующую политику и применить ее к целевым пользователям. Однако при изменении существующих политик пользователи, которые уже выполнили вход в приложения, не заметят никаких изменений в течение восьми часов.

Чтобы сразу увидеть эффект изменений, пользователям необходимо выйти из приложений и войти снова.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Изменение списка приложений, сопоставленных с политикой

1. На панели **Политики защиты приложений** выберите политику, которую нужно изменить.

2. На панели *Защита приложений Intune* выберите **Целевые приложения**, чтобы открыть список приложений.

3. Удалите или добавьте приложения в списке и щелкните значок **Сохранить** для сохранения изменений.

### <a name="to-change-the-list-of-user-groups"></a>Изменение списка групп пользователей


1. На панели **Политики защиты приложений** выберите политику, которую нужно изменить.

2. На панели *Защита приложений Intune* выберите **Назначения** и откройте панель **Защита приложений Intune — Назначения**, где отображается список групп пользователей, для которых установлена эта политика.

3. Чтобы добавить новую группу пользователей в эту политику, на вкладке *Включить* нажмите **Выбрать группы для включения** и выберите группу пользователей. Щелкните **Выбрать**, чтобы добавить группу. 

4. Чтобы исключить группу пользователей, на вкладке *Исключить* щелкните **Выбрать группы для исключения** и выберите группу пользователей. Нажмите **Выбрать** для удаления группы пользователей.  

5. Чтобы удалить группы, которые были добавлены ранее, на вкладке *Включение* или *Исключение* щелкните многоточие (...) и выберите **Удалить**. 

5. Изменив назначения, выберите **Сохранить**, чтобы сохранить конфигурацию и развернуть политику для новой группы пользователей. Если вы выберете **Отмена** до сохранения конфигурации, все изменения, внесенные на вкладках *Включение* и *Исключение* будут потеряны.

### <a name="to-change-policy-settings"></a>Изменение параметров политики

1. На панели **Политики защиты приложений** выберите политику, которую нужно изменить.

2. На панели *Защита приложений Intune* выберите **Свойства**, чтобы открыть список областей параметров, которые можно изменить. 

3. Выберите область параметров с параметрами, которые нужно изменить, например **Перемещение данных** или **Требования доступа**. Измените параметры.

4. Нажмите на значок **Сохранить**, чтобы сохранить изменения. Затем снова выберите область параметров, внесите и сохраните изменения, пока не измените все нужные параметры. После этого можно закрыть панель *Защита приложений Intune*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Назначение политик защиты приложений на основе состояния управления устройством
Как привило, во многих организациях конечные пользователи могут использовать управляемые устройства MDM Intune, такие как корпоративные устройства, и неуправляемые устройства, защищенные только с помощью политик защиты приложений Intune. Неуправляемые устройства часто используются в рамках концепции "принеси свое устройство" (BYOD).

Поскольку политики защиты приложений Intune предназначены для удостоверения пользователя, параметры защиты применяются к зарегистрированным (управляемым MDM) и незарегистрированным устройствам (без MDM). Таким образом, политику защиты приложений Intune можно использовать для зарегистрированных или незарегистрированных в Intune устройств iOS и Android. У вас могут быть отдельные политики защиты для неуправляемых устройств со строгими средствами защиты от потери данных (DLP) и для устройств под управлением MDM с менее жесткими средствами DLP. Дополнительные сведения о выполнении этого процесса на личных устройствах Android Enterprise см. в статье [Политики защиты приложений и рабочие профили на устройствах Android Enterprise в Intune](android-deployment-scenarios-app-protection-work-profiles.md).

Чтобы создать эти политики, в консоли Intune выберите **Клиентские приложения** > **Политики защиты приложений** и нажмите **Создать политику**. Можно также изменить существующую политику защиты приложений. Если политику защиты приложений требуется применять к управляемым и неуправляемым устройствам, задайте параметру **Применять ко всем типам приложений** значение **Да**, являющееся значением по умолчанию. Чтобы назначать политику отдельно в зависимости от состояния управления, задайте параметру **Применять ко всем типам приложений** значение **Нет**. 

![Снимок экрана: колонка "Добавить политику" с параметром "Применять ко всем типам приложений"](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Типы приложений

- **Приложения на неуправляемых устройствах**. Неуправляемые устройства — это устройства, на которых не найдено управление Intune MDM. Сюда входят сторонние поставщики MDM.
- **Приложения на управляемых устройствах Intune**. Управление управляемыми устройствами осуществляется через Intune MDM.
- **Приложения в рабочем профиле Android**. Управляемые устройства, зарегистрированные в качестве устройств рабочего профиля Android.

> Обратите внимание, что для устройств Android появится запрос на установку приложения "Корпоративный портал Intune" независимо от выбранного типа приложения. Например, при выборе "Приложения на управляемых устройствах Intune" пользователям с неуправляемыми устройствами Android все равно будет предложено установить приложение.

Для iOS требуются дополнительные параметры конфигурации политики защиты приложений (APP) для приложений на устройствах, зарегистрированных в Intune:

- Для всех приложений, управляемых MDM, необходимо настроить **IntuneMAMUPN**. Дополнительные сведения см. в разделе [Как управлять передачей данных между приложениями iOS в Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- Для всех сторонних приложений и бизнес-приложений, управляемых MDM, необходимо настроить **IntuneMAMDeviceID**. Для маркера идентификатора устройства необходимо настроить **IntuneMAMDeviceID**. Например, `key=IntuneMAMDeviceID, value={{deviceID}}`. См. сведения о [добавлении политик конфигурации приложений для управляемых устройств iOS](app-configuration-policies-use-ios.md).
- Если настроить только **IntuneMAMDeviceID**, Intune APP будет распознавать устройство как неуправляемое.

> [!NOTE]
> Конкретные сведения о поддержке iOS для политик защиты приложений на основе состояния управления устройством см. в разделе о [назначении политик защиты MAM на основе состояния управления](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Параметры политики
Чтобы просмотреть полный список параметров политики для iOS и Android, перейдите по следующим ссылкам:

- [Политики iOS](app-protection-policy-settings-ios.md)
- [Политики Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Дальнейшие шаги
[Мониторинг соответствия требованиям и состояния пользователей](app-protection-policies-monitor.md)

## <a name="see-also"></a>См. также
* [Что происходит при управлении приложением Android с помощью политик защиты приложений](../fundamentals/end-user-mam-apps-android.md)
* [Что происходит при управлении приложением iOS с помощью политик защиты приложений](../fundamentals/end-user-mam-apps-ios.md)