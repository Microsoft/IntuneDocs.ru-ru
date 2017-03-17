---
title: "Сброс секретного кода на веб-сайте корпоративного портала | Документы Майкрософт"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: f293901d3865f0b10ed876e83b151cf59a046cba
ms.openlocfilehash: 68725bb63ae2750e89a03c16027f8b4fd9111255
ms.lasthandoff: 02/24/2017


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Сброс секретного кода устройства на корпоративном портале

В случае утери ПИН-кода или пароля для устройства, зарегистрированного в Intune, можно воспользоваться [веб-сайтом корпоративного портала](http://portal.manage.microsoft.com), чтобы сбросить его. Веб-сайт корпоративного портала можно использовать для управления компьютерами и устройствами, зарегистрированными в Intune. На этом веб-сайте доступно большинство тех задач, которые можно выполнить с помощью приложения корпоративного портала.

> [!NOTE]
> Возможно, на корпоративном портале вы не видите кнопку **Сбросить секретный код**. В этом случае за помощью нужно обратиться к ИТ-администратору через корпоративный портал.

Сброс секретного кода

1.    На [веб-сайте корпоративного портала](http://portal.manage.microsoft.com) нажмите кнопку __меню__ ![Небольшое изображение кнопки меню, три параллельных горизонтальных линии](/Intune/whats-new/media/CP_hamburger_menu.png), а затем выберите __Мои устройства__.

2. На странице __Мои устройства__ выберите устройство, секретный код которого необходимо сбросить.

  ![Снимок страницы "Мои устройства" с несколькими неидентифицированными устройствами и баннером, который предлагает зарегистрировать устройства, которых нет в списке, или идентифицировать устройства, которые не были идентифицированы.](./media/macOS_enroll_002_tap_here_banner.png)

3.    Появится всплывающее окно со сведениями об устройстве. Нажмите кнопку **Сбросить секретный код**.

    ![Все действия для выбранного устройства на веб-сайте корпоративного портала, включая следующие: "Переименовать", "Удалить", "Сбросить устройство", "Сбросить секретный код" и "Удаленная блокировка". ](./media/iwp-screen-with-all-options.png)

4.  Появится окно с подтверждением сброса секретного кода, в котором также будет указано, что после сброса секретного кода будет выполнен автоматический выход из системы на устройстве. После этого вам потребуется подождать в течение пяти минут перед повторной попыткой входа.

  ![Окно с подтверждением сброса секретного кода, в котором также будет указано, что после сброса секретного кода будет выполнен автоматический выход из системы на устройстве. Пользователь может нажать кнопки "Выйти из системы" или "Отмена".](./media/iwp-reset-passcode-popup.png)

4.  При нажатии кнопки **Выйти из системы** вы получите последнее предупреждение об отключении секретного кода на устройстве. Если у вас с собой нет устройства, не отключайте секретный код, так как без него любой человек, у которого окажется ваше устройство, получит доступ к большей части данных на этом устройстве, как личных, так и корпоративных.

  ![Второе предупреждение о сбросе и отключении секретного кода на устройстве. Также рекомендуется задать новый секретный код в параметрах устройства.](./media/iwp-reset-passcode-2nd-popup.png)


Так как на различных устройствах используются различные типы секретных кодов, обратитесь к таблице ниже, чтобы узнать, как сброс секретного кода может повлиять на ваше устройство. 

    |Тип устройства|Что происходит при сбросе|
    |------------|-----------|
    |Android|Удаляется существующий секретный код и создается временный, состоящий из букв и цифр.|
    |iOS|Удаляется существующий секретный код, но временный не создается. Если вы используете сканер отпечатков пальцев Touch ID для разблокировки устройства или покупок, потребуется снова настроить его.|
    |Windows 10 Mobile|Удаляется существующий секретный код и создается временный, состоящий из букв и цифр. Распознавание лиц Windows Hello для входа на устройство по-прежнему будет поддерживаться.|
    |Windows Phone 8.1|Удаляется существующий секретный код и создается временный, состоящий из цифр.|

    5.  Разблокируйте устройство и задайте новый секретный код или измените временный в разделе **Настройки** устройства.

    Для просмотра уведомления об успешном сбросе пароля щелкните флаг уведомления в верхней правой части веб-сайта корпоративного портала.

По-прежнему нужна помощь? Обратитесь к ИТ-администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).
