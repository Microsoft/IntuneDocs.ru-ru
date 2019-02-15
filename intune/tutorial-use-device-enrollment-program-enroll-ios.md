---
title: Учебник. Регистрация устройств iOS в Intune с помощью Программы регистрации устройств
titleSuffix: Microsoft Intune
description: В этом руководстве вы настроите программу регистрации устройств Apple (DEP) для регистрации устройств iOS в Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17258ce2bd671dba091fa7206e599858e5ec7a93
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841544"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Руководство. Регистрация устройств iOS в Intune с помощью программы регистрации устройств
Программа регистрации устройств Apple (DEP) упрощает регистрацию устройств. При использовании Microsoft Intune и DEP устройства регистрируются автоматически при первом их включении. Это позволяет сразу предоставлять устройства группам пользователей вместо того, чтобы настраивать их по отдельности. 

Из этого руководства вы узнаете, как выполнять следующие задачи:
> [!div class="checklist"]
> * Получение токена Apple DEP
> * Создание группы устройств Autopilot.
> * Создание профиля развертывания Autopilot.
> * Назначение профиля развертывания Autopilot группе устройств.
> * Распределение устройств между пользователями.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](free-trial-sign-up.md).

## <a name="prerequisites"></a>Предварительные условия
- Устройства, приобретенные по [программе регистрации устройств Apple](http://deploy.apple.com)
- Установка [центра управления мобильными устройствами](mdm-authority-set.md)
- Получение [сертификата MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Получение токена Apple DEP
Перед регистрацией устройств iOS с помощью программы DEP необходимо получить файл токена DEP (.pem) от Apple. Этот токен позволяет службе Intune синхронизировать сведения о корпоративных устройствах, зарегистрированных по программе DEP. Он также позволяет службе Intune выполнять отправку данных профилей регистрации в Apple и назначать устройства этим профилям.

Токен DEP создается на портале Apple DEP. Кроме того, на портале DEP можно назначать устройства для управления службой Intune.

1. В [Intune на портале Azure](https://aka.ms/intuneportal) выберите **Регистрация устройства**  >  **Регистрация Apple**  >  **Токены программы регистрации**  >  **Добавить**.

2. Выберите **I agree** (Даю согласие), чтобы предоставить корпорации Майкрософт разрешение на отправку сведений о пользователях и устройствах в Apple.

   ![Снимок экрана с областью "Токен программы регистрации" в рабочей области сертификатов Apple для скачивания открытого ключа](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Выберите **Скачать сертификат открытого ключа**, чтобы скачать и сохранить файл ключа шифрования (PEM) локально. PEM-файл используется для запроса сертификата отношений доверия с портала программы регистрации устройств Apple.

4. Выберите **Create a token for Apple's Device Enrollment Program** (Создать токен с помощью программы регистрации устройств Apple), чтобы открыть портал программ развертывания Apple, и войдите с использованием корпоративного идентификатора Apple ID. Этот идентификатор Apple ID можно использовать для обновления токена DEP.

5.  На [портале программ развертывания](https://deploy.apple.com) Apple выберите значение **Начало работы** в поле **Программа регистрации устройств**.

4. На странице **Управление серверами** выберите **Add MDM Server** (Добавить сервер MDM).

5. В поле **MDM Server Name** (Имя сервера MDM) введите *TestMDMServer* и нажмите кнопку **Далее**. Имя сервера используется в качестве справочной информации для идентификации сервера управления мобильными устройствами (MDM). Это не имя или URL-адрес сервера Microsoft Intune.

6. Открывается диалоговое окно **Добавить &lt;имя_сервера&gt;** с сообщением **Upload Your Public Key** (Отправьте свой открытый ключ). Щелкните **Выбрать файл...** для отправки PEM-файла. Затем нажмите кнопку **Далее**.

6. Перейдите в раздел **Deployment Programs** > **Device Enrollment Program** > **Manage Devices** (Программы развертывания > Программа регистрации устройств > Управление устройствами).
7. В разделе **Choose Devices By** (Выбор устройств) выберите **Serial Number** (Серийный номер). <!--ask Tiffany about this-->

8. Для параметра **Выбрать действие** выберите значение **Назначить серверу**, укажите &lt;имя_сервера&gt;, заданное для Microsoft Intune, и нажмите кнопку **ОК**. Портал Apple назначает указанные устройства серверу Intune для управления, а затем отображает сообщение **Assignment Complete** (Назначено).

   На портале Apple перейдите в раздел **Deployment Programs** (Программы развертывания) &gt; **Device Enrollment Program** (Программы регистрации устройств) &gt; **View Assignment History** (Просмотреть журнал назначений), чтобы просмотреть список устройств и их назначение серверу MDM.

9. В Intune на портале Azure укажите идентификатор Apple ID, использовавшийся для создания этого токена, для дальнейшего применения.

    ![Снимок экрана, где указывается идентификатор Apple ID для создания токена программы регистрации и выполняется переход к токену.](./media/device-enrollment-program-enroll-ios/image03.png)

10. В поле **Токен Apple** перейдите к файлу сертификата (PEM) и щелкните **Открыть**, а затем выберите **Создать**. 

## <a name="create-an-apple-enrollment-profile"></a>Создание профиля регистрации Apple
Теперь, когда вы установили токен, можно создать профиль регистрации для устройств DEP. Профиль регистрации устройства определяет параметры, применяемые к группе устройств в процессе регистрации.

1. В Intune на портале Azure выберите **Регистрация устройства** > **Регистрация Apple** > **Токены программы регистрации**.

2. Выберите только что установленный токен и щелкните **Профили** > **Создать профиль**.

3. В разделе **Создание профиля** в поле **Имя** введите *TestDEPProfile*, а в поле **Описание** — *Тестирование DEP для устройств iOS*. Пользователям эти сведения не отображаются.

4. Для параметра **Сходство пользователей** выберите значение **Зарегистрировать с сопоставлением пользователей**. Этот вариант предназначен для устройств, которые принадлежат пользователям и должны использовать корпоративный портал для выполнения таких действий, как установка приложений.

5. Для параметра **Проверять подлинность с помощью корпоративного портала, а не помощника по настройке Apple** выберите значение **Нет**.

6. Выберите пункт **Параметры управления устройствами** и для параметра **Защищено** выберите значение **Нет**. Для защищенных устройств доступны дополнительные возможности управления, но в этом учебнике они использоваться не будут.

7. Нажмите кнопку **ОК**.

8. Выберите **Конфигурация помощника по настройке** и введите в поле **Название отдела** значение *Пример отдела*. Эта строка отображается, когда пользователь выбирает пункт **О конфигурации** во время активации устройства.

9. В поле **Номер телефона отдела** введите номер телефона. Этот номер отображается, когда пользователь нажимает кнопку **Нужна помощь** во время активации.

10. Вы можете **показать** или **скрыть** различные экраны во время активации устройства. Для целей этого учебника выберите для экрана **Секретный код** значение **Показать**, а для остальных экранов — **Скрыть**.

11. Нажмите кнопки **ОК**  >  **Создать**.

## <a name="sync-managed-devices"></a>Синхронизация управляемых устройств

Теперь вы можете увидеть, какие устройства назначены этому токену.

1. В Intune на портале Azure последовательно выберите **Регистрация устройства** > **Регистрация Apple** > **Токены программы регистрации**, выберите токен в списке, а затем щелкните **Устройства** > **Синхронизировать**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Назначение профиля регистрации устройствам iOS

Устройствам нужно назначить профиль программы регистрации, чтобы можно было их зарегистрировать.

1. В Intune на портале Azure выберите **Регистрация устройства** > **Регистрация Apple** > **Токены программы регистрации**, а затем выберите токен в списке.
2. Выберите **Устройства** > выберите устройства в списке > **Назначить профиль**.
3. В разделе **Назначение профиля** выберите профиль для устройств и нажмите **Назначить**.

## <a name="distribute-devices-to-users"></a>Распределение устройств между пользователями

Вы настроили управление и синхронизацию между Apple и Intune и назначили профиль, чтобы разрешить регистрацию устройств DEP. Теперь вы можете распределить устройства между пользователями. Устройствам со сходством пользователей требуется, чтобы каждому пользователю была назначена лицензия Intune.

## <a name="clean-up-resources"></a>Очистка ресурсов

Если вы не планируете далее использовать устройства Autopilot, их можно удалить.

- Если устройства зарегистрированы в Intune, сначала [удалите их на портале Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Дальнейшие шаги

Ознакомьтесь со сведениями о других параметрах, доступных для регистрации устройств iOS.

> [!div class="nextstepaction"]
> [Подробная статья о регистрации устройств iOS в программе DEP](device-enrollment-program-enroll-ios.md)