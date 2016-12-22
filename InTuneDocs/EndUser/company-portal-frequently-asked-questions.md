---
title: "Что такое корпоративный портал? | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3891d0389df3526ea328fc2952e3d181b1e766c0
ms.openlocfilehash: a0424ada754a210fb34acd49cf47d1c457ed86af


---

# <a name="about-the-company-portal"></a>О корпоративном портале

## <a name="what-is-the-company-portal-and-what-can-you-do-with-it"></a>Что такое корпоративный портал и для чего он нужен?
Корпоративный портал Microsoft Intune предоставляет доступ к корпоративным или учебным данным и приложениям. Доступ к корпоративному порталу можно получить двумя способами:

- Установив приложение корпоративного портала на устройство. Обычно приложение корпоративного портала устанавливается через магазин приложений на вашем устройстве, однако его также может установить ИТ-администратор.
- Перейдя на [веб-сайт корпоративного портала](http://portal.manage.microsoft.com), который настроил ИТ-администратор.

Между приложением и веб-сайтом корпоративного портала существуют небольшие различия, но большая часть задач в них выполняется одинаково. Ниже приведены некоторые доступные задачи.

- Регистрация устройств
- Просмотр состояния устройств
- Скачивание доступных корпоративных или учебных приложений
- переименовывать устройство;
- Сброс ПИН-кода или пароля
- Обращение в ИТ-отдел за поддержкой

Чтобы узнать, что можно делать с помощью веб-сайта корпоративного портала и приложения корпоративного портала на устройстве, выберите одну из следующих ссылок:

> [!div class="op_single_selector"]
- [Android](using-your-android-device-with-intune.md)
- [iOS и macOS](using-your-ios-or-mac-os-x-device-with-intune.md);
- [Windows](using-your-windows-device-with-intune.md)
- [Веб-сайт корпоративного портала](using-the-intune-company-portal-website.md)

## <a name="what-happens-when-you-add-a-computer-or-device-to-the-company-portal"></a>Что происходит при добавлении компьютера или устройства на корпоративный портал?
При добавлении компьютера или устройства на корпоративный портал могут быть установлены некоторые программы или загружено приложение (в зависимости от устройства).  Вы также предоставляете своему ИТ-администратору разрешение на управление устройством для защиты корпоративных данных на нем.

Чтобы узнать, что ИТ-администратор может и не может просмотреть на вашем устройстве, используйте ссылку, соответствующую типу устройства:

> [!div class="op_single_selector"]
- [Android](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-android.md)
- [iOS и macOS](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md);
- [Windows](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md)

## <a name="what-kind-of-computers-or-devices-can-you-add-to-the-company-portal"></a>Какие компьютеры или устройства можно добавлять на корпоративный портал?

-   Устройства iPhone, iPad и macOS

-   Мобильные устройства Android

-   Устройства Windows
    -   Windows 10 Mobile
    -   Windows 10 Desktop
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Можно ли удалить компьютер или устройство из корпоративного портала?
Можно удалить компьютер или устройство из корпоративного портала или сбросить его. Существует различие между **удалением** и **сбросом** устройства.

При *удалении* компьютера или устройства выполняется отмена регистрации устройства в Intune. После отмены регистрации вы больше не сможете обращаться к корпоративному порталу с этого устройства, и некоторые корпоративные данные могут быть удалены с вашего устройства. Чтобы узнать, как удалить устройство из корпоративного портала, выберите одну из следующих ссылок:

> [!div class="op_single_selector"]
- [Android](unenroll-your-device-from-intune-android.md)
- [iOS и macOS](unenroll-your-device-from-intune-ios.md);
- [Windows](unenroll-your-device-from-intune-windows.md)

При *сбросе* компьютера или устройства корпоративный портал пытается выполнить сброс устройства до заводских настроек по умолчанию. При сбросе устройства с него удаляются все корпоративные и персональные данные! В случае потери устройства вы сможете удаленно сбросить его с веб-сайта корпоративного портала.

Чтобы узнать, как выполнить сброс устройства, выберите одну из следующих ссылок:

> [!div class="op_single_selector"]
- [Android](reset-erase-your-lost-or-stolen-device-android.md)
- [iOS и macOS](reset-erase-your-lost-or-stolen-device-ios.md);
- [Windows](reset-erase-your-lost-or-stolen-device-windows.md)
- [Сброс устройства с веб-сайта корпоративного портала](reset-your-device-cpwebsite.md)

## <a name="you-do-not-see-all-of-your-devices-in-the-company-portal"></a>Почему не все устройства отображаются на корпоративном портале?
Устройство отображается на корпоративном портале, только если оно добавлено на него. Перейдите на корпоративный портал в соответствии с указаниями администратора и выполните действия, предусмотренные для вашего устройства. Также не будут отображаться корпоративные устройства и устройства, которыми управляет ваша компания.

## <a name="if-you-have-questions-contact-your-it-administrator"></a>Если у вас есть вопросы, обратитесь к ИТ-администратору.
Если вам нужна помощь, обратитесь к системному администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO1-->


