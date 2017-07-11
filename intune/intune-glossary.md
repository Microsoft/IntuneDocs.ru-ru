---
title: "Глоссарий Intune"
titleSuffix: Intune on Azure
description: "Сведения о терминологии, используемой в Microsoft Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d
ms.custom: intune-azure
ms.openlocfilehash: a9b43fc1a1877a3fc8bf4c5ee00e02dfee3cdea8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="microsoft-intune-glossary"></a>Глоссарий Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="a"></a>A

|||
|-|-|
|Назначение приложений|Позволяет пользователям [находить, скачивать и устанавливать](/intune/app-management) нужные приложения. Ранее эта функция называлась *развертыванием приложений*.|
|Профиль конфигурации приложения|Определяет конкретные параметры приложения [iOS](/intune/app-configuration-policies-use-ios) или [Android](/intune/app-configuration-policies-use-android) до его запуска.|
|Мониторинг приложений|Позволяет [просматривать последние сведения о состоянии и действиях](/intune/apps-monitor) для назначения приложения.|
|Задача по удалению данных для защиты приложения|[Удаляет данные приложения](/intune/app-protection-policies) с устройства пользователя.|
|Политика защиты приложений|Гарантирует, что приложения пользователя соответствуют требованиям [политик защиты данных организации](/intune/app-protection-policies).|
|App SDK (Пакет SDK для приложений)|[Пакет SDK для приложений Microsoft Intune](/intune/app-sdk) позволяет добавить функциональные возможности в собственные приложения, после чего ими можно будет управлять посредством политик защиты приложений Intune.|
|Действие удаления приложения|Позволяет [удалять приложения](/intune/apps-deploy) с устройств пользователя.|
|App wrapping tool (Инструмент упаковки приложений)|[Приложение командной строки](/intune/apps-prepare-mobile-application-management), которое создает оболочку вокруг бизнес-приложения, что позволяет управлять им с помощью политики защиты приложений Intune.|
|Действие назначения|Выбор, выполняемый при [назначении приложения](/intune/apps-deploy). Можно сделать установку приложения обязательной или необязательной (доступной), а также удалить приложение.|
|Available install (Доступная установка)|При назначении приложения с помощью этого действия оно отображается на корпоративном портале, и пользователи могут [установить его по запросу](/intune/apps-deploy).|
|Azure Portal (Портал Azure)|Новая консоль для службы Intune [Дополнительные сведения](/intune/what-is-intune).|

## <a name="b"></a>B
|||
|-|-|
|BYOD|[Принеси свое устройство](/intune/device-enrollment). Пользователи могут установить приложение корпоративного портала Intune на своем устройстве и зарегистрировать его для доступа к ресурсам организации, таким как электронная почта, корпоративные приложения, корпоративные данные и поддержка.|

## <a name="c"></a>C
|||
|-|-|
|Certificate profile (Профиль сертификата)|Используйте этот тип политики для [безопасного доступа к корпоративным ресурсам](/intune/certificates-configure) с помощью сертификатов, когда вы работаете с профилями Wi-Fi, VPN или электронной почты.|
|COD (КОД)|[Устройства, принадлежащие компании](/intune/device-enrollment), можно регистрировать разными способами в зависимости от потребностей организации и типов управляемых устройств.|
|Company Portal (Портал компании)|Приложение или веб-сайт, которые предоставляют пользователям [доступ к корпоративным данным и приложениям](/intune/company-portal-customize).|
|Compliance policy (Политика соответствия требованиям)|Гарантирует то, что устройства [соответствуют определенным правилам](/intune/device-compliance) (например, использование ПИН-кода для доступа к устройству и шифрование данных, хранящихся на устройстве).|
|Compliant and noncompliant apps (Соответствующие и несоответствующие приложения)|Эти параметры, являющиеся частью [профиля ограничения использования устройства](/intune/device-restrictions-configure), позволяют определить список приложений, которые пользователи могут или не могут запускать. После этого Intune уведомляет вас посредством чтобы были установлены или запущены несоответствующие приложения. Для некоторых платформ Intune также может блокировать установку несоответствующих приложений.|
|Conditional access (Условный доступ)|[Разрешает доступ к корпоративной электронной почте, Office 365 и другим службам](/intune/conditional-access) только с устройств, которые соответствуют набору заданных вами правил.|
|Custom policy (Настраиваемая политика)|[Используйте эти политики](/intune/custom-settings-configure), когда общая политика конфигурации не содержит нужные вам параметры. Возможно, с помощью настраиваемой политики вы сможете создать параметр другими способами, такими как конфигуратор Apple или OMA-URI.|

## <a name="d"></a>D
|||
|-|-|
|Deployment (Развертывание)|Процедура отправки приложения или политики для устройства или пользователя, которыми вы управляете. Это действие теперь называется *назначением*.|
|Device enrollment manager (Диспетчер регистрации устройств)|Организации могут использовать Intune для управления большим количеством мобильных устройств с помощью одной учетной записи пользователя. Учетная запись [диспетчера регистрации устройств (DEM)](/intune/device-enrollment-program-enroll-ios) — это специальная учетная запись Intune, на которую можно зарегистрировать до 1000 устройств.|
|Профили устройств|[Эти профили](/intune/device-profile-create) позволяют настроить широкий спектр параметров безопасности, функций и доступа на управляемых устройствах.|

## <a name="e"></a>E
|||
|-|-|
|Email profile (Профиль электронной почты)|Эта политика позволяет настроить [параметры доступа к электронной почте](/intune/email-settings-configure) для отдельных мобильных устройств, минимизируя объем необходимой настройки со стороны пользователя.|
|EMS|Microsoft Enterprise Mobility + Security (прежнее название — Enterprise Mobility Suite) защищает корпоративные данные и предоставляет вашим пользователям [доступ к нужным приложениям и содержимому](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|End user (Конечный пользователь)|[Пользователи таких устройств, как телефоны и компьютеры](/intune/end-user-educate), которые находятся под управлением Intune.|
|Enroll (Регистрация)|В Microsoft Intune [регистрация](/intune/device-enrollment) используется для обеспечения управления устройствами и доступа к ресурсам.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|[Служба Майкрософт](https://technet.microsoft.com/library/mt228265.aspx) для пользователей Intune со 150 лицензиями в рамках соответствующего плана. Благодаря этой службе специалисты Майкрософт помогут вам приступить к работе с Intune.|

## <a name="g"></a>G
|||
|-|-|
|Groups (Группы)|Группы позволяют [логически объединить пользователей или устройства](/intune/groups-get-started). Например, можно создать группу из всех компьютеров под управлением Windows. После этого группам можно назначать приложения и профили.|

## <a name="h"></a>H
|||
|-|-|
|Hybrid (гибридные)|Конфигурация, в которой можно управлять устройствами, зарегистрированными в Intune, с помощью консоли System Center Configuration Manager.|

## <a name="i"></a>I
|||
|-|-|
|Портал Intune|Портал Azure, используемый для большинства операций управления Intune.|
|Intune software client (Программный клиент Intune)|Альтернативный способ [управления несколькими компьютерами с Windows](/intune-classic/get-started/choose-how-to-manage-devices) для помощи в выборе подходящего метода.|
|Intune Software Publisher (издателя программного обеспечения Intune)|Средство, используемое для [определения приложений, которые необходимо развернуть и отправить в облачное хранилище](/intune-classic/deploy-use/add-apps).|
|Inventory (Товары)|Используйте для просмотра [оборудования и установленного программного обеспечения](/intune/device-inventory) на управляемых устройствах.|

## <a name="k"></a>K
|||
|-|-|
|Полноэкранный режим|Этот режим, настроенный в составе [профиля ограничения использования устройства](/intune/device-restrictions-configure), позволяет заблокировать устройства. Например, можно настроить устройство розничной торговли для запуска ограниченного набора приложений.|

## <a name="m"></a>M
|||
|-|-|
|Managed Browser|[Приложение для просмотра веб-страниц](/intune/app-configuration-managed-browser), которое можно назначить организации с помощью Intune. Политика управляемого браузера настраивает список разрешений или список блокировок, ограничивающий те веб-сайты, которые могут посетить пользователи управляемого браузера.|
|MDM authority (Центр MDM)|[Центр MDM](/intune/mdm-authority-set) определяет службу управления, у которой есть разрешение на управление набором устройств. Возможные варианты центра управления мобильными устройствами — отдельная служба Intune или Configuration Manager с Intune.|
|Mobile app configuration policy (Политика конфигурации мобильных приложений)|Политика [iOS](/intune/app-configuration-policies-use-ios) или [Android](/intune/app-configuration-policies-use-android), которая позволяет предоставить параметры для совместимых приложений при их запуске, например название организации или адрес сервера.|
|Mobile app provisioning policy (Политика подготовки мобильных приложений)|Политика iOS, помогающая предотвращать истечение срока действия для [профилей подготовки](/intune/app-provisioning-profile-ios) для назначаемых приложений iOS.|
|Управление мобильными приложениями|[Управление мобильными приложениями (MAM)](/intune/app-lifecycle) дает возможность публикации, отправки, настройки, защиты, мониторинга и обновления мобильных приложений для пользователей.
|управление мобильными устройствами|[Управление мобильными устройствами (MDM)](/intune/device-lifecycle) дает возможность регистрации устройств в Intune для последующей подготовки, настройки, мониторинга этих устройств и управления ими.



## <a name="o"></a>O
|||
|-|-|
|OMA-DM|Управление устройствами Open Mobile Alliance. Являющийся отраслевым стандартом протокол управления устройствами, используемый многими изготовителями оборудования для реализации функций управления мобильными устройствами и компьютерами.|
|OMA-URI|Универсальный идентификатор ресурса Open Mobile Alliance. Эти элементы определяют отдельные параметры устройств, соответствующие стандарту OMA-DM. Их можно использовать в [настраиваемых профилях Intune](/intune/custom-settings-configure) при отсутствии подходящих встроенных параметров.|

## <a name="p"></a>P
|||
|-|-|
|Сброс секретного кода|Функция Intune, позволяющая вынудить пользователя выполнить [сброс секретного кода](/intune/device-passcode-reset) на поддерживаемых устройствах.|

## <a name="r"></a>R
|||
|-|-|
|удаленная блокировка;|Функция Intune, позволяющая [заблокировать поддерживаемые устройства](/intune/device-remote-lock), включая те, которые вам не принадлежат.|
|Required install (Обязательная установка)|Если приложение назначено с помощью этого действия, для завершения его установки не требуется [вмешательство пользователя](/intune/apps-deploy). На некоторых платформах может потребоваться подтверждение установки конечным пользователем).|


## <a name="s"></a>S
|||
|-|-|
|Selective wipe (Выборочная очистка)|[Выборочная очистка](/intune/device-company-data-remove) удаляет с устройства только данные организации, включая данные управления мобильными приложениями (MAM), где это возможно, параметры и профили электронной почты. При выборочной очистке личные данные пользователя остаются на устройстве.|
|Загрузка неопубликованного приложения|Действие по установке бизнес-приложения без доступа к нему через магазин приложений.|
|Подписка|Заключенное вами соглашение, которое обеспечивает доступ к клиенту Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Стороннее приложение, работающее с Intune для предоставления [возможности удаленной помощи](/intune/device-profile-android-teamviewer) для устройств Android, управляемых с помощью Intune.|
|Клиент|Один экземпляр службы Intune, к которому вы можете получить доступ с помощью подписки.|
|Terms and conditions (Условия)|Тип политики, который можно назначить для пользователей, содержащий сведения, которые пользователи должны [прочесть и принять](/intune/terms-and-conditions-create), чтобы в дальнейшем использовать корпоративный портал для регистрации и доступа к своей работе.|

## <a name="v"></a>V
|||
|-|-|
|Приложения и книги, приобретенные по корпоративной программе|Некоторые магазины приложений позволяют приобретать сразу несколько лицензий, если приложение или книгу планируется использовать в организации. Intune позволяет управлять приложениями и книгами, [приобретенными по такой программе](/intune/vpp-apps). Вы можете импортировать сведения о лицензии из любого магазина приложений, отслеживать количество использованных лицензий и блокировать возможность установки большего числа копий приложения, чем есть в наличии.|
|VPN profile (Профиль VPN)|Политика, которая назначает [параметры VPN](/intune/vpn-settings-configure) для управляемых устройств, сводя к минимуму объем работ по настройке со стороны конечных пользователей.|

## <a name="w"></a>Вт
|||
|-|-|
|Wi-Fi profile (Профиль Wi-Fi)|Политика, которая назначает устройствам [параметры беспроводной сети](/intune/wi-fi-settings-configure), чтобы позволить пользователям подключаться к корпоративной сети без настройки каких-либо параметров.