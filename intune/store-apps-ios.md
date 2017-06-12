---
title: "Как добавить приложения из Магазина iOS в Intune | Документация Майкрософт"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, как добавить приложения из магазина iOS в Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d6da2bf1ebab609b8e9be4bec998d2f081600b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Добавление в Microsoft Intune приложений из магазина iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="before-you-start"></a>Перед началом работы

В Intune можно назначить только приложения, которые предоставляются бесплатно в магазине приложений. Если вы хотите назначить платные приложения, мы советуем использовать [программу iOS Volume Purchase Program](vpp-apps-ios.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Шаг 1. Найдите приложение в магазине

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Управление приложениями**.
4. В рабочей нагрузке **Мобильные приложения** выберите **Управление** > Приложения.
5. Щелкните **Добавить** над списком приложений.
6. В колонке **Добавить приложение** выберите **Поиск в App Store**.
7. В колонке **Apple App Store** в поле поиска введите имя приложения (или часть имени). Intune выполнит поиск в магазине и вернет соответствующие результаты.
8. Выберите в списке нужное приложение, затем нажмите кнопку **ОК**.

## <a name="step-2---configure-app-information"></a>Шаг 2. Настройка сведений о приложении

1. В колонке **Добавить приложение** выберите **Сведения о приложении**.
2. В колонке **Изменить приложение** настройте следующие сведения. Когда закончите, щелкните **Добавить**. В зависимости от выбранного приложения некоторые значения в этой колонке могут заполняться автоматически.
- **Имя приложения**. Введите имя приложения, которое будет отображаться на корпоративном портале. Убедитесь, что все имена приложений являются уникальными. Если имя приложения существует два раза, пользователи корпоративного портала увидят только одно из приложений.
    - **Описание приложения**. Введите описание приложения. Оно будет отображаться для пользователей на корпоративном портале.
- **Издатель**: введите имя издателя приложения.
- **App store URL** (URL-адрес приложения в магазине). Введите URL-адрес приложения в магазине, которое вы хотите создать.
- **Минимальная версия операционной системы**. Выберите в списке минимальную версию операционной системы, в которой можно установить приложение. Если назначить приложение устройству с более ранней версией операционной системы, оно не установится.
- **Категория** (необязательно). Выберите одну или несколько встроенных категорий приложений или созданную категорию. Это облегчит поиск приложения при просмотре пользователями корпоративного портала.
- **Отобразить это приложение в рекомендуемых на корпоративном портале**. Выберите этот параметр, чтобы приложение отображалось на видном месте на главной странице корпоративного портала, когда пользователи просматривают приложения.
- **URL-адрес сведений**. Необязательный параметр. Введите URL-адрес веб-сайта со сведениями об этом приложении. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
- **URL-адрес политики конфиденциальности**. Необязательный параметр. Введите URL-адрес веб-сайта со сведениями о политике конфиденциальности для этого приложения. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
- **Разработчик**. Необязательный параметр. Введите имя разработчика приложения.
- **Владелец**. Необязательный параметр. Введите имя владельца приложения, например **отдел кадров**.
- **Заметки**. Введите заметки, которые нужно связать с этим приложением.
- **Отправить значок**. Отправьте значок, который будет связан с приложением. Это значок, который будет отображаться с приложением при просмотре пользователями корпоративного портала.
3. По завершении в колонке **Добавить приложение** нажмите кнопку **Сохранить**.

Созданное приложение отобразится в списке приложений, из которого его можно назначить выбранным группам. Сведения см. в статье о [назначении приложений группам](apps-deploy.md).
