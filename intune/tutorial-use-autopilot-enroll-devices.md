---
title: Руководство по использованию Autopilot для регистрации устройств в Intune
titleSuffix: Microsoft Intune
description: В этом руководстве вы настроите Windows Autopilot для регистрации устройств в Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 087f890f84c9bc0ff0c46f129ef84b8a268c738e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187741"
---
# <a name="tutorial-use-autopilot-to-enroll-windows-devices-in-intune"></a>Руководство по использованию Autopilot для регистрации устройств Windows в Intune
Windows Autopilot упрощает регистрацию устройств. Благодаря Microsoft Intune и программе Autopilot вы можете предоставлять пользователям новые устройства без необходимости создавать, обслуживать и распространять образы операционной системы. 

Из этого руководства вы узнаете, как выполнять следующие задачи:
> [!div class="checklist"]
> * Добавление устройств в Intune.
> * Создание группы устройств Autopilot.
> * Создание профиля развертывания Autopilot.
> * Назначение профиля развертывания Autopilot группе устройств.
> * Распределение устройств между пользователями.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](free-trial-sign-up.md).

Общие сведения о преимуществах, сценариях и предварительных требованиях Autopilot см. в документации по [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Предварительные условия
- [Настроенная автоматическая регистрация Windows](quickstart-setup-auto-enrollment.md).
- [Требуется подписка Azure Active Directory Premium.](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## <a name="add-devices"></a>Добавление устройств

Первым шагом при настройке Windows Autopilot является добавление устройств Windows в Intune. Для этого достаточно создать CSV-файл и импортировать его в Intune.

1. В любом текстовом редакторе создайте список значений с разделителями-запятыми (CSV-файл), которые идентифицируют устройств Windows. Используйте следующий формат:
    
    *серийный номер*, *идентификатор продукта windows*, *хэш-код оборудования*, *необязательный идентификатор заказа*
    
    Первые три элемента являются обязательными, а идентификатор заказа можно не указывать.

2. Сохраните CSV-файл.

3. В [Intune на портале Azure](https://aka.ms/intuneportal) последовательно выберите **Регистрация устройства** > **Регистрация Windows** > **Устройства** > **Импорт**.

    ![Снимок экрана: устройства Windows Autopilot](media/enrollment-autopilot/autopilot-import-device.png)

4. В разделе **Добавить устройства Windows Autopilot** найдите сохраненный CSV-файл был сохранен.

    ![Снимок экрана: добавление устройств Windows Autopilot](media/enrollment-autopilot/autopilot-import-device2.png)

5. Выберите **Импорт**, чтобы начать импорт сведений об устройстве. Импорт может занять несколько минут.

4. После завершения импорта выберите **Регистрация устройства** > **Регистрация Windows** > **Windows Autopilot** > **Устройства** > **Синхронизировать**. Появится сообщение о том, что выполняется синхронизация. На завершение процесса может потребоваться несколько минут в зависимости от количества синхронизируемых устройств.

5. Чтобы увидеть новые устройства, обновите представление.

## <a name="create-an-autopilot-device-group"></a>Создание группы устройств Autopilot.

Теперь вы создадите группу устройств и разместите в ней только что загруженные устройства Autopilot.

1. В разделе [Intune на портале Azure](https://aka.ms/intuneportal) выберите **Группы** > **Создать группу**.
2. В колонке **Группа**
    1. В качестве **Типа группы** выберите **Безопасность**.
    2. В поле **Имя группы** введите *Группа Autopilot*. В поле **Описание группы** введите текст *Тестовая группа для устройств Autopilot*.
    3. В поле **Тип членства** выберите **Назначено**.
3. В колонке **Группа** выберите **Члены** и добавьте в группу устройства Autopilot. Для еще не зарегистрированных устройств Autopilot в качестве имени используется серийный номер устройства.
4. Выберите команду **Создать**.  

## <a name="create-an-autopilot-deployment-profile"></a>Создание профиля развертывания Autopilot.

Создав группу устройств, необходимо создать профиль развертывания, который позволяет настроить устройства Autopilot.

1. В [Intune на портале Azure](https://aka.ms/intuneportal) последовательно выберите **Регистрация устройства** > **Регистрация Windows** > **Профили развертывания** > **Создать профиль**.
2. В поле **Имя** введите *Профиль Autopilot*. В поле **Описание** введите текст *Тестовый профиль для устройств Autopilot*.
3. Для параметра **Convert all targeted devices to Autopilot** (Преобразовать все целевые устройства в Autopilot) выберите вариант **Да**. Этот параметр гарантирует, что все устройства из списка будут зарегистрированы в службе развертывания Autopilot. Регистрация завершится в течение 48 часов.
4. Для параметра **Режим развертывания** выберите **Под управлением пользователя**. Устройства с таким профилем связываются с пользователем, регистрирующим устройство. Для регистрации устройства нужны учетные данные пользователя.
5. В поле **Тип присоединения к Azure AD** выберите **Присоединено к Azure AD**.
6. Выберите **Готовый интерфейс (OOBE)**, настройте перечисленные ниже параметры и сохраните настройки по умолчанию для всех остальных, после чего нажмите **Сохранить**.
    - **Лицензионное соглашение (EULA)**: **Скрыть**.
    - **Параметры конфиденциальности**: **Отобразить**.
    - **Тип учетной записи пользователя**: **Стандартный**.

6. Нажмите **Создать** для создания профиля. Теперь профиль развертывания Autopilot можно назначать устройствам.

## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Назначение профиля развертывания Autopilot группе устройств

Созданный профиль развертывания можно присвоить группе устройств.
1. В [Intune на портале Azure](https://aka.ms/intuneportal) последовательно выберите **Регистрация устройства** > **Регистрация Windows** > **Профили развертывания**, а затем укажите нужный профиль.
2. В колонке этого профиля выберите **Назначения**. 
3. Щелкните **Выбрать группы**, затем в колонке **Выбор групп** щелкните **Группа Autopilot** и **Выбрать**.

## <a name="distribute-devices-to-users"></a>Распределение устройств между пользователями

Теперь можно распределить устройства Windows между пользователями. При первом входе пользователей система Autopilot автоматически выполнит регистрацию и настройку устройств. 

## <a name="clean-up-resources"></a>Очистка ресурсов

Если вы не планируете далее использовать устройства Autopilot, их можно удалить.

1. Если устройства зарегистрированы в Intune, сначала [удалите их на портале Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. В [Intune на портале Azure](https://aka.ms/intuneportal) последовательно выберите **Регистрация устройства** > **Регистрация Windows** > **Устройства**.

3. В разделе **Устройства Windows Autopilot** выберите удаляемые устройства и щелкните **Удалить**.

4. Подтвердите удаление, щелкнув **Да**. Этот процесс может занять несколько минут.

## <a name="next-steps"></a>Дальнейшие шаги

См. дополнительные сведения о других параметрах, доступных для Windows Autopilot.

> [!div class="nextstepaction"]
> [Подробная статья о регистрации Autopilot](enrollment-autopilot.md)

