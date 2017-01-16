---
title: "Включение Lookout MTP в Intune | Документы Майкрософт"
description: "Включение защиты от угроз на мобильных устройствах Lookout MTP в консоли администрирования Intune"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b83d06ecbe6e202bf022444c288e0866b3507c6
ms.openlocfilehash: 153e446e49beff24b9c7404d15592d88478b89da


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Включение подключения Lookout MTP в консоли администрирования Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Чтобы включить подключение защиты от опасных угроз (MTP) Lookout, требуется уже настроенный соединитель Intune в консоли Lookout.  Если вы еще этого не сделали, выполните действия, описанные в статье [Настройка службы Lookout MTP в подписке](set-up-your-subscription-with-lookout-mtp.md).

Чтобы включить подключение Lookout MTP в Intune, на странице **Администрирование** в [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Интеграция сторонних служб**. Выберите **Состояние Lookout** и включите **синхронизацию с MTP** с помощью переключателя.

![снимок экрана страницы синхронизации с Lookout с выделенной кнопкой переключателя](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Вам **потребуется** настроить приложение Lookout for Work до создания правил политики соответствия и настройки политики условного доступа. Это гарантирует, что приложение будет готово к работе и доступно для установки конечными пользователями, прежде чем они смогут получать доступ к электронной почте или другим корпоративным ресурсам.

Это завершит настройку интеграции Lookout и Intune в консоли администрирования Intune.  Дальнейшие действия, необходимые для реализации этого решения, включают развертывание [приложений Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) и настройку политики [соответствия](enable-device-threat-protection-rule-in-compliance-policy.md).


## <a name="next-steps"></a>Дальнейшие действия
[Настройка приложения Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO4-->


