---
title: "Включение Lookout MTP в Intune"
description: "Включение защиты от угроз на мобильных устройствах Lookout MTP в консоли администрирования Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f34697140a287d41203d1bad5df59250f07d08ce
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Включение подключения Lookout MTP на классическом портале Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Чтобы включить в Intune подключение защиты мобильных устройств от угроз Lookout, требуется ранее настроенный в консоли Lookout соединитель Intune.  Если вы еще этого не сделали, выполните действия, описанные в статье [Настройка подписки для службы защиты мобильных устройств от угроз Lookout](setup-your-lookout-mtd-subscription.md).

Чтобы включить подключение Lookout MTP в Intune, на странице **Администрирование** в [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Интеграция сторонних служб**. Выберите **Состояние Lookout** и включите **синхронизацию с MTP** с помощью переключателя.

![снимок экрана страницы синхронизации с Lookout с выделенной кнопкой переключателя](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Вам **потребуется** настроить приложение Lookout for Work до создания правил политики соответствия и настройки политики условного доступа. Это гарантирует, что приложение будет готово к работе и доступно для установки конечными пользователями, прежде чем они смогут получать доступ к электронной почте или другим корпоративным ресурсам.

Это завершит настройку интеграции Lookout и Intune в консоли администрирования Intune.  Дальнейшие действия для реализации этого решения включают развертывание политики [приложений Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Дальнейшие действия
[Настройка приложения Lookout for Work ](/intune-classic/deploy-use/device-threat-protection-apps)
