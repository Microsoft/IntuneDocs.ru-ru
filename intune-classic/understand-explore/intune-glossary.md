---
title: "Глоссарий Intune | Документация Майкрософт"
description: "Дополнительные сведения о терминологии в Microsoft Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 43b6dbfc004e8687eaf2a0ee185728136f457bfc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="microsoft-intune-glossary"></a>Глоссарий Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="a"></a>A

|||
|-|-|
|App SDK (Пакет SDK для приложений)|[Пакет SDK для приложений Microsoft Intune](/intune-classic/develop/intune-app-sdk) позволяет добавить функциональные возможности в собственные приложения, после чего ими можно будет управлять посредством политик управления мобильными приложениями Intune.|
|App wrapping tool (Инструмент упаковки приложений)|[Приложение командной строки](/intune-classic/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune), которое создает оболочку вокруг бизнес-приложения, что позволяет управлять им с помощью политики управления мобильными приложениями Intune.|
|Available install (Доступная установка)|При развертывании приложения с помощью этого действия оно отображается на корпоративном портале, и пользователи могут [установить его по запросу](/intune-classic/deploy-use/deploy-apps).|
|Azure Portal (Портал Azure)|Новая консоль Intune, которая появится в ближайшее время. Сейчас для создания [политик Intune MAM](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) для устройств можно использовать портал Azure.||

## <a name="b"></a>B
|||
|-|-|
|BYOD|[Принеси свое устройство](/intune-classic/get-started/choose-how-to-enroll-devices1). Пользователи могут установить приложение корпоративного портала Intune на своем устройстве и зарегистрировать его для доступа к ресурсам организации, таким как электронная почта, корпоративные приложения, корпоративные данные и поддержка.|

## <a name="c"></a>C
|||
|-|-|
|Certificate profile (Профиль сертификата)|Используйте этот тип политики для [безопасного доступа к корпоративным ресурсам](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) с помощью сертификатов, когда вы работаете с профилями Wi-Fi, VPN или электронной почты.|
|Cloud storage space (Пространство облачного хранилища)|Место, где [хранятся](/intune-classic/deploy-use/add-apps#cloud-storage-space) приложения или данные о создаваемых приложениях.|
|COD (КОД)|[Устройства, принадлежащие компании](/intune-classic/get-started/choose-how-to-enroll-devices1), можно регистрировать разными способами в зависимости от потребностей организации и типов управляемых устройств.|
|Company Portal (Портал компании)|Приложение или веб-сайт, которые предоставляют пользователям [доступ к корпоративным данным и приложениям](/intune-classic/get-started/microsoft-intune-company-portal).|
|Compliance policy (Политика соответствия требованиям)|Гарантирует то, что устройства, используемые для доступа к данным и приложениям организации, [соответствуют определенным правилам](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) (например, использование ПИН-код для доступа к устройству и шифрование данных, хранящихся на устройстве).|
|Compliant and noncompliant apps (Соответствующие и несоответствующие приложения)|Эти параметры, являющиеся частью [общей политики конфигурации](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), позволяют определить список приложений, которые пользователи могут или не могут запускать. После этого служба Intune с помощью отчетов уведомляет вас о том, чтобы были установлены или запущены несоответствующие приложения. Для некоторых платформ Intune также может блокировать установку несоответствующих приложений.|
|Conditional access (Условный доступ)|[Разрешает доступ к корпоративной электронной почте, Office 365 и другим службам](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) только с устройств, которые соответствуют набору заданных вами правил.|
|Custom policy (Настраиваемая политика)|[Используйте эти политики](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), когда общая политика конфигурации не содержит нужные вам параметры. Возможно, с помощью настраиваемой политики вы сможете создать параметр другими способами, такими как конфигуратор Apple или OMA-URI.|

## <a name="d"></a>D
|||
|-|-|
|Deployment (Развертывание)|Процедура отправки приложения или политики для устройства или пользователя, которыми вы управляете.|
|Deployment action (Действие развертывания)|Выбор, выполняемый при [развертывании приложения](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune). Можно сделать установку приложения обязательной или необязательной, а также удалить приложение.|
|Device enrollment manager (Диспетчер регистрации устройств)|Организации могут использовать Intune для управления большим количеством мобильных устройств с помощью одной учетной записи пользователя. Учетная запись [диспетчер регистрации устройств /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) — это специальная учетная запись Intune, с помощью которой можно зарегистрировать до 1000 устройств.|
|Device group mapping (Сопоставление группы устройств)|Помогает [автоматически добавить устройства в группы](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) на основе категории (например, "Личные" или "Продажи"), которую вы или конечный пользователь назначаете устройству.|

## <a name="e"></a>E
|||
|-|-|
|Email profile (Профиль электронной почты)|Эта политика позволяет настроить [параметры доступа к электронной почте](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) для отдельных почтовых клиентов на мобильных устройствах, минимизируя объем необходимой настройки со стороны пользователя.|
|EMS|Microsoft Enterprise Mobility + Security (прежнее название — Enterprise Mobility Suite) защищает корпоративные данные и предоставляет вашим пользователям [доступ к нужным приложениям и содержимому](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|End user (Конечный пользователь)|[Пользователи таких устройств, как телефоны и компьютеры](/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune), которые находятся под управлением Intune.|
|Enroll (Регистрация)|В Microsoft Intune [регистрация](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) используется для обеспечения управления устройствами и доступа к ресурсам.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|[Служба Майкрософт](https://technet.microsoft.com/library/mt228265.aspx) для пользователей Intune со 150 лицензиями в рамках соответствующего плана. Благодаря этой службе специалисты Майкрософт помогут вам приступить к работе с Intune.|

## <a name="g"></a>G
|||
|-|-|
|Groups (Группы)|Группы позволяют [логически объединить пользователей или устройства](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). Например, можно создать группу из всех компьютеров под управлением Windows. Затем для этих групп можно развертывать приложения и политики.|

## <a name="h"></a>H
|||
|-|-|
|Hybrid (гибридные)|Конфигурация, в которой можно управлять устройствами, зарегистрированными в Intune, [с помощью консоли System Center Configuration Manager](/intune-classic/get-started/integration-with-cloud-services).|

## <a name="i"></a>I
|||
|-|-|
|Intune administration console (консоль администрирования Intune)|Текущая консоль, используемая для большинства операций управления Intune.|
|Intune software client (Программный клиент Intune)|Альтернативный способ [управления несколькими компьютерами с Windows](/intune-classic/get-started/choose-how-to-manage-devices) для помощи в выборе подходящего метода.|
|Intune Software Publisher (издателя программного обеспечения Intune)|Средство, используемое для [определения приложений, которые необходимо развернуть и отправить в облачное хранилище](/intune-classic/deploy-use/add-apps).|
|Inventory (Товары)|Используйте для просмотра [оборудования и установленного программного обеспечения](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) на управляемых устройствах.|

## <a name="k"></a>K
|||
|-|-|
|Kiosk mode (Полноэкранный режим)|Этот режим, настроенный в составе [общей политики конфигурации](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), позволяет заблокировать устройства. Например, можно настроить устройство розничной торговли для запуска всего одного приложения.|

## <a name="m"></a>M
|||
|-|-|
|Managed Browser|[Приложение для просмотра веб-страниц](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies), которое можно развернуть в организации с помощью Microsoft Intune. Политика управляемого браузера настраивает список разрешений или список блокировок, ограничивающий те веб-сайты, которые могут посетить пользователи управляемого браузера.|
|Управление мобильными приложениями|[Управление мобильными приложениями /intune-classic/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) позволяет публиковать, отправлять, настраивать, защищать, отслеживать и обновлять мобильные приложения для пользователей.
|управление мобильными устройствами|[Управление мобильными устройствами /intune-classic/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) позволяет зарегистрировать устройства в Intune для последующей подготовки, настройки, мониторинга и выполнения действий на этих устройствах.
|MDM authority (Центр MDM)|[Центр MDM](/intune-classic/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) определяет службу управления, у которой есть разрешение на управление набором устройств. Возможные варианты центра управления мобильными устройствами — отдельная служба Intune или Configuration Manager с Intune.|
|Mobile app provisioning policy (Политика подготовки мобильных приложений)|Политика iOS, помогающая предотвращать истечение срока действия для [профилей подготовки](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles) для развертываемых приложений iOS.|
|Mobile app configuration policy (Политика конфигурации мобильных приложений)|Политика iOS, которая позволяет [предоставить параметры для совместимых приложений iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) при их запуске, например название организации или адрес сервера.|

## <a name="o"></a>O
|||
|-|-|
|OMA-DM|Управление устройствами Open Mobile Alliance. Являющийся отраслевым стандартом протокол управления устройствами, используемый многими изготовителями оборудования для реализации функций управления мобильными устройствами и компьютерами.|
|OMA-URI|Универсальный идентификатор ресурса Open Mobile Alliance. Они определяют отдельные параметры устройств, соответствующие стандарту OMA-DM. Некоторые из них можно использовать в [настраиваемых политиках Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) при отсутствии подходящих встроенных параметров.|

## <a name="p"></a>P
|||
|-|-|
|Policy (Политика)|[Пакет сведений](/intune-classic/deploy-use/microsoft-intune-policy-reference), передаваемый из Intune на устройство. Например, можно развернуть на устройстве параметры безопасности или сведения о соответствии устройств.|
|Passcode reset (Сброс секретного кода)|Функция Intune, позволяющая вынудить пользователя выполнить [сброс секретного кода](/intune-classic/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) на поддерживаемых устройствах.|

## <a name="r"></a>R
|||
|-|-|
|Remote lock (удаленная блокировка)|Функция Intune, позволяющая [заблокировать поддерживаемые устройства](/intune-classic/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), включая те, которые вам не принадлежат.|
|Reports|Intune предлагает обширный набор [встроенных отчетов](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports), предоставляющих сведения об управляемых устройствах.|
|Required install (Обязательная установка)|При развертывании приложения с помощью этого действия оно устанавливается на устройстве [без вмешательства пользователя](/intune-classic/deploy-use/deploy-apps) (хотя на некоторых платформах пользователю может потребоваться принять установку).|
|Requirements (Требования)|[Операция развертывания приложения](/intune-classic/deploy-use/add-apps), позволяющая выбрать требования, которые должны быть выполнены на устройстве перед установкой приложения. Например, можно указать версию ОС IOS, которую необходимо установить перед установкой приложения.|

## <a name="s"></a>S
|||
|-|-|
|Selective wipe (Выборочная очистка)|[Выборочная очистка](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) удаляет с устройства только данные организации, включая данные управления мобильными приложениями (MAM), где это возможно, параметры и профили электронной почты. При выборочной очистке личные данные пользователя остаются на устройстве.|
|Подписка|Заключенное вами соглашение, которое обеспечивает доступ к клиенту Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Стороннее приложение, работающее с Intune для предоставления [возможности удаленной помощи](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) компьютерам с Windows, управляемым с помощью программного клиента Intune.|
|Клиент|Один экземпляр службы Intune, к которому вы можете получить доступ с помощью подписки.|
|Terms and conditions (Условия)|Тип политики, который можно развернуть для пользователей, содержащий сведения, которые пользователи должны [прочесть и принять](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune), чтобы в дальнейшем использовать корпоративный портал для регистрации и доступа к своей работе.|

## <a name="v"></a>V
|||
|-|-|
|Volume-purchased app (Приложение, приобретенное по программе Volume Purchase Program)|Некоторые магазины приложений позволяют приобретать сразу несколько лицензий, если приложение планируется использовать в организации. Intune помогает управлять приложениями, [приобретенными по такой программе](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune), импортируя данные о лицензиях из магазина приложений, отслеживая число используемых лицензий и следя за тем, чтобы число установленных копий приложения не превышало число приобретенных.|
|VPN profile (Профиль VPN)|Политика, которая развертывает [параметры VPN](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune) для управляемых устройств, сводя к минимуму объем работ по настройке со стороны конечных пользователей.|

## <a name="w"></a>Вт
|||
|-|-|
|Wi-Fi profile (Профиль Wi-Fi)|Политика, которая развертывает на устройствах [параметры беспроводной сети](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune), чтобы позволить пользователям подключаться к корпоративной сети без настройки каких-либо параметров.
