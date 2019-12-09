---
title: Настройка Google Chrome для устройств Android с помощью Intune
titleSuffix: Microsoft Intune
description: Используйте политики конфигурации Intune с Google Chrome для устройств Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: c344a518890a2309a7805d61a5675e2646029bbb
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564045"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Настройка Google Chrome для устройств Android с помощью Intune 

Используйте политики конфигурации приложений Intune, чтобы настроить Google Chrome для устройств Android. Параметры приложения могут быть применены автоматически. Например, можно специально задать закладки и URL-адреса, которые вы хотите заблокировать или разрешить.

## <a name="prerequisites"></a>Предварительные условия

- Устройство пользователя Android для бизнеса должно быть зарегистрировано в Intune. Дополнительные сведения см. в статье [Настройка регистрации устройств с рабочим профилем Android для бизнеса](~/enrollment/android-work-profile-enroll.md).
- Google Chrome добавляется в качестве приложения, управляемого Google Play. Дополнительные сведения об управляемом Google Play см. в разделе [Подключение учетной записи Intune к учетной записи управляемого Google Play](~/enrollment/connect-intune-android-enterprise.md).

## <a name="add-the-google-chrome-app-to-intune"></a>Добавление приложения Google Chrome в Intune

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Выберите **Приложения** > **Все приложения** > **Добавить**, затем добавьте приложение **Управляемый Google Play**.
3. Перейдите в раздел Управляемый Google Play, выполните поиск с помощью **Google Chrome** и утвердите.

    ![Поиск и утверждение Google Chrome](~/apps/media/apps-configure-chrome-android/search.png)

4. Назначьте Google Chrome группе пользователей в качестве требуемого типа приложения. Google Chrome будет автоматически развернут при регистрации устройства в Intune.

Дополнительные сведения о добавлении Управляемого Google Play приложения в Intune см. в разделе [Приложения магазина в управляемом Google Play](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps).

## <a name="add-app-configuration-for-managed-ae-devices"></a>Добавление конфигурации приложения для управляемых устройств AE

1. В панели [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) выберите **Политики конфигурации приложения** > **Добавить**.
2. Добавьте имя политики, выберите **Управляемые устройства** в поле "Тип регистрации устройства" и **Android** в поле "Платформа".

    ![Добавление политики конфигурации Google Chrome](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. Щелкните **Связанное приложение** и выберите **Google Chrome** .

    ![Выбор Google Chrome в разделе "Связанное приложение"](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Щелкните **Параметры конфигурации**, выберите **Применить конструктор конфигураций**, а затем щелкните **Добавить**, чтобы выбрать ключи конфигурации.

    ![Добавьте "Использовать конструктор конфигурации"](~/apps/media/apps-configure-chrome-android/configuration.png)

    Ниже приведен пример общих параметров.
    - **Блокировать доступ к списку URL-адресов** : `["*"]`
    - **Разрешить доступ к списку URL-адресов** : `["baidu.com", "youtube.com", "chromium.org", "chrome://*"]`
    - **Управляемые закладки**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Доступность в режиме инкогнито**: `Incognito mode disabled`

    После добавления параметров конфигурации с помощью конструктора конфигураций они будут перечислены в таблице. 

    ![Общие параметры](~/apps/media/apps-configure-chrome-android/common-settings.png)

    Указанные выше параметры создают закладки и блокируют доступ ко всем URL-адресам, кроме `baidu.com`, `yahoo.com`, `chromium.org` и `chrome://`.

5. Щелкните **OK** и **Добавить**, чтобы добавить политику конфигурации в Intune.
6. Назначьте эту политику конфигурации группе пользователей. Дополнительные сведения см. в статье [Назначение приложений группам с помощью Microsoft Intune](~/apps/apps-deploy.md). 

## <a name="verify-the-device-settings"></a>Проверка параметров устройства

После регистрации устройства Android в Android для бизнеса управляемое приложение Google Chrome со значком портфеля будет развернуто автоматически.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Запустите Google Chrome, и вы увидите примененные параметры.

   Закладки:<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   Заблокированный URL-адрес:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   Разрешить URL-адрес:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Вкладка в режиме инкогнито:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Диагностика

1. Проверяйте портал Intune, чтобы отслеживать состояние развертывания политики.

    ![Мониторинг состояния развертывания политики](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Запустите Google Chrome и посетите **chrome://policy**. Мы можем подтвердить, что настройки успешно применены.

    ![Подтверждение успешного применения настроек](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Дополнительные сведения

- [Добавление политик конфигурации приложений для управляемых устройств Android для бизнеса](~/app-configuration-policies-use-android.md)
- [Список корпоративных политик Chrome](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Дальнейшие шаги

- Дополнительные сведения о полностью управляемых устройствах с Android для бизнеса см. в статье [Настройка регистрации полностью управляемых устройств Android для бизнеса в Intune (предварительная версия)](~/enrollment/android-fully-managed-enroll.md).
