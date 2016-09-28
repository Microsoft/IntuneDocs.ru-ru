---
title: "Развертывание приложения Lookout for Work | Microsoft Intune"
description: "Настройка и развертывание приложения Lookout for Work для Android."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Настройка и развертывание приложения Lookout for Work
В этом выпуске поддерживается приложение Lookout for Work на устройствах под управлением Android 4.1 и более поздних версий.
## Android
В этой статье описывается настройка и развертывание приложения Lookout for Work для устройств Android, зарегистрированных в Intune.  
* Шаг 1. В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) перейдите в раздел **Приложения** и выберите **Добавить приложения**.   
* Шаг 2. На странице **Установка ПО** издателя выберите **Внешняя ссылка** и укажите следующий URL-адрес: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Не устанавливайте флажок для задания управляемого браузера.

* Шаг 3. На странице **Описание ПО** заполните следующие поля.
  * **Издатель:** Lookout Mobile Security
  * **Имя:** Lookout for Work
  * **Описание:** Lookout обеспечивает лучшую защиту от угроз мобильных устройств. При установке приложения Lookout на устройстве оно защищает устройство от угроз и будет оповещать вас (и администратора организации) в случае их обнаружения.
  * **Категория:** управление компьютерами
* Шаг 4. После успешного завершения отображается сообщение **Отправка данных в Microsoft Intune выполнена успешно**.

Теперь в консоли Intune при щелчке элемента **Приложения** в списке будет отображаться приложение Lookout for Work ![ снимок экрана страницы "Приложения" консоли администрирования Intune с приложением Lookout for Work в списке](../media/mtp/lookout-app-listed-intune-console.png)

Шаг 5. На этом этапе Intune может выполнить автоматическую установку приложения Lookout for Work для Android.   Можно развернуть приложение для пользователей, выбрав приложение Lookout for Work, показанное на экране выше, и щелкнув **Управление развертыванием**.

Необходимо выбрать тех же пользователей, которые были добавлены при задании параметра "Управление регистрацией" в консоли Lookout MTP.  См. шаг 3 в разделе [Настройка службы Lookout MTP в подписке](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp), где приводятся сведения о добавлении групп пользователей в Lookout MTP.
>[!IMPORTANT]
> Мастер развертывания приложений Intune не учитывает группы пользователей Azure AD и использует вместо них группы пользователей Intune. Поэтому необходимо создать группу пользователей Intune на основе группы пользователей Azure AD, зарегистрированной в консоли Lookout MTP, как описано в [этом](plan-your-user-and-device-groups.md) разделе.

Шаг 6. Выберите вариант **Обязательная установка**, чтобы настроить обязательную установку приложения Lookout на устройствах пользователей.

### Активация устройства
Если для развертывания выбран вариант **Обязательная установка**, Intune будет принудительно устанавливать Lookout for Work на устройстве.   

Когда пользователь откроет приложение Lookout for Work на устройстве, ему будет предложено активировать приложение и выбрать вариант входа с помощью Azure Active Directory. Подробное пошаговое руководство с процедурой для конечных пользователей можно найти в следующих разделах:

* [Вам предложено установить Lookout for Work на устройстве Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Вам требуется устранить угрозу, обнаруженную Lookout for Work на устройстве Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Дальнейшие шаги
* [Включение правила защиты устройства от угроз в политике соответствия](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


