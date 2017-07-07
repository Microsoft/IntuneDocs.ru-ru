---
title: "Добавление приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS"
description: "Добавление приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS в классической консоли Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 425b86e92281bb6e3657a6c806be269ccae94311
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Добавление приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Необходимо использовать Intune для добавления и развертывания приложений Skycure, чтобы конечные пользователи могли получать уведомления при определении угроз в их мобильных устройствах и рекомендации по устранению этих угроз.

Кроме того, вам требуется [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), чтобы идентификаторы пользователей проверялись в Azure AD, и политика конфигурации приложений для iOS, которая сообщает приложению Skycure для iOS о необходимости использования Intune и единого входа Azure, чтобы пользователям не надо было вводить имя и пароль при каждом входе в приложение Skycure.

## <a name="before-you-begin"></a>Подготовка к работе

-   Следующие действия необходимо выполнить в [классической консоли Intune](https://manage.microsoft.com/).

-   Используйте ту же учетную запись Azure AD, которая ранее была настроена в консоли управления Skycure. Это должна быть учетная запись для входа в классическую консоль Intune.

-   У вас должен быть готовый к использованию файл интеграции Skycure. Это ранее скачанный из консоли управления Skycure ZIP-файл, который содержит файл **skycure\_configuration.plist** с параметрами политики конфигурации приложения для iOS.

-   Убедитесь, что вы знакомы со следующими процессами.

    -   [Добавление приложения в Intune](/intune-classic/deploy-use/add-apps).

    -   [Добавление политики конфигурации приложения для iOS в Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>Добавление приложения Skycure для Android

1.  В классической консоли Intune выберите пункты **Приложения** &gt; **Добавить приложения** для запуска издателя ПО Intune и нажмите кнопку **Далее**.

2.  На странице **Настройка ПО**  выберите пункт **Внешняя ссылка** и вставьте [URL-адрес приложения Skycure для Android](https://play.google.com/store/apps/details?id=com.skycure.skycure) в поле **Укажите URL-адрес**.

    !["Издатель ПО Intune", "Укажите URL-адрес"](../media/mtp/skycure-add-apps-1.png)

3.  На странице **Описание ПО** укажите **Издателя**, **Название** и **Описание**, выберите параметр **Отображать это приложение как рекомендуемое и выделить его на портале организации** и нажмите кнопку **Далее**.

    !["Издатель ПО Intune", "Описание ПО"](../media/mtp/skycure-add-apps-2.png)

4.  Нажмите кнопку **Отправить**, затем — **Закрыть**.

## <a name="to-add-the-skycure-app-for-ios"></a>Добавление приложения Skycure для iOS

1.  В классической консоли Intune выберите пункты **Приложения** &gt; **Добавить приложения** для запуска издателя ПО Intune и нажмите кнопку **Далее**.

2.  На странице **Настройка ПО**  выберите **Управляемое приложение iOS из магазина App Store** и вставьте [URL-адрес приложения Skycure для iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) в поле **Укажите URL-адрес**.

    !["Издатель ПО Intune", "Управляемое приложение iOS"](../media/mtp/skycure-add-apps-3.png)

3.  На странице **Описание ПО** укажите **Издателя**, **Название** и **Описание**, выберите параметр **Отображать это приложение как рекомендуемое и выделить его на портале организации** и нажмите кнопку **Далее**.

    ![Параметры издателя ПО Intune](../media/mtp/skycure-add-apps-4.png)

4.  На странице **Требования** выберите значение **Любой** в поле **Тип мобильного устройства**, затем нажмите кнопку **Далее**.

5.  Нажмите кнопку **Отправить**, затем — **Закрыть**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Добавление приложения Microsoft Authenticator для iOS

1.  В классической консоли Intune выберите пункты **Приложения** &gt; **Добавить приложения** для запуска издателя ПО Intune и нажмите кнопку **Далее**.

2.  На странице **Настройка ПО**  выберите **Управляемое приложение iOS из магазина App Store** и вставьте [URL-адрес приложения Microsoft Authenticator для iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) в поле **Укажите URL-адрес**.

    !["Издатель ПО Intune", "Управляемое приложение iOS 2"](../media/mtp/skycure-add-apps-5.png)

3.  На странице **Описание ПО** укажите **Издателя**, **Название** и **Описание**, выберите параметр **Отображать это приложение как рекомендуемое и выделить его на портале организации** и нажмите кнопку **Далее**.

    !["Издатель ПО Intune", "Управляемое приложение iOS 3"](../media/mtp/skycure-add-apps-6.png)

4.  На странице **Требования** выберите значение **Любой** в поле **Тип мобильного устройства**, затем нажмите кнопку **Далее**.

5.  Нажмите кнопку **Отправить**, затем — **Закрыть**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Добавление политики настройки приложения Skycure для iOS

1.  В классической консоли Intune выберите пункты **Политика** &gt; **Обзор &gt; Добавить политику**.

2.  В списке политик разверните узел **iOS**, выберите пункт **Политика настройки мобильного приложения (iOS 8.0 и более поздние версии)** и выберите команду **Создать политику**.

    ![Политика настройки приложения для iOS](../media/mtp/skycure-add-apps-7.png)

3.  В разделе **Общее** страницы **Создание политики** введите имя и необязательное описание политики настройки приложения для iOS.

    а.  Откройте файл **skycure\_configuration.plist** в текстовом редакторе (например, Блокноте), скопируйте содержимое и вставьте его в поле **Политика настройки мобильного приложения**, выберите команду **Проверить**, а затем — **Сохранить политику**.

       ![Политика настройки приложения для iOS 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Дальнейшие действия

[Развертывание приложений Skycure, Microsoft Authenticator и политики настройки приложения для iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
