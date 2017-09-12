---
title: "Подготовка к регистрации устройств Android в Intune"
titlesuffix: Azure portal
description: "Узнайте, как подготовить устройства Android к регистрации в Intune.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ba809003dbdf63377a0b87b747c9865393786d72
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-android-devices"></a>Регистрация устройств Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Как администратор Intune вы получаете возможность управления устройствами Android, в том числе устройствами Samsung Knox Standard. Кроме того, вы можете управлять рабочим профилем на устройствах [Android for Work](#enable-enrollment-of-android-for-work-devices).

Устройства под управлением Samsung KNOX Standard теперь поддерживаются для управления несколькими пользователями с помощью Intune. Это означает, что пользователи могут выполнять вход и выход на устройстве с помощью учетных данных Azure AD, а устройством можно управлять централизованно, независимо от того, используется оно или нет. Когда пользователь входит в систему, он получает доступ к приложениям, кроме того, к нему применяются соответствующие политики. После выхода пользователя из системы все данные приложения удаляются.

## <a name="prerequisite"></a>Необходимое условие

Чтобы подготовиться к управлению мобильными устройствами, в качестве центра MDM необходимо указать **Microsoft Intune**. Инструкции см. в статье [Установка центра управления мобильными устройствами](mdm-authority-set.md). Этот параметр указывается только один раз при первой настройке Intune для управления мобильными устройствами.

## <a name="set-up-android-enrollment"></a>Настройка регистрации устройств Android

По умолчанию в службе Intune разрешена регистрация устройств Android и Samsung Knox Standard.

Чтобы заблокировать регистрацию всех или только личных устройств Android, см. инструкции в разделе [Установка ограничений по типу устройства](enrollment-restrictions-set.md).

Чтобы обеспечить управление устройствами, пользователям необходимо зарегистрировать их, скачав приложение корпоративного портала Intune, которое доступно в Google Play, а затем открыв это приложение и выполнив указания по установке. Когда устройства Android будут зарегистрированы в системе управления, вы сможете [назначать политики соответствия требованиям](compliance-policy-create-android.md), [управлять приложениями](app-management.md) и выполнять другие действия.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Включение регистрации устройств Android for Work

Чтобы включить управление рабочим профилем на устройствах, [поддерживающих Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), необходимо добавить привязку Android for Work в Intune. Что касается регистрации устройств, которые поддерживают Android for Work, но ранее были зарегистрированы как обычные устройства Android, их регистрацию необходимо отменить, а затем снова зарегистрировать.

## <a name="add-android-for-work-binding-for-intune"></a>Добавление привязки Android for Work для Intune

1. **Настройка Intune MDM**<br>
Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [задав в качестве центра сертификации управления мобильными устройствами](mdm-authority-set.md) службу **Microsoft Intune**.
2. **Настройка привязки Android for Work**<br>
    Войдите с правами администратора Intune на портал Azure и выберите **Другие службы** > **Мониторинг и управление** > **Intune**.

    1. В колонке **Intune** выберите элемент **Регистрация устройств** > **Регистрация Android for Work** и щелкните **Настройка**, чтобы открыть веб-страницу Android for Work в магазине Google Play. Он откроется на новой вкладке в браузере.
  ![Снимок экрана, содержащий ссылку на настройку привязки к Android for Work](./media/android-work-bind.png)

    2. **Вход в Google**<br>
   На странице входа в Google выполните вход с учетной записью Google, которая будет связана со всеми задачами управления устройствами Android for Work для этого клиента. Это учетная запись Google, которая совместно используется ИТ-администраторами в организации для управления и публикации приложений в консоли Play for Work.

    3. **Указание данных об организации**<br>
   Укажите наименование своей компании в поле **Название организации**. Для параметра **Поставщик услуг Enterprise mobility management (EMM)** должно быть указано значение *Microsoft Intune*. Примите соглашение Android for Work и нажмите кнопку **Подтвердить**. Ваш запрос будет обработан.

## <a name="specify-android-for-work-enrollment-settings"></a>Настройка параметров регистрации Android for Work
   Android for Work поддерживается только на некоторых устройствах Android. См. [Требования к Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") компании Google. Любое устройство, которое поддерживает Android for Work, также поддерживает обычное управление Android.  Intune позволяет задать способ управления поддерживаемыми устройствами Android for Work.

   - **Управлять всеми устройствами как Android** — все устройства Android, включая устройства, поддерживающие Android for Work, будут зарегистрированы как обычные устройства Android.
   - **Управлять поддерживаемыми устройствами как Android for Work** — все устройства, поддерживающие Android for Work, регистрируются как устройства Android for Work. Любое устройство Android, которое не поддерживает Android for Work, регистрируется как обычное устройство Android.
   - **Управлять поддерживаемыми устройствами как Android for Work только для пользователей из этих групп пользователей** — позволяет осуществлять управление Android for Work только для ограниченного набора пользователей. Устройства, поддерживающие Android for Work, регистрируются как устройства Android for Work, только для членов выбранных групп. Все остальные устройства регистрируются как устройства Android. Это удобно при реализации пилотных проектов Android for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Сообщите пользователям, как зарегистрировать свои устройства, чтобы получить доступ к ресурсам компании

Вам следует сообщить пользователям о том, что им необходимо перейти в Google Play, чтобы скачать приложение корпоративного портала Intune, а затем открыть это приложение и зарегистрировать устройство, выполнив указания. Приложение помогает пользователям пройти процедуру регистрации, уведомляя их о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.

Вы также можете отправить им ссылку инструкции по регистрации в Интернете: [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Дополнительные сведения о других задачах для пользователей см. в статьях:

- [Ресурсы по пользовательскому интерфейсу Microsoft Intune](end-user-educate.md)
- [Использование устройства Android с Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Отмена привязки учетной записи администратора Android for Work

Вы можете отменить регистрацию и управление Android for Work. Нажатие кнопки **Отменить привязку** в консоли администрирования Intune отменяет регистрацию всех зарегистрированных устройств Android for Work и удаляет связь между учетной записью Android for Work и Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Отмена привязки учетной записи Android for Work

1. **Отмена привязки Android for Work**<br>
    Войдите с правами администратора Intune на портал Azure и выберите **Другие службы** > **Мониторинг и управление** > **Intune**.  В колонке **Intune** выберите элемент **Регистрация устройств** > **Регистрация Android for Work**, а затем щелкните **Отменить привязку**.

2. **Согласие на удаление привязки Android for Work**<br>
  Нажмите кнопку **Да**, чтобы удалить привязку и отменить регистрацию всех устройств Android for Work в Intune.
