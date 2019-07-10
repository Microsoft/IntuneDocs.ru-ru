---
title: Интеграция Zimperium MTD с Microsoft Intune
titleSuffix: Microsoft Intune
description: Как настроить решение Zimperium Mobile Threat Defense (MTD) в Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e78c9034058a5f60f01056711465b28deca77d83
ms.sourcegitcommit: ede86a3cb094c12e3e218b956abb9935bec76902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2019
ms.locfileid: "67572163"
---
# <a name="integrate-zimperium-with-intune"></a>Интеграция Zimperium с Intune

Чтобы интегрировать решение Mobile Threat Defense Zimperium с Intune, следуйте инструкциям ниже.

## <a name="before-you-begin"></a>Подготовка к работе

> [!NOTE]
> Следующие шаги выполняются в [консоли Zimperium MTD](https://www.zimperium.com/platform).

Перед началом интеграции Zimperium с Intune убедитесь в наличии следующей подписки и учетных данных:

- Подписка на Microsoft Intune

- Учетные данные глобального администратора Azure Active Directory для предоставления следующих разрешений:

    - Вход и чтение профилей пользователей

    - Доступ к каталогу от имени вошедшего в систему пользователя

    - Чтение данных каталога

    - Отправка сведений об устройстве в Intune

- Учетные данные администратора для доступа к консоли MTD Zimperium.

### <a name="zimperium-app-authorization"></a>Авторизация приложения Zimperium

Авторизация приложения Zimperium выполняется так:

- Вы предоставляете разрешение службе Zimperium на передачу в Intune сведений о состоянии работоспособности устройства. Для этого необходимо использовать учетные данные глобального администратора. Предоставление разрешений — это разовая операция. После предоставления разрешений учетные данные глобального администратора больше не понадобятся.

- Zimperium синхронизируется с членством в группе регистрации Azure Active Directory (AD) и заполняет базу данных устройства.

- Вы разрешаете консоли администрирования Zimperium использовать единый вход (SSO) Azure AD.

- Вы разрешаете приложению Zimperium выполнять вход в режиме единого входа Azure AD.

Дополнительные сведения о предоставлении согласия и приложениях Azure Active Directory см. в разделе [Запрос разрешений у администратора каталога](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) в статье *Разрешения и предоставление согласия в конечной точке Azure Active Directory версии 2.0*.


## <a name="to-set-up-zimperium-integration"></a>Настройка интеграции Zimperium

1. Перейдите в [консоль MTD Zimperium](https://www.zimperium.com/platform) и выполните вход, используя свои учетные данные. Чтобы выполнить процесс настройки интеграции Zimperium, необходимо войти в систему с помощью учетных данных пользователя Azure Active Directory, имеющего роль глобального администратора. Эта одноразовая операция настройки использует права глобального администратора для предоставления разрешения в вашей организации на взаимодействие приложений Zimperium с Intune. 

2. Выберите в левом меню пункт **Управление**.

3. Перейдите на вкладку **Параметры MDM**.

4. Выберите **Добавить MDM,** а затем **Microsoft Intune** в списке **поставщиков MDM**.

5. Когда вы настроите Microsoft Intune как службу управления мобильными устройствами, откроется окно **Настройка Microsoft Intune**. Выберите вариант **Добавить Azure Active Directory** для каждого параметра: **Zimperium zConsole**, **zIPS iOS and Android apps** (Приложения zIPS iOS и Android), чтобы разрешить Zimperium взаимодействовать с Intune и Azure AD в режиме единого входа Azure AD.

    > [!IMPORTANT]  
    > Чтобы завершить процесс интеграции с Intune, вам потребуется добавить приложения zConsole Zimperium, zIPS iOS и Android.

6. Нажмите кнопку **Принять**, чтобы разрешить приложению Zimperium взаимодействовать с Intune и Azure Active Directory.

7. После добавления приложений **Zimperium zConsole** и **zIPS iOS и Android** в Azure AD добавьте группы безопасности Azure AD. Это позволит Zimperium синхронизировать группу безопасности Azure AD со своей службой.

8. Нажмите кнопку **Готово**, чтобы сохранить конфигурацию и запустить первую синхронизацию групп безопасности Azure AD.

9. Выйдите из консоли Zimperium MTD.

## <a name="next-steps"></a>Дальнейшие шаги

- [Настройка приложений Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
