---
title: Политики конфигурации для управляемых приложений без регистрации устройств
titleSuffix: Microsoft Intune
description: Узнайте, как настроить политики конфигурации для управляемых приложений без регистрации устройств.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7716eeb496567eb4e4a35a703b66597ed47e87a6
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725846"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Добавление политик конфигурации приложений для управляемых приложений без регистрации устройств

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Политики конфигурации приложений можно использовать с управляемыми приложениями, поддерживающими пакет SDK для приложений Intune даже на незарегистрированных устройствах. 

> [!NOTE]
> Чтобы получить политики App Configuration, к приложениям также должна применяться политика Защиты приложений Intune. Дополнительные сведения о создании политик Защиты приложений Intune см. в статье [Что такое политики защиты приложений?](app-protection-policy.md)

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Выберите рабочую нагрузку **Клиентские приложения**.
4. В группе **Управление** выберите **Политики конфигурации приложений**, а затем нажмите кнопку **Добавить**.
5. Задайте следующие значения:
    - **Имя**  
      Имя профиля, которое будет отображаться на портале Azure.
    - **Описание**  
      Описание профиля, которое будет отображаться на портале Azure.
    - **Тип регистрации устройства**  
      Выберите **Управление приложениями**.
6. Щелкните **Связанные приложения**, чтобы выбрать приложение, которое нужно настроить. Для выбора используйте список приложений, которые были утверждены и синхронизированы в Intune.
7. Для каждого параметра конфигурации, поддерживаемого приложением, укажите **Имя** и **Значение** и нажмите кнопку с многоточием ( **...** ).  
    Чтобы удалить конфигурацию, нажмите кнопку с многоточием ( **...** ) и выберите **Удалить**.  
    
Приложения на основе пакета SDK для приложений Intune поддерживают конфигурации в виде пар "ключ-значение". Дополнительные сведения о поддерживаемых конфигурациях "ключ-значение" см. в документации по конкретному приложению. Обратите внимание, что можно применять маркеры, которые будут динамически заполняться данными, создаваемыми приложением. Сведения о параметрах политики конфигурации Outlook для iOS см. в статье [Управление конфигурацией приложения Outlook для iOS с помощью Microsoft Intune](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Значения конфигурации для использования токенов

Intune может создавать определенные токены и отправлять их в управляемое приложение. Например, если конфигурация приложения использует параметр электронной почты, с помощью токена можно добавить динамическую электронную почту. Введите ожидаемое приложением имя в поле **Имя**, а затем введите `\{\{mail\}\}` в поле **Значение**.

Intune поддерживает следующие типы токенов в параметрах конфигурации. Другие пользовательские пары ключ-значение не поддерживаются.

- \{\{userprincipalname\}\}, например John@contoso.com
- \{\{mail\}\}, например John@contoso.com
- \{\{partialupn\}\}, например Илья
- \{\{accountid\}\}, например fc0dc142-71d8-4b12-bbea-bae2a8514c81
- \{\{userid\}\}, например 3ec2c00f-b125-4519-acf0-302ac3761822
- \{\{username\}\}, например Илья Глазков
- \{\{PrimarySMTPAddress\}\}, например testuser@ad.domain.com


> [!Note]  
> Символы \{\{ и \}\} используются только для типов токенов и не должны применяться в других целях.

## <a name="next-steps"></a>Дальнейшие шаги

Продолжайте [назначать](apps-deploy.md) и [отслеживать](apps-monitor.md) приложение как обычно.