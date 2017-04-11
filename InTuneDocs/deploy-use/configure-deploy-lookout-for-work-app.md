---
title: "Развертывание приложения Lookout for Work | Документы Майкрософт"
description: "Настройка и развертывание приложения Lookout for Work для Android."
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: ad1133d17f8d64c79c08437b914ae28e00cae638
ms.lasthandoff: 03/21/2017


---

# <a name="configure-and-deploy-lookout-for-work-app"></a>Настройка и развертывание приложения Lookout for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В этой статье описывается настройка и развертывание приложения Lookout for Work для устройств Android и iOS.

## <a name="android-google-play-store-app"></a>Android (приложение магазина Google Play)

1.    В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) перейдите в раздел **Приложения** и выберите **Добавить приложения**.
2.    На странице **Установка ПО** издателя выберите **Внешняя ссылка** и укажите следующий URL-адрес: https://play.google.com/store/apps/details?id=com.lookout.enterprise.
  >[!NOTE]
  >Не устанавливайте флажок для задания управляемого браузера.

3.    На странице **Описание ПО** заполните следующие поля:
  * **Издатель:** Lookout Mobile Security
  * **Имя:** Lookout for Work
  * **Описание:** Lookout обеспечивает лучшую защиту от угроз мобильных устройств. При установке приложения Lookout на устройстве оно защищает устройство от угроз и будет оповещать вас (и администратора организации) в случае их обнаружения.
  * **Категория:** управление компьютерами

4. После успешного завершения отображается сообщение **Отправка данных в Microsoft Intune выполнена успешно**.

  Когда в консоли Intune вы щелкнете **Приложения**, в списке отобразится приложение **Lookout for Work**. ![Снимок экрана: страница "Приложения" консоли администрирования Intune с приложением Lookout for Work в списке](../media/mtp/lookout-app-listed-intune-console.png)

5. Чтобы развернуть приложение для пользователей, выберите приложение Lookout for Work и нажмите **Управление развертыванием**.

  Необходимо выбрать тех же пользователей, которые были добавлены при задании параметра "Управление регистрацией" в консоли Lookout MTP.  См. шаг 3 в разделе [Настройка службы Lookout MTP в подписке](configure-and-deploy-lookout-for-work-apps.md), где приводятся сведения о добавлении групп пользователей в Lookout MTP.

  >[!IMPORTANT]
  > Мастер развертывания приложений Intune не учитывает группы пользователей Azure AD и использует вместо них группы пользователей Intune. Поэтому необходимо создать группу пользователей Intune на основе группы пользователей Azure AD, зарегистрированной в консоли Lookout MTP, как описано в [этом](plan-your-user-and-device-groups.md) разделе.

6. Выберите вариант **Обязательная установка**, чтобы система требовала от пользователей установить приложение Lookout на устройства.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (версия приложения Lookout с корпоративной подписью)

1. Убедитесь, что на устройстве настроено **Управление iOS**. Инструкции по настройке управления iOS на устройстве см. в статье [Настройка управления устройствами в iOS и Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. **Повторно подпишите** приложение Lookout for Work iOS. Lookout распространяет приложение Lookout for Work iOS за пределами магазина iOS App Store. **Перед распространением приложения** необходимо повторно подписать приложение с сертификатом корпоративного разработчика iOS. Подробные инструкции по повторной подписи приложений Lookout for Work iOS см. в статье [Процесс повторной подписи приложения Lookout for Work iOS](https://personal.support.lookout.com/hc/en-us/articles/114094038714) на сайте Lookout.

3. Включите проверку подлинности Azure Active Directory для пользователей iOS, выполнив следующие действия.
  1.  Выполните вход на [портал управления Azure Active Directory](https://manage.windowsazure.com) и перейдите на страницу приложения.
  2.  Добавьте **Приложение Lookout for Work iOS** в качестве **встроенного клиентского приложения**.
  ![Снимок экрана: диалоговое окно добавления приложений с выбранным параметром встроенного клиентского приложения](../media/mtp/aad-add-app.png)
  3. Замените адрес **com.lookout.enterprise.yourcompanyname** на идентификатор пакета клиента, выбранный во время подписи пакета IPA.
  4.  Добавьте дополнительный URI перенаправления: **&lt;companyportal://code/>**, за которым указывается оригинальный URI перенаправления, закодированный как URL-адрес.
  5.  Добавьте **Делегированные разрешения** в приложение.

  Дополнительные сведения см. в статье [Настройка встроенного клиентского приложения](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Передайте повторно подписанный IPA-файл, как описано в разделе [Добавление приложения для мобильных устройств в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Установите минимальную версию ОС равную iOS 8.0 или более поздней версии.

  ![Снимок экрана: страница приложений в консоли администрирования Intune с приложением Lookout for Work в списке приложений](../media/mtp/ios-app-uploaded-intune.png)

5. Создайте политику конфигурации управляемого приложения, как описано в разделе [Настройка приложений iOS с помощью политик конфигурации мобильных приложений в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Снимок экрана: мастер создания политики с выбранной политикой конфигурации приложения для iOS 8.0 или более поздней версии](../media/mtp/ios-app-config.png)

6. **Чтобы развернуть приложение для пользователей**, выберите приложение Lookout for Work и нажмите **Управление развертыванием**.

  Необходимо выбрать тех же пользователей, которые были добавлены в разделе Enrollment Management (Управление регистрацией) в консоли Lookout.  См. шаг 3 в разделе [Настройка подписки службы Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps), где приводятся сведения о добавлении групп пользователей в Lookout MTP.

  >[!IMPORTANT]
  > Мастер развертывания приложений Intune не обладает информацией о группах пользователей Azure AD и вместо этого использует группы пользователей Intune. Поэтому вам необходимо создать группу пользователей Intune на основе группы пользователей Azure AD, зарегистрированной в консоли Lookout, как описано в [этой](plan-your-user-and-device-groups.md) статье.

  Выберите вариант **Обязательная установка**, чтобы система требовала от пользователей установить приложение Lookout на устройства.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Что происходит при открытии развернутого приложения на устройстве

Когда пользователь откроет приложение Lookout for Work на устройстве, ему будет предложено активировать приложение и выбрать вариант входа с помощью Azure Active Directory. Подробное пошаговое руководство с процедурой для конечных пользователей можно найти в следующих разделах:

* [Вам предложено установить Lookout for Work на устройстве с Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android).

* [Вам требуется устранить угрозу, обнаруженную Lookout for Work на устройстве Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Дальнейшие действия
* [Создание политики соответствия устройств Lookout в Intune](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)

