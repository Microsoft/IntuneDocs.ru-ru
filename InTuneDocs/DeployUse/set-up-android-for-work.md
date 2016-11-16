---
title: "Настройка управления Android for Work | Microsoft Intune"
description: "Включение управления мобильными устройствами (MDM) для устройств Android for Work с помощью Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 56988f0a69e6ff281439e6e77d1814ec130c8b49
ms.openlocfilehash: d5000db99bf2325e062274e29bc663f20d37d369


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Включение регистрации устройств Android for Work

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Чтобы включить управление устройствами Android for Work, в Intune необходимо добавить привязку Android for Work. Для регистрации устройств, которые поддерживают Android for Work, но ранее были зарегистрированы как обычные устройства Android, их регистрацию необходимо отменить, а затем снова зарегистрировать.

## <a name="add-android-for-work-binding-for-intune"></a>Добавление привязки Android for Work для Intune

1. **Настройка Intune**<br>
Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами](prerequisites-for-enrollment.md#set-mobile-device-management-authority) службу **Microsoft Intune** и настроив MDM.

2. **Настройка привязки Android for Work**<br>
    В качестве пользователя с правами администратора откройте [консоль администрирования Microsoft Intune](http://manage.microsoft.com), последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Android for Work** и нажмите кнопку **Настроить**, чтобы открыть веб-сайт Android for Work в Google Play. Он откроется на новой вкладке в браузере.

3. **Вход в Google**<br>
   На странице входа в Google выполните вход с учетной записью Google, которая будет связана со всеми задачами управления устройствами Android for Work для этого клиента. Это может быть учетная запись Google, общая для всех администраторов, управляющих Intune. Это учетная запись Google, которая используется в организации для управления и публикации приложений в консоли Play for Work.

4. **Сведения об организации**<br>
   Укажите наименование своей компании в поле **Название организации**. Для параметра **Поставщик услуг Enterprise mobility management (EMM)** должно быть указано значение *Microsoft Intune*. Примите соглашение Android for Work и нажмите кнопку **Подтвердить**. Ваш запрос будет обработан.

## <a name="specify-android-for-work-enrollment-settings"></a>Настройка параметров регистрации Android for Work
   Android for Work поддерживается только на некоторых устройствах Android. См. [Требования к Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") компании Google.  Любое устройство, которое поддерживает Android for Work, также поддерживает обычное управление Android.  Intune позволяет задать способ управления поддерживаемыми устройствами Android for Work.

   - **Управлять всеми устройствами как Android** — отключено. Все устройства Android, включая устройства, поддерживающие Android for Work, будут зарегистрированы как обычные устройства Android.
   - **Управлять поддерживаемыми устройствами как Android for Work** — включено. Все устройства, поддерживающие Android for Work, регистрируются как устройства Android for Work. Любое устройство Android, которое не поддерживает Android for Work, регистрируется как обычное устройство Android.
   - **Управлять поддерживаемыми устройствами как Android for Work только для пользователей из этих групп пользователей** — тестовый режим. Позволяет осуществлять управление Android for Work только для ограниченного набора пользователей. Устройства, поддерживающие Android for Work, регистрируются как устройства Android for Work, только для членов выбранных групп. Все остальные устройства регистрируются как устройства Android.

## <a name="next-steps-for-android-for-work"></a>Дальнейшие действия для управления Android for Work
После настройки привязки и параметров Android for Work можно выполнить следующие действия.
- [Развертывание приложений Android for Work](android-for-work-apps.md)
- [Добавление политик конфигурации Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Отмена привязки учетной записи администратора Android for Work

Вы можете отменить регистрацию и управление Android for Work. Нажатие кнопки **Отменить привязку** отменяет регистрацию всех зарегистрированных устройств Android for Work и удаляет связь между учетной записью Android for Work и Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Отмена привязки учетной записи Android for Work

1. **Отмена привязки Android for Work**<br>
    В качестве пользователя с правами администратора откройте [консоль администрирования Microsoft Intune](http://manage.microsoft.com), последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Android for Work** и нажмите кнопку **Отменить привязку**.

2. **Согласие на удаление привязки Android for Work**<br>
  Нажмите кнопку **Да**, чтобы удалить привязку и отменить регистрацию всех устройств Android for Work в Intune.



<!--HONumber=Nov16_HO1-->


