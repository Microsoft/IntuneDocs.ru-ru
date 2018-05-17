---
title: Загрузка политики конфигурации приложения Skycure для iOS
description: Загрузите политику конфигурации приложения Skycure для iOS, чтобы использовать ее с приложением Skycure для iOS, развернутым для конечных пользователей.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f3cf3b2b18eeadf6779b7a8e96d75e569e6e3be
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Загрузка политики конфигурации приложения Skycure для iOS

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Подготовка к работе

Для выполнения следующих шагов нужно войти в консоль управления Skycure.

> [!TIP] 
> При использовании Microsoft Internet Explorer 11 или Microsoft Edge может потребоваться открыть консоль управления Skycure в режиме InPrivate.

## <a name="to-download-the-ios-app-configuration-policy"></a>Скачивание политики конфигурации приложения для iOS

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

    ![Вход в консоль управления Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Имя администратора Skycure — это адрес электронной почты, который должен быть действительной учетной записью в Azure Active Directory; в противном случае войти не удастся. Skycure использует Azure Active Directory для проверки подлинности администратора с помощью единого входа (SSO).

3.  Последовательно выберите пункты **Параметры** &gt; **Интеграция устройств управления** &gt; **Выбор интеграции EMM**, выберите **Microsoft Intune**, затем сохраните свой выбор.

2.  Щелкните ссылку **Файлы установки интеграции** и сохраните созданный \*ZIP-файл. ZIP-файл содержит файл **skycure\_configuration.plist**, который будет использоваться для создания политики конфигурации приложения для iOS н классическом портале Intune.

![Файлы установки интеграции Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Дальнейшие шаги

[Добавление приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
