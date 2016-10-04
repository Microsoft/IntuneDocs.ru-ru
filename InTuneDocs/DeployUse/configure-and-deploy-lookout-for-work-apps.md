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
ms.sourcegitcommit: ceaeba74f8671caf4125252fce02fd06752c3fe8
ms.openlocfilehash: 46a6b836e344c9cf876d633f868753a49c0cd440


---

# Настройка и развертывание приложения Lookout for Work
В этой статье описывается настройка и развертывание приложения Lookout for Work для зарегистрированных устройств под управлением Android 4.1 и более поздней версии.

* **Шаг 1.** В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) перейдите в раздел **Приложения** и выберите **Добавить приложения**.   
* **Шаг 2.** На странице **Установка ПО** издателя выберите **Внешняя ссылка** и укажите следующий URL-адрес: https://play.google.com/store/apps/details?id=com.lookout.enterprise.
>[!NOTE]
>Не устанавливайте флажок для задания управляемого браузера.

* **Шаг 3.** На странице **Описание ПО** заполните следующие поля:
  * **Издатель:** Lookout Mobile Security
  * **Имя:** Lookout for Work
  * **Описание:** Lookout обеспечивает лучшую защиту от угроз мобильных устройств. Приложение Lookout защищает устройство от угроз и оповещает вас и администратора организации об обнаруженных угрозах.
  * **Категория:** управление компьютерами
* **Шаг 4.** После успешного завершения отображается сообщение **Отправка данных в Microsoft Intune выполнена успешно**.

Если щелкнуть **Приложения** в консоли администрирования Intune, вы увидите приложение Lookout for Work в списке ![снимок экрана страницы "Приложения" консоли администрирования Intune с приложением Lookout for Work в списке](../media/mtp/lookout-app-listed-intune-console.png)

**Чтобы развернуть приложение для пользователей**, выберите приложение Lookout for Work (показанное на снимке выше) и щелкните **Управление развертыванием**.

Необходимо выбрать тех же пользователей, которые были добавлены в разделе Enrollment Management (Управление регистрацией) в консоли Lookout.  См. шаг 3 в разделе [Настройка службы защиты от угроз на устройствах Lookout в подписке](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp), где приводится информация о добавлении групп пользователей в Lookout MTP.
>[!IMPORTANT]
> Мастер развертывания приложений Intune не обладает информацией о группах пользователей Azure AD и вместо этого использует группы пользователей Intune. Поэтому вам необходимо создать группу пользователей Intune на основе группы пользователей Azure AD, зарегистрированной в консоли Lookout, как описано в [этой](plan-your-user-and-device-groups.md) статье.

Выберите вариант **Обязательная установка**, чтобы система требовала от пользователей установить приложение Lookout на устройства.


Если для развертывания выбран вариант **Обязательная установка**, Intune будет принудительно устанавливать Lookout for Work на устройстве.   

Когда пользователь откроет приложение Lookout for Work на устройстве, ему будет предложено активировать приложение и выбрать вариант входа с помощью Azure Active Directory. Подробное пошаговое руководство с процедурой для конечных пользователей можно найти в следующих разделах:

* [Вам предложено установить Lookout for Work на устройстве Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Вам требуется устранить угрозу, обнаруженную Lookout for Work на устройстве Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Дальнейшие шаги
* [Включение правила защиты устройства от угроз в политике соответствия](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO4-->


