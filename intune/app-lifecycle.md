---
title: "Общие сведения о жизненном цикле приложений"
description: "Сведения о жизненном цикле приложений, управляемых Intune, начиная с добавления вплоть до прекращения использования."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf505bec8a07923db78a870e4d7bfd64660e681c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Общие сведения о жизненном цикле приложений

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Жизненный цикл приложений Intune начинается с добавления приложений. Затем они проходят дополнительные этапы вплоть до своего удаления.

![Жизненный цикл приложений](./media/app-lifecycle.png "жизненный цикл приложений Intune")

## <a name="add"></a>Add

Первым этапом в развертывании приложений является добавление в Intune приложений, которые будут назначены и будут находиться под управлением системы. Несмотря на то, что вы можете работать со множеством разных типов приложений, основные процедуры всегда одинаковы. Intune позволяет добавлять приложения для [зарегистрированных устройств](apps-add.md) ([классический портал](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) или для [компьютеров Windows, которыми вы управляете с помощью клиентского ПО Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Развернуть

Приложение, добавленное в Intune, можно [назначить пользователям и управляемым устройствам](apps-deploy.md) ([классический портал](/intune-classic/deploy-use/deploy-apps)). Intune упрощает этот процесс, и после развертывания приложения можно [отследить успех](apps-monitor.md) ([классический портал](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) развертывания из консоли администрирования Intune. Кроме того, в некоторых магазинах приложений, таких как магазины [Apple](vpp-apps-ios.md) ([классический портал](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) и [Windows](windows-store-for-business.md) ([классический портал](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), можно приобрести лицензии на приложения в рамках корпоративных закупок. Intune обеспечивает синхронизацию данных с этими магазинами, чтобы вы смогли развертывать приложения и отслеживать использование лицензий для этих типов приложений прямо из консоли администрирования Intune.

## <a name="configure"></a>Настройка

В рамках жизненного цикла приложений регулярно выходят новых версий приложений. Intune предоставляет инструменты, сильно упрощающие [обновление развернутых приложений](apps-add.md) ([классический портал](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) до более новой версии. Кроме того, вы можете настроить дополнительные функциональные возможности для некоторых приложений.
- В [политиках конфигурации приложений iOS](app-configuration-policies-use-ios.md) ([классический портал](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) указываются параметры для совместимых iOS-приложений, используемых при работе приложения. Например, приложение может потребовать задания определенных параметров фирменной символики или ввода имени сервера, к которому оно будет подключено.
- [Политики Managed Browser](app-configuration-managed-browser.md) ([классический портал](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) используются для настройки параметров браузера Intune Managed Browser, который заменяет браузер устройств по умолчанию и позволяет ограничить веб-сайты, доступные пользователям.

## <a name="protect"></a>Защита

Intune предоставляет множество способов защиты данных в приложениях. Вот основные методы.
- [Условный доступ](conditional-access.md) ([классический портал](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) контролирует доступ к почте и другим службам на основе указанных условий. Условия включают типы устройств или соответствие [развернутой политике соответствия устройств требованиям](device-compliance.md) ([классический портал](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)).
- [Политики защиты приложений](app-protection-policy.md) ([классический портал](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) работают с отдельными приложениями для защиты используемых в них данных компании. Например, вы можете ограничить копирование данных между неуправляемыми и управляемыми приложениями или запретить выполнение приложений на устройствах со снятым ограничением на доступ к файловой системе или с полученными правами суперпользователя.

## <a name="retire"></a>Прекратить использование

В конечном счете, скорее всего, развернутые приложения устареют и их потребуется удалить. Intune упрощает [снятие приложений с учета](device-management.md) ([классический портал](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
