---
title: Использование шаблонов для устройств Windows 10 в Microsoft Intune — Azure | Документация Майкрософт
description: Административные шаблоны в Microsoft Intune можно использовать для создания групп параметров для устройств Windows 10. Используйте эти параметры в профиле конфигурации устройства для управления приложениями Office, Microsoft Edge, функций безопасности в Internet Explorer, управления доступом к OneDrive, использования функций удаленного рабочего стола, включения автоматического воспроизведения, установки параметров управления питанием, HTTP-печати, использования других параметров входа в систему и контроля размера журнала событий.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b41405e2256d6d2608b05a9c7e8a40cbb3ab349
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724299"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Использование шаблонов Windows 10 для настройки параметров групповой политики в Microsoft Intune

При управлении устройствами в вашей организации вам стоит создать группы параметров, которые применяются к различным группам устройств. Например, у вас есть несколько групп устройств. Для GroupA вы хотите назначить определенный набор параметров. Для GroupB вы хотите назначить другой набор параметров. Также можно настроить простое представление параметров.

Можно выполнить этот задачу, используя **административные шаблоны** в Microsoft Intune. Административные шаблоны содержат сотни параметров для управления функциями в Microsoft Edge 77 и последующих версий, Internet Explorer и приложениях Microsoft Office, функциями удаленного рабочего стола, доступом к OneDrive, управления паролями и ПИН-кодами и многим другим. Эти параметры позволяют администраторам групп управлять групповыми политиками с помощью облака.

Параметры Windows похожи на параметры групповой политики (GPO) в Active Directory (AD). Эти параметры встроены в Windows и являются [параметрами с поддержкой ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies), которые используют XML. Параметры Office и Microsoft Edge включены в файлы ADMX и используют параметры ADMX в [файлах административных шаблонов Office](https://www.microsoft.com/download/details.aspx?id=49030) и [файлах административных шаблонов Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise). Но шаблоны в Intune являются полностью облачными. Это простой способ настройки и поиска нужных параметров.

**Административные шаблоны** встроены в Intune и не требуют настройки, в том числе с помощью OMA-URI. В рамках решения в системе управления мобильными устройствами используйте эти параметры шаблона как единое средство для управления устройствами Windows 10.

В этой статье описано, как создать шаблон для устройств Windows 10, и показано, как фильтровать все доступные параметры в Intune. При создании шаблона создается профиль конфигурации устройства. Затем можно назначить или развернуть этот профиль для устройств Windows 10 в вашей организации.

## <a name="before-you-begin"></a>Подготовка к работе

- Некоторые из этих параметров доступны, начиная с Windows 10, версия 1703 (RS2). Не все параметры доступны во всех выпусках Windows. Для оптимизации рекомендуется использовать Windows 10 Корпоративная, версия 1903 (19H1) и выше.

- Параметры Windows используют [политику поставщиков службы конфигурации Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies). Поставщики CSP работают в разных выпусках Windows, таких как Домашняя, Профессиональная, Корпоративная и т. д. Чтобы узнать, работает ли поставщик CSP в определенном выпуске, см. статью о [поставщиках CSP политики Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies).

## <a name="create-a-template"></a>Создание шаблона

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя**. Введите имя для профиля.
    - **Описание** Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите **Windows 10 и более поздних версий**.
    - **Тип профиля**. Выберите **Административные шаблоны**.

4. Выберите **Создать**. В новом окне выберите **Параметры**. Каждый параметр представлен в списке, и можно использовать кнопки со стрелками, чтобы просмотреть дополнительные параметры:

    ![См. пример списка параметров и воспользуйтесь кнопками "Вперед" и "Назад"](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > Параметры Windows в Intune сопоставляются с путем локальной групповой политики, который отображается в редакторе локальных групповых политик (`gpedit`).

5. По умолчанию в раскрывающемся списке отображаются **все продукты**. Параметры в списке можно также отфильтровать так, чтобы отображались только параметры **Windows**, только параметры **Office** или только параметры **Microsoft Edge версии 77 и последующих**.

    ![Фильтрация списка для отображения всех параметров Windows или Office в административных шаблонах в Intune](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > Параметры Microsoft Edge применяются к:
    >
    > - Microsoft Edge 77 и последующих версий. Сведения о настройке Microsoft Edge 45 и предшествующих версий см. в разделе о [параметрах ограничений устройств в браузере Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).
    > - Windows 10 RS4 и последующим версиям с установленным исправлением [KB4512509](https://support.microsoft.com/kb/4512509).
    > - Windows 10 RS5 и последующим версиям с установленным исправлением [KB4512534](https://support.microsoft.com/kb/4512534).
    > - Windows 10 19H1 и последующим версиям с установленным исправлением [KB4512941](https://support.microsoft.com/kb/4512941).

6. Выберите любой параметр. Например, отфильтруйте параметры, выбрав **Office** в раскрывающемся меню, и щелкните **Перейти в режим ограниченного просмотра**. Появится подробное описание параметра. Задайте значение **Включено**, **Отключено** или **Не настроено** (задано по умолчанию). Также предоставляется подробное описание того, что происходит при выборе значений **Включено**, **Отключено** или **Не настроено**.
7. Нажмите кнопку **OK**, чтобы сохранить изменения.

Продвигайтесь через список параметров и настройте параметры, которые требуются в вашей среде. Ниже приводится несколько примеров.

- Используйте **параметры уведомлений макросов VBA**, чтобы обрабатывать макросы VBA в разных программах Microsoft Office, включая Word и Excel.
- Используйте параметр **Разрешить скачивание файлов**, чтобы разрешить или запретить скачивание в Internet Explorer.
- Используйте параметр **Требовать пароль при выходе из спящего режима (питание от сети)** , чтобы запрашивать у пользователей пароль при выходе устройств из спящего режима.
- Используйте параметр **Скачивать неподписанные элементы управления ActiveX**, чтобы запретить пользователям скачивать неподписанные элементы управления ActiveX в Internet Explorer.
- Используйте параметр **Отключить восстановление системы**, чтобы разрешить или запретить пользователям запускать восстановление системы на устройстве.
- Используйте параметр **Разрешить импорт из избранного**, чтобы разрешить или запретить пользователям импортировать избранное из другого браузера в Microsoft Edge.
- И это еще не все!

## <a name="find-some-settings"></a>Найти параметры

В этих шаблонах доступны сотни параметров. Чтобы упростить поиск параметров, используйте встроенные функции:

- В шаблоне выберите столбцы **Параметры**, **Состояние**, **Тип параметра**или **Путь** для сортировки списка. Например, выберите столбец **Путь**, чтобы увидеть все параметры по пути `Microsoft Excel`:

  ![Щелкните путь, чтобы отобразить все параметры, сгруппированные по пути групповой политики или ADMX в административных шаблонах в Intune.](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- В шаблоне используйте поле **поиска**, чтобы найти определенные параметры. Поиск можно выполнять по имени параметра или пути. Например, выполните поиск по фразе `copy`. Отображаются все параметры с `copy`:

  ![Поиск по слову "копировать", при котором отображаются все соответствующие параметры Windows и Office в административных шаблонах в Intune](./media/administrative-templates-windows/search-copy-settings.png) 

  Например, используйте поиск по фразе `microsoft word`. Появятся все параметры, которые можно задать в программе Microsoft Word. Используйте поиск `explorer` для просмотра всех параметров Internet Explorer, которые можно добавить в шаблон.

## <a name="next-steps"></a>Дальнейшие шаги

Профиль создан, но пока ничего не делает. Далее нужно провести [назначение шаблона, также называемого профилем,](device-profile-assign.md) и [отслеживать его состояние](device-profile-monitor.md).