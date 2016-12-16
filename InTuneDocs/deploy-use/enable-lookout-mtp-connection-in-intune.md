---
title: "Включение Lookout MTP в Intune | Microsoft Intune"
description: "Включение защиты от угроз на мобильных устройствах Lookout MTP в консоли администрирования Intune"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 1bef6c15387309e1b36bc85758ca699acd54fdd0


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Включение подключения Lookout MTP в консоли администрирования Intune
В этом разделе показано, как включить подключение Lookout MTP в Intune. Перед выполнением этого шага соединитель Intune уже должен быть настроен в консоли Lookout.  Если вы еще этого не сделали, выполните действия, описанные в статье [Настройка службы Lookout MTP в подписке](set-up-your-subscription-with-lookout-mtp.md).

Чтобы включить подключение Lookout MTP в Intune, на странице **Администрирование** в [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Интеграция сторонних служб**. Выберите **Состояние Lookout** и включите **синхронизацию с MTP** с помощью переключателя.

![снимок экрана страницы синхронизации с Lookout с выделенной кнопкой переключателя](../media/mtp/lookout-intune-synchronization.png)

Это завершит настройку интеграции Lookout и Intune в консоли администрирования Intune.  Дальнейшие действия, необходимые для реализации этого решения, включают развертывание [приложений Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) и настройку политики [соответствия](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> Вам **потребуется** настроить приложение Lookout for Work до создания правил политики соответствия и настройки политики условного доступа. Это гарантирует, что приложение будет готово к работе и доступно для установки конечными пользователями, прежде чем они смогут получать доступ к электронной почте или другим корпоративным ресурсам.
## <a name="next-steps"></a>Дальнейшие действия
[Настройка приложения Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO2-->


