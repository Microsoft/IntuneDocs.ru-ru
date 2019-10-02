---
title: Настройка интеграции Sophos Mobile и Intune
titleSuffix: Intune on Azure
description: Как настроить решение Sophos Mobile в Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec60a618280caf6a5b7ef242c192cc64b5d839de
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726678"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Интеграция Sophos Mobile с Intune  

Чтобы интегрировать решение Sophos Mobile с Intune, выполните следующие действия.  

## <a name="before-you-begin"></a>Подготовка к работе  

Перед началом интеграции Sophos Mobile с Intune проверьте, что у вас есть следующее.  
- Подписка на Microsoft Intune  
- Учетные данные администратора Azure Active Directory для предоставления следующих разрешений:  
  - Вход и чтение профилей пользователей  
  - Доступ к каталогу от имени вошедшего в систему пользователя  
  - Чтение данных каталога  
  - Отправка сведений об устройстве в Intune  
- Учетные данные администратора для доступа к консоли администрирования Sophos Mobile.  


### <a name="sophos-mobile-app-authorization"></a>Авторизация приложения Sophos Mobile  
  
Авторизация приложения Sophos Mobile выполняется следующим образом:  
- Вы разрешаете службе Sophos Mobile передавать в Intune сведения о состоянии работоспособности устройства.  
- Sophos Mobile синхронизируется с членством в группе регистрации Azure AD и заполняет базу данных устройства.  
- Вы разрешаете консоли администрирования Sophos Mobile использовать единый вход Azure AD.  
- Вы разрешаете приложению Sophos Mobile использовать единый вход в Azure AD.  


## <a name="to-set-up-sophos-mobile-integration"></a>Настройка интеграции Sophos Mobile  

1. Войдите на [портал Azure]( https://portal.azure.com/), перейдите в раздел **Intune** > **Соответствие устройств** > **Mobile Threat Defense** > и выберите команду **Добавить**.  
2. На странице **Добавление соединителя** используйте раскрывающийся список и выберите **Sophos**. Затем нажмите **Создать**.  
3. Перейдите по ссылке *Открыть консоль администрирования Sophos*.  
4. Войдите в [консоль администрирования Sophos](https://central.sophos.com/) с вашими учетными данными Sophos.  
5. Перейдите в раздел **Мобильные устройства** > **Параметры** > **Настройка** > **Настройка Sophos**.  
6. На странице **Настройка Sophos** выберите вкладку **Intune MTD**.  
   ![Настройка Sophos](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Выберите команду **Привязать**, а затем выберите **Да**. Sophos подключается к Intune; вам необходимо войти в свою подписку Intune. 
8. В окне проверки подлинности Microsoft Intune введите свои учетные данные Intune и **примите** запрос разрешений для *Sophos Mobile Threat Defense*.  
   ![Проверка подлинности Intune](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. На странице **Настройка Sophos** выберите команду **Сохранить** для завершения настройки Intune:  
   ![Сохранение настройки Sophos](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. При отображении сообщения **Successful Integration** (Интеграция выполнена) интеграция завершена.  
1. В консоли Intune теперь доступна служба Sophos.  


## <a name="next-steps"></a>Дальнейшие действия  
[Настройка клиентских приложений Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
