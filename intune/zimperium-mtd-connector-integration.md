---
title: Интеграция Zimperium MTD с Microsoft Intune
titleSuffix: ''
description: Как настроить решение Zimperium Mobile Threat Defense (MTD) в Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fada315aad9bce47a3a04286d84e1c7dbdd2ce61
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
ms.locfileid: "29777625"
---
# <a name="integrate-zimperium-with-intune"></a>Интеграция Zimperium с Intune

Чтобы интегрировать решение Mobile Threat Defense Zimperium с Intune, следуйте инструкциям ниже.

## <a name="before-you-begin"></a>Подготовка к работе

> [!NOTE]
> Следующие шаги выполняются в [консоли Zimperium MTD](https://staging2-console.zimperium.com).

Перед началом интеграции Zimperium с Intune убедитесь в наличии следующей подписки и учетных данных:

-   Подписка на Microsoft Intune

-   Учетные данные администратора Azure Active Directory для предоставления следующих разрешений:

    -   Вход и чтение профилей пользователей

    -   Доступ к каталогу от имени вошедшего в систему пользователя

    -   Чтение данных каталога

    -   Отправка сведений об устройстве в Intune

-   Учетные данные администратора для доступа к консоли MTD Zimperium.

### <a name="zimperium-app-authorization"></a>Авторизация приложения Zimperium

Авторизация приложения Zimperium выполняется так:

-   Вы разрешаете службе Zimperium передавать в Intune сведения о состоянии работоспособности устройства.

-   Zimperium синхронизируется с членством в группе регистрации Azure Active Directory (AD) и заполняет базу данных устройства.

-   Вы разрешаете консоли администрирования Zimperium использовать единый вход (SSO) Azure AD.

-   Вы разрешаете приложению Zimperium выполнять вход в режиме единого входа Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Настройка интеграции Zimperium

1.  Перейдите в [консоль MTD Zimperium](https://staging2-console.zimperium.com) и выполните вход, используя свои учетные данные.

2.  Выберите в левом меню пункт **Управление**.

3.  Перейдите на вкладку **Параметры MDM**.

4.  Выберите **Добавить MDM,** а затем **Microsoft Intune** в списке **поставщиков MDM**.

5.  Когда вы настроите Microsoft Intune как службу управления мобильными устройствами, откроется окно **Настройка Microsoft Intune**. Выберите вариант **Добавить Azure Active Directory** для каждого параметра: **Zimperium zConsole**, **Приложения iOS и Android zIPS**, чтобы разрешить Zimperium взаимодействовать с Intune и Azure AD в режиме единого входа Azure AD.

    > [!IMPORTANT]
    > Чтобы завершить процесс интеграции с Intune, вам потребуется добавить приложения zConsole Zimperium, zIPS iOS и Android.

6.  Нажмите кнопку **Принять**, чтобы разрешить приложению Zimperium взаимодействовать с Intune и Azure Active Directory.

7.  После добавления приложений **Zimperium zConsole** и **iOS и Android zIPS** в Azure AD добавьте группы безопасности Azure AD. Это позволит Zimperium синхронизировать группу безопасности Azure AD со своей службой.

8.  Нажмите кнопку **Готово**, чтобы сохранить конфигурацию и запустить первую синхронизацию групп безопасности Azure AD.

## <a name="next-steps"></a>Дальнейшие шаги

-   [Настройка приложений Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
