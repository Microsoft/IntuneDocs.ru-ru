---
title: Добавление в Microsoft Intune приложений из магазина iOS
titleSuffix: ''
description: Узнайте, как добавлять приложения из магазина iOS в Microsoft Intune. Можно назначить приложения, используя этот метод, если приложения предоставляются бесплатно в магазине приложений.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68976c9a71ab1c1886fd5f975df563acb44dc731
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724494"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Добавление в Microsoft Intune приложений из магазина iOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

В этой статье рассказывается, как добавлять в Microsoft Intune приложения из магазина iOS. Приложения из магазина iOS — это приложения, которые Intune устанавливает на устройствах пользователей. Пользователь является сотрудником вашей компании. Приложения из магазина iOS обновляются автоматически.

>[!NOTE]
>Пользователи устройств iOS могут удалять некоторые встроенные приложения iOS, такие как Акции или Карты, и с помощью Intune восстановить их на устройствах невозможно. Чтобы восстановить эти приложения, пользователи должны зайти в App Store и установить их вручную.

## <a name="before-you-start"></a>Перед началом работы

В Intune можно назначить только приложения, которые предоставляются бесплатно в App Store. Если вы хотите назначить платные приложения, мы советуем использовать [программу iOS Volume Purchase Program](vpp-apps-ios.md).

>[!NOTE]
>Рекомендуемые при работе с Microsoft Intune браузеры — Chrome и Microsoft Edge.

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. На панели **Intune** выберите **Клиентские приложения**.
4. В области рабочей нагрузки **Клиентские приложения** перейдите к разделу **Управление** и выберите **Приложения**.
5. В области **Приложения** нажмите кнопку **Добавить**.
6. В разделе **Приложение магазина** выберите в списке **Тип приложения** тип **iOS**.
7. Щелкните **Поиск в App Store**.
8. В области **Поиск в App Store** выберите языковой стандарт App Store для страны или региона.
9. В поле **поиска** введите имя (или часть имени) приложения.  
    Intune выполнит поиск в магазине и отобразит соответствующие результаты.
10. В списке результатов выберите нужное приложение и щелкните **Выбрать**.
11. В области **Добавить приложение** выберите **Сведения о приложении** для настройки приложения.
12. В области **Сведения о приложении** добавьте сведения о приложении. В зависимости от выбранного приложения некоторые значения в этой области могут заполняться автоматически:
    - **Имя**. Введите имя приложения, которое будет отображаться на корпоративном портале. Убедитесь, что используемое имя приложения уникально. При дублировании имени приложения пользователи корпоративного портала увидят только одно из них.
    - **Описание** Введите описание приложения. Оно отображается на корпоративном портале.
    - **Издатель**. Введите имя издателя приложения.
    - **URL-адрес Appstore**. Введите URL-адрес приложения в магазине, которое вы хотите создать.
    - **Минимальная версия операционной системы**. Выберите в списке минимальную версию операционной системы, в которой можно установить приложение. Если назначить приложение устройству с более ранней версией операционной системы, оно не установится.
    - **Применимый тип устройств**. Выберите в списке устройства, используемые приложением.
    - **Категория**. При необходимости выберите для приложения одну или несколько встроенных или созданных вами категорий. Это поможет пользователям найти приложение на корпоративном портале.
    - **Отобразить это приложение в рекомендуемых на Корпоративном портале**. Выберите этот параметр, чтобы набор приложений отображался на видном месте на главной странице Корпоративного портала, когда пользователи просматривают приложения.
    - **URL-адрес сведений**. Дополнительно можно ввести URL-адрес веб-сайта со сведениями об этом приложении. Он будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес политики конфиденциальности**. Дополнительно можно ввести URL-адрес веб-сайта со сведениями о политике конфиденциальности для этого приложения. Он будет отображаться для пользователей на корпоративном портале.
    - **Разработчик**. При необходимости введите имя разработчика приложения. Это поле отображается только для администраторов. Пользователи не видят его.
    - **Имя владельца**. При необходимости введите имя владельца приложения, например, *отдел кадров*. Это поле отображается только для администраторов. Пользователи не видят его.
    - **Заметки**. При необходимости введите любые заметки, которые нужно связать с этим приложением. Это поле видит только администратор, но не пользователи.
    - **Логотип**. При необходимости загрузите значок, который будет связан с приложением. Этот значок будет отображаться с приложением при просмотре пользователями корпоративного портала.
13. Нажмите кнопку **ОК**.
14. Нажмите кнопку **Добавить**.

Созданное приложение отображается в списке приложений, из которого его можно назначить выбранным группам.

## <a name="next-steps"></a>Дальнейшие шаги

- [назначение приложений группам](apps-deploy.md).