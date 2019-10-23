---
title: Использование устройств Windows Holographic с помощью Microsoft Intune в Azure | Документация Майкрософт
description: С помощью Microsoft Intune можно управлять устройствами с Windows Holographic for Business и HoloLens и выполнять на них различные задачи, включая настройку корпоративного портала, создание политики соответствия, настройку параметров OMA-URI, развертывание приложений, разделение устройств на группы, создание профилей, ограничение устройств, включение обновлений программного обеспечения, задание условий, настройку параметров сетей Wi-Fi и VPN и использование Hello для бизнеса.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 585a2f17-106b-4f02-adf7-05f08a92dbc1
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdb3623a61c16f69773703b8acdbb8f7c02b4ac4
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504745"
---
# <a name="manage-and-use-different-device-management-features-on-windows-holographic-and-hololens-devices-with-intune"></a>Администрирование и использование различных возможностей управления устройствами Windows Holographic и HoloLens с помощью Intune

Microsoft Intune содержит множество функций для управления устройствами под управлением Windows Holographic for Business, например [Microsoft HoloLens](https://docs.microsoft.com/hololens/). С помощью Intune вы можете гарантировать, что все устройства соответствуют действующим в организации требованиям, а также добавить для них профиль VPN или Wi-Fi. Еще одна ключевая возможность — использование устройства в качестве киоска для запуска определенного приложения или набора приложений.

Представленные в этой статье задачи помогут упростить администрирование, настройку и защиту устройств под управлением Windows Holographic for Business, в том числе обновление программного обеспечения и использование Windows Hello для бизнеса.

Чтобы использовать в Intune устройства под управлением Windows Holographic, создайте профиль "Обновление выпуска". Этот профиль позволяет обновлять устройства с Windows Holographic до Windows Holographic for Business. Для получения нужной лицензии на обновление Microsoft HoloLens вы можете приобрести пакет Commercial Suite. Дополнительные сведения: [Обновление устройств с Windows Holographic до Windows Holographic for Business](../configuration/holographic-upgrade.md).

## <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory (AD) отлично подходит для настройки устройств с Windows Holographic for Business и управления ими. Intune и Azure AD дают следующие возможности: 

- **[Присоединение устройств к Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)** . В Azure Active Directory (AD) можно добавить принадлежащие организации устройства на базе Windows 10, включая устройства с Windows Holographic for Business. Эта функция позволяет Azure AD управлять устройством. С ее помощью вы можете добиться того, чтобы пользователи обращались к ресурсам организации с устройств, отвечающих стандартам по безопасности и соответствию требованиям.

  Дополнительные сведения см. в статье [Что такое управление устройствами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/overview).

- **[Массовая регистрация для устройств Windows](../enrollment/windows-bulk-enroll.md)** . Вы можете присоединить большое количество новых устройств Windows к Azure Active Directory и Intune. Эта функция вызывается массовой регистрацией и использует пакеты подготовки. Эти пакеты присоединяют устройства с Windows Holographic for Business к клиенту Azure AD и регистрируют их в Intune.

## <a name="company-portal"></a>Company Portal (Портал компании)
**[Настройка приложения корпоративного портала](../apps/company-portal-app.md)**

В состав Intune входит корпоративный портал — приложение, где пользователи могут получать доступ к данным организации, регистрировать устройства, устанавливать приложения, обращаться к сотрудникам к ИТ-отдела и т. д. Приложение корпоративного портала можно настроить для устройств с Windows Holographic for Business.

В приложении корпоративного портала можно выполнять указанные ниже действия:

- [Удалить устройство из Intune](/intune-user-help/unenroll-your-device-from-intune-windows) с помощью приложения "Параметры" или приложения корпоративного портала
- [Переименовать устройство](/intune-user-help/rename-your-device-cpapp)
- [Устанавливать приложения](/intune-user-help/install-apps-cpapp-windows) на устройстве
- [Синхронизировать устройства вручную](/intune-user-help/sync-your-device-manually-windows) из приложения "Параметры" или приложения корпоративного портала

## <a name="compliance-policy"></a>Compliance policy (Политика соответствия требованиям)
**[Создание политики соответствия устройств](../protect/compliance-policy-create-windows.md)**

Политики соответствия требованиям — это правила и параметры, которым должны отвечать устройства, чтобы считаться соответствующими. Эти политики можно использовать с условным доступом для блокировки доступа не соответствующих требованиям устройств к корпоративным ресурсам. В Intune можно создать политики соответствия, разрешающие или запрещающие доступ устройствам с Windows Holographic for Business. Например, можно создать политику, которая требует включения BitLocker.

См. также статью **[Начало работы с политиками соответствия устройств](../protect/device-compliance-get-started.md)** .

## <a name="deploy-and-manage-apps"></a>Развертывание приложений и управление ими
**[Добавление приложений в Intune](../apps/apps-add.md)**

С помощью Intune можно добавлять приложения на устройства с Windows Holographic for Business. Существует множество способов развертывания приложений, в том числе:

- [добавление приложений из Microsoft Store](../apps/store-apps-windows.md);
- [добавление создаваемых вами приложений](../apps/lob-apps-windows.md);
- [назначение приложений группам](../apps/apps-deploy.md).

Microsoft Intune может развертывать универсальные приложения для Windows на устройствах Microsoft HoloLens под управлением Windows Holographic for Business. Вы можете напрямую отправить пакеты приложений на портале Intune Azure или развернуть их из Microsoft Store для бизнеса. Дополнительные сведения о связанных областях см. в следующих статьях:
- Сведения о развертывании бизнес-приложений с помощью портала Intune Azure см. в статье [Как добавить бизнес-приложения Windows в Microsoft Intune](../apps/lob-apps-windows.md).

    > [!NOTE]
    > Максимальный размер пакета в Intune — 8 ГБ. Этот размер пакета доступен только для бизнес-приложений, отправленных в Intune.

- Сведения о развертывании приложений из Microsoft Store для бизнеса см. в статье [Управление приложениями, приобретенными в Магазине Майкрософт для бизнеса, с помощью Microsoft Intune](../apps/windows-store-for-business.md). 
- Сведения об управлении приложениями с помощью Microsoft Intune см. в статье [Что такое управление приложениями с помощью Microsoft Intune](../apps/app-management.md).
- Сведения о разработке приложений для Microsoft HoloLens см. на странице [о приложениях смешанной реальности для Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Устройства HoloLens под управлением Windows 10 Holographic for Business 1607 не поддерживают лицензированные веб-приложения из Microsoft Store для бизнеса. Дополнительные сведения см. в статье [Установка приложений на устройство HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

## <a name="device-actions"></a>Действия устройства
Intune имеет несколько встроенных действий, позволяющих ИТ-администраторам выполнять разные задачи как локально на устройстве, так и удаленно с помощью Intune на портале Azure. Кроме того, пользователи могут запускать удаленную команду с корпоративного портала Intune для личных устройств, зарегистрированных в Intune.

Для устройств с Windows Holographic for Business можно использовать следующие действия: 

- **[Очистка](../remote-actions/devices-wipe.md#wipe)** . Действие **Очистка** удаляет устройство из Intune и восстанавливает на нем заводские параметры. Используйте это действие перед передачей устройства новому пользователю, а также при утере или краже.

- **[Прекратить использование](../remote-actions/devices-wipe.md#retire)** . Действие **Прекратить использование** удаляет устройство из Intune. Оно также удаляет данные управляемого приложения, параметры и профили электронной почты, назначенные Intune. Персональные данные пользователя остаются на устройстве.

- **[Синхронизация устройств для получения последних политик и действий](../remote-actions/device-sync.md)** . Действие **Синхронизация** заставляет устройство немедленно установить связь с Intune. При возврате устройство сразу же получает все ожидающие действия или политики, которые были ему назначены. Эта функция позволяет проверять назначенные политики и устранять возникшие неполадки, не дожидаясь следующего запланированного возврата.

Статья **[Что такое управление устройствами с помощью Microsoft Intune?](../remote-actions/device-management.md)** является хорошим источником сведений об управлении устройствами с помощью портала Azure. 

## <a name="device-categories-and-groups"></a>Категории и группы устройств
**[Разделение устройств на группы](../enrollment/device-group-mapping.md)**

С помощью Intune можно создать категории устройств для автоматического добавления устройств в группы на основании создаваемых категорий, таких как "Sales" (Продажи), "Accounting" (Бух. учет), "Human Resources" (Отдел кадров). Идея состоит в том, чтобы упростить управление устройствами с Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Профили конфигурации устройства 
**[Начало работы с профилями конфигураций](../configuration/device-profiles.md) и [создание собственного профиля](../configuration/device-profile-create.md)**

Intune содержит параметры и функции, которые можно включать или отключать на различных устройствах в вашей организации. Эти параметры и функции управляются с помощью профилей. Например, можно создать профиль, который включает Кортану или использует Smart Screen Защитника Windows на устройствах с Windows Holographic for Business.

C помощью OMA-URI в профилях настраиваются некоторые параметры, создаются ограничения устройств и настраиваются параметры виртуальной частной сети (VPN) и Wi-Fi.

### <a name="custom-device-settingsconfigurationcustom-settings-windows-holographicmd"></a>[Настраиваемые параметры устройств](../configuration/custom-settings-windows-holographic.md)

Чтобы настроить параметры OMA-URI (Open Mobile Alliance Uniform Resource Identifier), создайте пользовательский профиль в Intune. Используйте параметры OMA-URI для управления различными функциями на устройствах Windows Holographic for Business, такими как включение VPN и проверка наличия обновлений в Центре обновления Майкрософт.

### <a name="configure-kiosk-modeconfigurationkiosk-settings-holographicmd"></a>[Настройка режима киоска](../configuration/kiosk-settings-holographic.md)

Используя функции общего или гостевого компьютера, доступные в Intune, можно настроить в Windows Holographic for Business запуск от имени в режиме терминала устройства (киоска). Такие устройства позволяют запускать одно приложение (полноэкранный режим одного приложения) или несколько приложений (режим киоска с несколькими приложениями).

### <a name="device-restrictionsconfigurationdevice-restrictions-windows-holographicmd"></a>[Ограничения устройств](../configuration/device-restrictions-windows-holographic.md)

Ограничения устройств позволяют управлять различными параметрами и функциями на устройствах, включая требование пароля, установку приложений из [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), включение Bluetooth и многое другое. Эти ограничения создаются в профиле Intune. Профиль можно применить к нескольким устройствам с Windows Holographic for Business.

### <a name="configure-vpnconfigurationvpn-settings-configuremd"></a>[Настройка VPN](../configuration/vpn-settings-configure.md)

Виртуальная частная сеть (VPN) предоставляет пользователям безопасный удаленный доступ к сети компании. В Intune можно создать профиль VPN с конкретными параметрами для устройств с Windows Holographic for Business. Например, можно создать профиль VPN, чтобы все устройства с Windows Holographic for Business использовали Citrix VPN в качестве типа соединения.

### <a name="configure-wi-ficonfigurationwi-fi-settings-configuremd"></a>[Настройка Wi-Fi](../configuration/wi-fi-settings-configure.md)

В Intune можно также создать профиль Wi-Fi для назначения параметров беспроводной сети устройствам Windows Holographic for Business. При назначении профиля Wi-Fi конечные пользователи получают доступ к корпоративной сети без настройки сети. Например, можно создать сеть Wi-Fi, предназначенную только для устройств с Windows Holographic for Business.

## <a name="shared-multi-user-devices"></a>Общие устройства для множества пользователей
[Общие устройства](../configuration/shared-user-device-settings-windows-holographic.md)

Устройства с Windows Holographic for Business, такие как Microsoft HoloLens, поддерживают несколько пользователей. Intune содержит параметры для управления различными функциями на этих общих устройствах, такие как управление питанием, с помощью локального хранилища и управления учетными записями. Профили конфигурации могут также применяться к устройствам с разными операционными системами. Например, в одной и той же группе устройств могут быть устройства под управлением RS2 и RS3.

## <a name="software-updates"></a>Обновления программного обеспечения
**[Управление обновлениями программного обеспечения](../protect/windows-update-for-business-configure.md)**

Intune содержит функцию, называемую кругами обновления для устройств Windows 10. Эти круги обновления содержат группу параметров, которые определяют способ установки обновлений. Например, можно создать период обслуживания для установки обновлений или выбрать возможность перезапуска после установки обновлений. Круг обновления можно применить к нескольким устройствам с Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Terms and conditions (Условия)
**[Задание условий компании для доступа пользователей](../enrollment/terms-and-conditions-create.md)**

Прежде чем пользователи смогут зарегистрировать устройства и получить доступ к корпоративным приложениям, включая электронную почту, можно потребовать принятие условий компании. В Intune можно определить способ отображения условий на корпоративном портале, а также назначить эти условия устройствам с Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello для бизнеса
**[Использование Windows Hello для бизнеса](../protect/windows-hello.md)**

Windows Hello для бизнеса — это альтернативный метод входа, использующий учетную запись Azure Active Directory для замены пароля, смарт-карты или виртуальной смарт-карты. Благодаря Windows Hello для бизнеса можно выполнять вход с устройств с Windows Holographic for Business с помощью заданного ПИН-кода минимальной длины.
