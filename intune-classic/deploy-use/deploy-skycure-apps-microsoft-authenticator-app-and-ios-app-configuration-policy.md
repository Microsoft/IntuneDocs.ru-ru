---
title: Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS
description: Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS на классическом портале Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d28cf8f4dca89b99deb32ce054db6b04e02edae6
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Подготовка к работе

-   Следующие действия необходимо выполнить на [классическом портале Intune](https://manage.microsoft.com/).

-   Используйте ту же учетную запись Azure AD, которая ранее была настроена в консоли управления Skycure. Это должна быть учетная запись для входа на классический портал Intune.

-   Убедитесь, что вы знакомы со следующими процессами.

    -   [Развертывание приложения с помощью Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Развертывание политики конфигурации приложения для iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Развертывание приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS

1.  На классическом портале Intune выберите пункты **Приложения** &gt; **Приложения** для просмотра списка приложений, которыми можно управлять.

2.  Выберите следующие приложения.

    a.  Microsoft Authenticator

    b.  Приложение Skycure для Android

    c.  Приложение Skycure для iOS

       ![Классический портал Intune: все приложения для развертывания](../media/mtp/skycure-deploy-app-1.png)

3.  Выберите **Управление развертываниями**, выберите группу безопасности Azure AD с пользователями Skycure, а затем нажмите кнопку **Далее**.

4.  На странице **Действие развертывания** выберите параметр **Требуемая установка** в раскрывающемся списке **Утверждение**, а затем нажмите кнопку **Далее**.

    ![Классический портал Intune: действие развертывания](../media/mtp/skycure-deploy-app-2.png)

5.  На странице **Профиль VPN** выберите параметр **Нет** в раскрывающемся списке **Политика VPN**, а затем нажмите кнопку **Далее**.

6.  На странице **Конфигурация мобильного приложения** выберите ранее созданную политику приложения для iOS в раскрывающемся списке **Политика конфигурации приложения**, а затем нажмите кнопку **Готово**.

    ![Классический портал Intune: конфигурация мобильного приложения](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Дальнейшие шаги

[Настройка интеграции Skycure и Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
