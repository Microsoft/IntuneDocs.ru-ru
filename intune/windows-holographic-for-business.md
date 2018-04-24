---
title: Управление устройствами Windows Holographic с помощью Microsoft Intune в Azure | Документы Майкрософт
description: С помощью Microsoft Intune можно выполнять различные задачи на устройствах с Windows Holographic for Business, включая настройку корпоративного портала, создание политики соответствия, настройку параметров OMA-URI, развертывание приложений, разделение устройств на группы, создание профилей, ограничение устройств, включение обновлений программного обеспечения, задание условий, настройку параметров сетей Wi-Fi и VPN и использование Hello для бизнеса.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41c1ea3bf12b83a0f09c8535275ffb58e5f46931
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Настройка устройств с Windows Holographic с помощью Intune

Microsoft Intune поддерживает устройства с Windows Holographic for Business, такие как [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Для управления устройствами с Windows Holographic с помощью Microsoft Intune необходимо создать профиль обновления выпуска. Этот профиль позволяет обновлять устройства с Windows Holographic до Windows Holographic for Business. Для получения нужной лицензии на обновление Microsoft HoloLens вы можете приобрести пакет Commercial Suite. Дополнительные сведения: [Обновление устройств с Windows Holographic до Windows Holographic for Business](holographic-upgrade.md).

Для настройки устройств с Windows Holographic for Business и управления ими можно использовать задачи, приведенные в этой статье. Например, можно управлять обновлениями программного обеспечения, настраивать параметры VPN и многое другое.

## <a name="company-portal"></a>Company Portal (Портал компании)
**[Настройка приложения корпоративного портала](company-portal-app.md)**

В состав Intune входит корпоративный портал, где пользователи могут получать доступ к данным компании, регистрировать устройства, устанавливать приложения, обращаться к сотрудникам к ИТ-отдела и т. д. Приложение корпоративного портала можно настроить для устройств с Windows Holographic for Business.

## <a name="compliance-policy"></a>Compliance policy (Политика соответствия требованиям)
**[Создание политики соответствия устройств](compliance-policy-create-windows.md)**

Политики соответствия требованиям — это правила и параметры, которым должны отвечать устройства, чтобы считаться соответствующими. Эти политики можно использовать с условным доступом для блокировки доступа не соответствующих требованиям устройств к корпоративным ресурсам. В Intune можно создать политики соответствия, разрешающие или запрещающие доступ устройствам с Windows Holographic for Business. Например, можно создать политику, которая требует включения BitLocker.

См. также статью **[Начало работы с политиками соответствия устройств](device-compliance-get-started.md)**.

## <a name="deploy-apps"></a>Развертывание приложений
**[Добавление приложений в Intune](apps-add.md)**

С помощью Intune можно добавлять приложения на устройства с Windows Holographic for Business. Существует множество способов развертывания приложений, в том числе:

- [добавление приложений из Microsoft Store](store-apps-windows.md);
- [добавление создаваемых вами приложений](lob-apps-windows.md);
- [назначение приложений группам](apps-deploy.md).

## <a name="device-categories-and-groups"></a>Категории и группы устройств
**[Разделение устройств на группы](device-group-mapping.md)**

С помощью Intune можно создать категории устройств для автоматического добавления устройств в группы на основании создаваемых категорий, таких как "Sales" (Продажи), "Accounting" (Бух. учет), "Human Resources" (Отдел кадров). Идея состоит в том, чтобы упростить управление устройствами с Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Профили конфигурации устройства 
**[Начало работы с профилями конфигураций](device-profiles.md) и [создание собственного профиля](device-profile-create.md)**

Intune содержит параметры и функции, которые можно включать или отключать на различных устройствах в вашей организации. Эти параметры и функции управляются с помощью профилей. Например, можно создать профиль, который включает Кортану или использует Smart Screen Защитника Windows на устройствах с Windows Holographic for Business.

C помощью OMA-URI в профилях настраиваются некоторые параметры, создаются ограничения устройств и настраиваются параметры виртуальной частной сети (VPN) и Wi-Fi.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Настраиваемые параметры устройств](custom-settings-windows-holographic.md)

Чтобы настроить параметры OMA-URI (Open Mobile Alliance Uniform Resource Identifier), создайте пользовательский профиль в Intune. Используйте параметры OMA-URI для управления различными функциями на устройствах Windows Holographic for Business, такими как включение VPN и проверка наличия обновлений в Центре обновления Майкрософт.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Ограничения устройств](device-restrictions-windows-holographic.md)

Ограничения устройств позволяют управлять различными параметрами и функциями на устройствах, включая требование пароля, установку приложений из [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), включение Bluetooth и многое другое. Эти ограничения создаются в профиле Intune. Профиль можно применить к нескольким устройствам с Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Настройка VPN](vpn-settings-configure.md)

Виртуальная частная сеть (VPN) предоставляет пользователям безопасный удаленный доступ к сети компании. В Intune можно создать профиль VPN с конкретными параметрами для устройств с Windows Holographic for Business. Например, можно создать профиль VPN, чтобы все устройства с Windows Holographic for Business использовали Citrix VPN в качестве типа соединения.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Настройка Wi-Fi](wi-fi-settings-configure.md)

В Intune можно также создать профиль Wi-Fi для назначения параметров беспроводной сети устройствам Windows Holographic for Business. При назначении профиля Wi-Fi конечные пользователи получают доступ к корпоративной сети без настройки сети. Например, можно создать сеть Wi-Fi, предназначенную только для устройств с Windows Holographic for Business.

## <a name="software-updates"></a>Обновления программного обеспечения
**[Управление обновлениями программного обеспечения](windows-update-for-business-configure.md)**

Intune содержит функцию, называемую кругами обновления для устройств Windows 10. Эти круги обновления содержат группу параметров, которые определяют способ установки обновлений. Например, можно создать период обслуживания для установки обновлений или выбрать возможность перезапуска после установки обновлений. Круг обновления можно применить к нескольким устройствам с Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Terms and conditions (Условия)
**[Задание условий компании для доступа пользователей](terms-and-conditions-create.md)**

Прежде чем пользователи смогут зарегистрировать устройства и получить доступ к корпоративным приложениям, включая электронную почту, можно потребовать принятие условий компании. В Intune можно определить способ отображения условий на корпоративном портале, а также назначить эти условия устройствам с Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello для бизнеса
**[Использование Windows Hello для бизнеса](windows-hello.md)**

Windows Hello для бизнеса — это альтернативный метод входа, использующий учетную запись Azure Active Directory для замены пароля, смарт-карты или виртуальной смарт-карты. Благодаря Windows Hello для бизнеса можно выполнять вход с устройств с Windows Holographic for Business с помощью заданного ПИН-кода минимальной длины.
