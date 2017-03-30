---
title: "Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS | Документы Майкрософт"
description: "Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS в классической консоли Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 9f09a070ec120064bdd64bfb05a39ec9e484606c
ms.lasthandoff: 03/21/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Подготовка к работе

-   Следующие действия необходимо выполнить в [классический консоли Intune](https://manage.microsoft.com/).

-   Используйте ту же учетную запись Azure AD, которая ранее была настроена в консоли управления Skycure. Это должна быть учетная запись для входа в классическую консоль Intune.

-   Убедитесь, что вы знакомы со следующими процессами.

    -   [Развертывание приложения с помощью Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Развертывание политики конфигурации приложения для iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS

1.  В классической консоли Intune выберите пункты **Приложения** &gt; **Приложения** для просмотра списка приложений, которыми можно управлять.

2.  Выберите следующие приложения.

    а.  Microsoft Authenticator

    b.  Приложение Skycure для Android

    в.  Приложение Skycure для iOS

       ![Классическая консоль Intune, все приложения для развертывания](../media/mtp/skycure-deploy-app-1.png)

3.  Выберите **Управление развертываниями**, выберите группу безопасности Azure AD с пользователями Skycure, а затем нажмите кнопку **Далее**.

4.  На странице **Действие развертывания** выберите параметр **Требуемая установка** в раскрывающемся списке **Утверждение**, а затем нажмите кнопку **Далее**.

    ![Классическая консоль Intune, действие развертывания](../media/mtp/skycure-deploy-app-2.png)

5.  На странице **Профиль VPN** выберите параметр **Нет** в раскрывающемся списке **Политика VPN**, а затем нажмите кнопку **Далее**.

6.  На странице **Конфигурация мобильного приложения** выберите ранее созданную политику приложения для iOS в раскрывающемся списке **Политика конфигурации приложения**, а затем нажмите кнопку **Готово**.

    ![Классическая консоль Intune, конфигурация мобильного приложения](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Дальнейшие действия

[Настройка интеграции Skycure и Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

