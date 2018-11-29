---
title: Настройка интеграции Symantec и Microsoft Intune
titlesuffix: ''
description: Как настроить решение Symantec Endpoint Protection Mobile в Microsoft Intune для управления доступом к корпоративным ресурсам с мобильных устройств.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: accd8dea2b997a6eb1cfec22a6e822e984ef710d
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180159"
---
# <a name="set-up-symantec-endpoint-protection-mobile-integration-with-intune"></a>Настройка интеграции Symantec Endpoint Protection Mobile с Intune

Выполните следующие действия, чтобы настроить интеграцию решения Symantec Endpoint Protection Mobile (SEP Mobile) с Intune. Приложения SEP Mobile нужно добавить в Azure AD, чтобы использовать функцию единого входа.

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="azure-ad-account-used-to-integrate-intune-and-sep-mobile"></a>Учетная запись Azure AD для интеграции Intune и SEP Mobile.

-   Перед началом базовой настройки SEP Mobile убедитесь, что у вас есть учетная запись Azure AD, правильно настроенная в [консоли управления Symantec Endpoint Protection Mobile](https://aad.skycure.com).
- Для интеграции вам потребуется учетная запись глобального администратора Azure AD.
### <a name="network-setup"></a>Настройка сети

См. дополнительные сведения о проверке [конфигурации сети для интеграции с SEP Mobile](https://portal.skycure.com/articles/Documentation/Setting-up-your-network-configuration-26-8-2016) (руководство Symantec).

### <a name="full-integration-vs-read-only"></a>Полная интеграция и интеграция Только чтение

SEP Mobile поддерживает два режима интеграции с Intune.

-   **Интеграция только для чтения (базовая настройка)**: выполняется только инвентаризация устройств из Azure Active Directory и их внесение в консоль Symantec Endpoint Protection Mobile.
<br>
    -   Если в панели управления Symantec Endpoint Protection Mobile не выбраны параметры **Сообщать о работоспособности и рисках устройств в Intune** и **Также передавать инциденты безопасности в Intune**, интеграция используется в режиме "только для чтения", не позволяя изменять состояние (соответствие) для устройств в Intune.
<br></br>
-   **Полная интеграция**: разрешает SEP Mobile сообщать в Intune об устройствах с рисками и об инцидентах безопасности, то есть создает двунаправленное взаимодействие между облачными службами.

### <a name="how-are-the-sep-mobile-apps-used-with-azure-ad-and-intune"></a>Как используются приложения SEP Mobile совместно с Azure AD и Intune?

-   **Приложение для iOS**: позволяет конечным пользователям входить в Azure AD с помощью приложения для iOS.

-   **Приложение для Android**: позволяет конечным пользователям входить в Azure AD с помощью приложения Android.

-   **Приложение управления**: это мультитенантное приложение SEP Mobile для Azure AD, которое обеспечивает для Intune обмен данными типа "служба — служба".

## <a name="to-set-up-the-read-only-integration-between-intune-and-sep-mobile"></a>Настройка интеграции только для чтения между Intune и SEP Mobile

> [!IMPORTANT]
> Учетные данные администратора SEP Mobile должны содержать адрес электронной почты действительного пользователя Azure Active Directory. В противном случае вход завершится сбоем. SEP Mobile использует Azure Active Directory для аутентификации администратора с помощью единого входа (SSO).

1.  Откройте [консоль управления Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2.  Введите **учетные данные администратора SEP Mobile** и выберите действие **Продолжить**.

3.  Перейдите в **Параметры** и в разделе **Интеграция Intune** выберите пункт **Базовая настройка**.

4.  Рядом с элементом **Приложение iOS** выберите действие **Добавить в Active Directory**.

    ![Изображение приложения iOS в консоли управления Symantec Endpoint Protection Mobile](./media/symantec-portal-basic-add.png)

5.  На открывшейся странице входа введите учетные данные Intune и щелкните **Принять**.

    ![Изображение окна входа приложений для iOS в Intune](./media/symantec-portal-basic-accept.png)

6.  Когда приложение будет добавлено в Azure AD, вы увидите сообщение об этом.

    ![Изображение экрана с информацией о завершении для приложения для iOS](./media/symantec-portal-basic-added.png)

7. Повторите эти шаги для приложений **SEP Mobile Android** и **Управление**.

### <a name="add-an-azure-ad-security-group-into-sep-mobile"></a>Добавление группы безопасности Azure AD в SEP Mobile

Необходимо добавить группу безопасности Azure AD со всеми устройствами, на которых работает SEP Mobile.

-  Введите и выберите все группы безопасности, в которые входят устройства под управлением SEP Mobile, а затем сохраните изменения.

    ![Изображение с группами пользователей для приложений SEP Mobile](./media/symantec-portal-basic-groups.png)   

SEP Mobile синхронизирует устройства, на которых работает служба Mobile Threat Defense в пределах групп безопасности Azure AD.

![Изображение с подтверждением завершения настройки групп безопасности в консоли управления SEP Mobile](./media/symantec-portal-basic-status.png)

## <a name="to-set-up-the-full-integration-between-intune-and-sep-mobile"></a>Настройка полной интеграции между Intune и SEP Mobile

### <a name="retrieve-the-directory-id-in-azure-ad"></a>Получение идентификатора каталога в Azure AD

1. Войдите на [портал Azure](https://portal.azure.com).

2. В поле поиска введите Active Directory и выберите элемент **Azure Active Directory**.

3. Выберите пункт **Свойства**.

4. Рядом с **идентификатором каталога** щелкните значок копирования и вставьте идентификатор в безопасное расположение. Этот идентификатор потребуется вам на следующих шагах.

    ![Изображение с идентификатором каталога на портале Azure](./media/symantec-azure-portal-directory-ID.png)

### <a name="optional-create-a-dedicated-security-group-for-devices-that-need-to-run-the-sep-mobile-apps"></a>(Необязательно.) Создайте отдельную группу безопасности для устройств, на которых будут выполняться приложения SEP Mobile
1. На [портале Azure](https://portal.azure.com) в разделе **Управление** выберите **Пользователи и группы** и **Все группы**.

2. Выберите кнопку **Добавить**. Введите **Имя** для группы. Для параметра **Тип членства** выберите значение **Назначено**.

3. В колонке **Члены** выберите все элементы группы, а затем нажмите кнопку **Выбрать**.

4. В колонке **Группа** выберите действие **Создать**.

### <a name="set-up-the-integration-between-symantec-endpoint-protection-mobile-and-intune"></a>Настройка интеграции между Symantec Endpoint Protection Mobile и Intune

1.  Откройте [консоль управления Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2.  Введите **учетные данные администратора SEP Mobile** и выберите **Продолжить**.

3.  Последовательно выберите элементы **Параметры** > **Интеграции** > **Intune** > **Выбор интеграции EMM**.

4. В поле **идентификатор каталога** вставьте идентификатор каталога, который вы скопировали в предыдущем разделе из Azure Active Directory, и сохраните параметры.

    ![Изображение с идентификатором каталога на портале SEP Mobile](./media/symantec-portal-directory-ID.png)     

5. Последовательно выберите **Параметры** > **Интеграции** > **Intune** > **Базовая настройка**.

6. Рядом с элементом **Приложение iOS** нажмите кнопку **Добавить в Active Directory**.

    ![Изображение процесса добавления приложения iOS в Active Directory](./media/symantec-portal-basic-add.png)   

7.  Выполните вход с учетными данными Azure Active Directory для учетной записи Office 365, которая управляет этим каталогом.

8.  Выберите кнопку **Принять**, чтобы добавить приложение SEP Mobile для iOS в Azure Active Directory.

    ![Изображение с кнопкой "Принять"](./media/symantec-portal-basic-accept.png)     

9.  Повторите все эти действия для **приложения для Android** и **приложения управления**.

10. Выберите все группы с пользователями, которые будут выполнять приложения SEP Mobile, например созданную ранее группу безопасности.

    ![Изображение с группами пользователей для приложений SEP Mobile](./media/symantec-portal-basic-groups.png)   

11.  СЕН Mobile синхронизирует устройства из выбранных групп и начнет передавать данные в Intune. Эти данные можно просмотреть в разделе полной интеграции. Последовательно выберите элементы **Параметры** > **Интеграции** > **Intune** > **Полная интеграция**.

     ![Изображение с сообщением о завершении полной интеграции SEP Mobile](media/symantec-portal-basic-status.PNG)
## <a name="next-steps"></a>Дальнейшие шаги

[Настройка приложений SEP Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)
