---
title: "Включение службы защиты мобильных устройств от угроз Skycure в Intune | Документы Майкрософт"
description: "Включение службы защиты мобильных устройств от угроз Skycure в классической консоли Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Включение службы защиты мобильных устройств от угроз Skycure в Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Чтобы включить в Intune подключение защиты мобильных устройств от угроз Skycure, требуется ранее настроенный [в консоли Skycure соединитель Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Включение подключения Skycure в Intune

1.  Перейдите в [классическую консоль Intune](https://manage.microsoft.com/) и введите свои учетные данные.

2.  Выберите пункты **Администратор** &gt; **Интеграция со службами сторонних производителей**, затем выберите **Состояние Skycure** и включите **Синхронизацию с MTD** с помощью кнопки-переключателя.

    ![Включение переключателя Skycure в классической консоли Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> До создания правил политики соответствия и настройки политики условного доступа нужно настроить приложения Skycure. Это гарантирует, что приложение будет готово к работе и доступно для установки конечными пользователями, прежде чем они смогут получать доступ к электронной почте или другим корпоративным ресурсам.

Это завершит настройку интеграции Skycure и Intune в консоли администрирования Intune. Дальнейшие действия, необходимые для реализации этого решения, включают развертывание приложений Skycure for Work и настройку политики соответствия.

## <a name="next-steps"></a>Дальнейшие действия

[Создание политики соответствия защиты мобильных устройств от угроз Skycure](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
