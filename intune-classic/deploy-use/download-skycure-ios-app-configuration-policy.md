---
title: "Загрузка политики конфигурации приложения Skycure для iOS"
description: "Загрузите политику конфигурации приложения Skycure для iOS, чтобы использовать ее с приложением Skycure для iOS, развернутым для конечных пользователей."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 3159985bfbaec40899dd58766e214daa672ee6d4
ms.contentlocale: ru-ru
ms.lasthandoff: 06/08/2017


---

# <a name="download-skycure-ios-app-configuration-policy"></a>Загрузка политики конфигурации приложения Skycure для iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Подготовка к работе

Для выполнения следующих шагов нужно войти в консоль управления Skycure.

> [!TIP] 
> При использовании Microsoft Internet Explorer 11 или Edge может потребоваться открыть консоль управления Skycure в режиме InPrivate.

## <a name="to-download-the-ios-app-configuration-policy"></a>Скачивание политики конфигурации приложения для iOS

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

    ![Вход в консоль управления Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Имя администратора Skycure — это адрес электронной почты, который должен быть действительной учетной записью в Azure Active Directory; в противном случае войти не удастся. Skycure использует Azure Active Directory для проверки подлинности администратора с помощью единого входа (SSO).

3.  Последовательно выберите пункты **Параметры** &gt; **Интеграция устройств управления** &gt; **Выбор интеграции EMM**, выберите **Microsoft Intune**, затем сохраните свой выбор.

2.  Щелкните ссылку **Файлы установки интеграции** и сохраните созданный \*ZIP-файл. ZIP-файл содержит файл **skycure\_configuration.plist**, который будет использоваться для создания политики конфигурации приложения для iOS в классической консоли Intune.

![Файлы установки интеграции Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Дальнейшие действия

[Добавление приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

