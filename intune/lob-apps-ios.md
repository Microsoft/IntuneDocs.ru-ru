---
title: "Добавление бизнес-приложений iOS в Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте, как добавлять в Intune бизнес-приложения iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1e9dea2b44279c26de2b2ea4141fe010645ba942
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a>Как добавлять в Microsoft Intune бизнес-приложения iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Шаг 1. Выбор файла установки программного обеспечения

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Управление приложениями**.
4. В рабочей нагрузке **Мобильные приложения** выберите **Управление** > **Приложения**.
5. Щелкните **Добавить** над списком приложений.
6. В колонке **Добавить приложение** выберите **Бизнес-приложение**.

## <a name="step-2---configure-the-app-package-file"></a>Шаг 2. Настройка файла пакета приложения

1. В колонке **Добавить приложение** выберите **Пакет приложения**.
2. В колонке файла **Пакет приложения** нажмите кнопку "Обзор" и выберите файл установки iOS с расширением **.ipa**.
3. После этого нажмите кнопку **ОК**.


## <a name="step-3---configure-app-information"></a>Шаг 3. Настройка сведений о приложении

1. В колонке **Добавить приложение** выберите **Пакет приложения**.
2. В колонке **Сведения о приложении** настройте следующие сведения. В зависимости от выбранного приложения некоторые значения в этой колонке могут заполняться автоматически.
    - **Имя**: введите имя приложения так, как оно будет отображаться на корпоративном портале. Убедитесь, что все имена приложений являются уникальными. Если имя приложения существует два раза, пользователи корпоративного портала увидят только одно из приложений.
    - **Описание**: введите описание приложения. Оно будет отображаться для пользователей на корпоративном портале.
    - **Издатель**: введите имя издателя приложения.
    - **Минимальная версия операционной системы**. Выберите в списке минимальную версию операционной системы, в которой можно установить приложение. Если назначить приложение устройству с более ранней версией операционной системы, оно не установится.
    - **Категория**. Выберите одну или несколько встроенных категорий приложений или созданную категорию. Это облегчит поиск приложения при просмотре пользователями корпоративного портала.
    - **Отобразить это приложение в рекомендуемых на корпоративном портале**. Выберите этот параметр, чтобы приложение отображалось на видном месте на главной странице корпоративного портала, когда пользователи просматривают приложения.
    - **URL-адрес сведений**. Необязательный параметр. Введите URL-адрес веб-сайта со сведениями об этом приложении. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес политики конфиденциальности**. Необязательный параметр. Введите URL-адрес веб-сайта со сведениями о политике конфиденциальности для этого приложения. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **Разработчик**. Необязательный параметр. Введите имя разработчика приложения.
    - **Владелец**. Необязательный параметр. Введите имя владельца приложения, например **отдел кадров**.
    - **Заметки**. Введите заметки, которые нужно связать с этим приложением.
    - **Логотип**. Загрузите значок, который будет связан с приложением. Это значок, который будет отображаться с приложением при просмотре пользователями корпоративного портала.
3. После этого нажмите кнопку **ОК**.

## <a name="step-4---finish-up"></a>Шаг 4. Завершение

1. В колонке **Добавить приложение** проверьте правильность указанных сведений.
2. Выберите **Добавить**, чтобы отправить приложение в Intune.

Созданное приложение отобразится в списке приложений, из которого его можно назначить выбранным группам. Сведения см. в статье о [назначении приложений группам](apps-deploy.md).
