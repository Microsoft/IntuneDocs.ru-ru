---
title: "Загрузка политики конфигурации приложения Skycure для iOS с помощью Intune"
titlesuffix: Azure portal
description: "Загрузка политики конфигурации приложения Skycure для iOS с помощью Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 296d5545530e8001c0648bafac3101b94f45529d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Загрузка политики конфигурации приложения Skycure для iOS

## <a name="before-you-begin"></a>Подготовка к работе

Для выполнения следующих шагов нужно войти в консоль управления Skycure.

> [!TIP] 
> При использовании Microsoft Internet Explorer 11 или Edge может потребоваться открыть консоль управления Skycure в режиме InPrivate.

## <a name="to-download-the-ios-app-configuration-policy"></a>Скачивание политики конфигурации приложения для iOS

1.  Перейдите в [Консоль управления Skycure](https://aad.skycure.com).

2.  Введите ваши **учетные данные администратора Skycure** и нажмите кнопку **Продолжить**.

    ![Вход в консоль управления Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Имя администратора Skycure — это адрес электронной почты, который должен быть действительной учетной записью в Azure Active Directory; в противном случае войти не удастся. Skycure использует Azure Active Directory для проверки подлинности администратора с помощью единого входа (SSO).

3.  Последовательно выберите пункты **Параметры** &gt; **Интеграция устройств управления** &gt; **Выбор интеграции EMM**, выберите **Microsoft Intune**, затем сохраните свой выбор.

4.  Щелкните ссылку **Файлы установки интеграции** и сохраните созданный \*ZIP-файл. ZIP-файл содержит файл **skycure\_configuration.plist**, который будет использоваться для создания политики конфигурации приложения для iOS н классическом портале Intune.

![Файлы установки интеграции Skycure](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Дальнейшие действия

[Добавление и назначение приложений Skycure, Microsoft Authenticator и политики конфигурации приложения для iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)
