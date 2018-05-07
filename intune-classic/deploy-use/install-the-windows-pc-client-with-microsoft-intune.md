---
title: Установка клиентского программного обеспечения для ПК
description: В этом руководстве содержатся сведения об управлении ПК Windows с помощью клиентского программного обеспечения Microsoft Intune.
keywords: ''
author: nathbarn
ms.author: nathbarn
ms.date: 07/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 85d77356d7a864f3d7703e087528fe0cefafb312
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a>Установка программного клиента Intune на компьютерах Windows

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Компьютеры под управлением Windows можно зарегистрировать с помощью установки клиентского программного обеспечения Intune. Клиентское программное обеспечение Intune можно установить одним из следующих способов:

- ИТ-администратор может использовать один из следующих способов: установка вручную, групповая политика или установка из образа диска;

- установка клиентского программного обеспечения пользователями вручную.

Клиентское программное обеспечение Intune содержит минимальный набор программного обеспечения, необходимый для регистрации компьютера в службе управления Intune. Когда компьютер будет зарегистрирован, клиентское программное обеспечение Intune скачает полное клиентское программное обеспечение, требуемое для управления компьютером.

Эта серия скачиваний минимизирует влияние на пропускную способность сети и сокращает время, требуемое для первоначальной регистрации компьютера в Intune. Она также предоставляет новейшее программное обеспечение клиенту после завершения второго скачивания.

Одна лицензия Intune позволяет установить клиентское ПО Intune на пять компьютеров.

## <a name="download-the-intune-client-software"></a>Скачать клиентское программное обеспечение Intune

Во всех методах, кроме самостоятельной установки клиентского программного обеспечения Intune пользователями, предполагается, что программное обеспечение будет скачано и развернуто для пользователей ИТ-администраторами.

1. В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) выберите пункты **Администрирование** &gt; **Загрузка клиентского программного обеспечения**.

   ![Загрузка клиентского ПО Intune](../media/pc-sa-client-download.png)

2. На странице **Загрузка клиентского программного обеспечения** нажмите кнопку **Загрузить клиентское программное обеспечение**. После этого сохраните пакет **Microsoft_Intune_Setup.zip**, который содержит программное обеспечение, в безопасном месте в сети.

   Пакет установки клиентского программного обеспечения Intune содержит определенные уникальные сведения о вашей учетной записи, содержащиеся во внедренном сертификате. Если доступ к установочному пакету получат неавторизованные пользователи, они смогут зарегистрировать компьютеры в учетной записи, указанной во внедренном сертификате, и получить доступ к ресурсам организации.

3. Извлеките содержимое пакета установки и сохраните его в надежной сетевой папке.

    > [!IMPORTANT]
    > Не переименовывайте и не удаляйте извлеченный файл **ACCOUNTCERT**, так как в этом случае установка клиентского программного обеспечения будет невозможна.

## <a name="deploy-the-client-software-manually"></a>Развертывание клиентского программного обеспечения вручную

На компьютерах, на которых будет установлен клиент программного обеспечения, перейдите в папку с установочными файлами клиентского программного обеспечения. Затем запустите файл **Microsoft_Intune_Setup.exe**, чтобы установить клиентское программное обеспечение.

> [!NOTE]
> Состояние установки отображается при наведении указателя мыши на значок на панели задач клиентского компьютера.

## <a name="deploy-the-client-software-by-using-group-policy"></a>Развертывание клиентского программного обеспечения с помощью групповой политики

1.  В папке с файлами **Microsoft_Intune_Setup.exe** и **MicrosoftIntune.accountcert** выполните следующую команду для извлечения программ установки установщика Windows для 32- и 64-разрядных компьютеров.

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Скопируйте файлы **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** и **MicrosoftIntune.accountcert** в сетевую папку, доступную всем компьютерам, на которых будет установлено клиентское программное обеспечение.

    > [!IMPORTANT]
    > Не переименовывайте и не разделяйте файлы, так как в этом случае установка клиентского программного обеспечения не будет выполнена.

3.  С помощью групповой политики разверните программное обеспечение на компьютерах в сети.

    Дополнительные сведения об автоматическом развертывании программного обеспечения с помощью групповой политики см. в статье [Групповая политика для начинающих](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="deploy-the-client-software-as-part-of-an-image"></a>Развертывание клиентского программного обеспечения в составе образа
Клиентское программное обеспечение Intune можно развернуть в составе образа операционной системы, выполнив следующую приведенную в качестве примера процедуру.

1.  Скопируйте файлы установки клиента, **Microsoft_Intune_Setup.exe** и **MicrosoftIntune.accountcert**, в папку **%Systemdrive%\Temp\Microsoft_Intune_Setup** на эталонном компьютере.

2.  Создайте запись реестра **WindowsIntuneEnrollPending**, добавив в сценарий **SetupComplete.cmd** следующую команду:

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  Добавьте следующую команду в сценарий **setupcomplete.cmd**, чтобы запустить пакет регистрации с аргументом /PrepareEnroll:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > Сценарий **SetupComplete.cmd** позволяет программе установки Windows вносить изменения в систему до того, как пользователь выполнит вход. Аргумент командной строки **/PrepareEnroll** подготавливает целевой компьютер к автоматической регистрации в Intune после того, как программа установки Windows завершит работу.

4.  Поместите **SetupComplete.cmd** в папку **%Windir%\Setup\Scripts** на эталонном компьютере.

5.  Запишите образ эталонного компьютера, а затем разверните его на целевых компьютерах.

    После перезагрузки целевого компьютера по завершении выполнения программы установки Windows будет создан раздел реестра **WindowsIntuneEnrollPending**. Пакет регистрации проверяет, зарегистрирован ли компьютер. Если компьютер зарегистрирован, дальнейшие действия не предпринимаются. Если компьютер не зарегистрирован, пакет регистрации создает задачу автоматической регистрации в Microsoft Intune.

    При следующем запланированном запуске задачи автоматической регистрации выполняется проверка на наличие параметра реестра **WindowsIntuneEnrollPending** и предпринимается попытка регистрации целевого компьютера в Intune. Если по какой-либо причине выполнить регистрацию не удается, при следующем запуске задачи будет предпринята повторная попытка. Попытки продолжаются в течение месяца.

    После успешной регистрации или через месяц задача автоматической регистрации Intune, значение реестра **WindowsIntuneEnrollPending** и сертификат учетной записи удаляются с целевого компьютера (в зависимости от того, что произойдет раньше).

## <a name="instruct-users-to-self-enroll"></a>Инструктирование пользователей по самостоятельной регистрации

Пользователи могут установить клиентское программное обеспечение Intune, перейдя на [веб-сайт корпоративного портала](https://portal.manage.microsoft.com). Точные сведения, которые пользователи видят на веб-портале, могут отличаться. Это зависит от центра MDM вашей учетной записи, а также платформы и версии ОС пользовательского компьютера.

Если пользователям не назначена лицензия Intune или если в качестве центра MDM организации не задана служба Intune, пользователям недоступны варианты регистрации.

Если пользователям назначена лицензия Intune и в качестве центра MDM организации задана служба Intune.

- Пользователям компьютеров с ОС Windows 7 и Windows 8 предлагается ТОЛЬКО вариант регистрации в Intune путем скачивания и установки на компьютерах клиентского ПО, уникального для организации.

- Пользователям компьютеров с Windows 10 и Windows 8.1 предлагаются два вариант регистрации.

  -  **Регистрация компьютера как мобильного устройства**. Пользователи нажимают кнопку **Сведения о регистрации** и получают инструкции по регистрации компьютера как мобильного устройства. Эта кнопка заметна в первую очередь, так как регистрация в системе управления мобильными устройствами считается предпочтительным способом регистрации, предлагаемым по умолчанию. Но этот способ не относится к теме раздела, так как в нем рассматривается только установка клиентского программного обеспечения.
  - **Регистрация компьютера с помощью клиентского программного обеспечения Intune**. Вам следует сообщить пользователям о том, что им необходимо щелкнуть ссылку **Щелкните здесь, чтобы скачать**, чтобы выполнить процедуру установки клиентского ПО.

В таблице ниже приведена сводка по способам регистрации.

  ![Способы регистрации по умолчанию для каждой платформы](../media/default-enrollment-options-table.png)

На снимках экрана ниже показано, что видят пользователи при регистрации устройств с помощью программного клиента.

Сначала пользователи получают запрос на идентификацию или регистрацию устройства.

  ![Идентификация или регистрация устройства](../media/identify-device-or-enroll.png)

Чтобы пользователи установили клиентское ПО на ПК, вам следует сообщить, что им необходимо щелкнуть ссылку **Щелкните здесь, чтобы скачать**. Это позволит им скачать клиентское ПО на ПК и пройти процедуру установки. Нажав кнопку **Сведения о регистрации**, пользователи открывают документацию по регистрации в системе управления мобильными устройствами, которая не имеет отношения к этим инструкциям по установке клиентского ПО.

  ![Щелкните ссылку "Щелкните здесь, чтобы скачать"](../media/enroll-your-windows-device.png)

Когда пользователь щелкает ссылку, он видит кнопку **Загрузить ПО**, которую нужно нажать, чтобы начать установку клиентского ПО на компьютере.

  ![Нажмите кнопку "Загрузить ПО"](../media/download-pc-client-software.png)

После этого пользователю предлагается выполнить вход с корпоративными учетными данными.

  ![Вход с использованием учетных данных](../media/sign-in-to-intune.png)

Пользователь переходит на страницу приветствия для установки.

  ![Страница приветствия для установки клиента на ПК](../media/welcome-to-pc-agent-install-wizard.png)

Затем пользователь нажимает кнопку **Далее**, и установка начинается.

  ![Страница приветствия для установки клиента на ПК](../media/welcome-to-pc-agent-install-wizard.png)

По завершении установки пользователь нажимает кнопку **Готово**.

  ![Завершение установки клиента на ПК](../media/completed-the-setup-wizard.png)

Если пользователь попытается зарегистрировать свой компьютер как мобильное устройство после регистрации с помощью клиентского ПО Intune, он увидит экран с сообщением об ошибке, показанный ниже.

  ![Экран, появляющийся в случае, если компьютер уже зарегистрирован](../media/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>Отслеживание и проверка успешного развертывания клиента
Для отслеживания и проверки успешного развертывания клиента можно использовать любую из следующих процедур.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>Проверка установки клиентского программного обеспечения с консоли администрирования Microsoft Intune

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) выберите **Группы** &gt; **Все устройства** &gt; **Все компьютеры**.

2.  В списке найдите компьютеры, взаимодействующие с Intune. Кроме того, можно найти конкретный управляемый компьютер, указав его имя целиком (или любую часть имени) в поле **Поиск устройств**.

3.  Проверьте состояние компьютера в нижней части консоли. Устраните возможные ошибки.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Создание отчета об инвентаризации компьютеров для отображения всех зарегистрированных компьютеров

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) выберите **Отчеты** &gt; **Отчеты об инвентаризации компьютеров**.

2.  На странице **Создание отчета** оставьте значения по умолчанию во всех полях (если не требуется применять фильтры) и нажмите кнопку **Просмотреть отчет**.

3.  В новом окне откроется страница **Отчет об инвентаризации компьютеров** со списком всех компьютеров, успешно зарегистрированных в Intune.

    > [!TIP]
    > Чтобы отсортировать список по содержимому столбца, щелкните заголовок столбца.

## <a name="uninstall-the-windows-client-software"></a>Удаление клиентского программного обеспечения Windows

Отменить регистрацию клиентского программного обеспечения Windows можно двумя способами:

- из консоли администрирования Intune (рекомендуется);
- из командной строки в клиенте.

### <a name="unenroll-by-using-the-intune-admin-console"></a>Отмена регистрации с помощью консоли администрирования Intune

Чтобы отменить регистрацию клиентского программного обеспечения с помощью консоли администрирования Intune, откройте меню **Группы** > **Все компьютеры** > **Устройства**. Щелкните клиент правой кнопкой мыши и выберите параметр **Снять с учета/очистить**.

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a>Отмена регистрации из командной строки в клиенте

Используя командную строку с повышенными привилегиями, выполните одну из указанных ниже команд.

**Метод 1**.

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

**Метод 2** (обратите внимание, что все из этих агентов устанавливаются на каждый SKU Windows).

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall
    wmic product where name="Microsoft Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall
    wmic product where name="Microsoft Policy Platform" call uninstall
    wmic product where name="Microsoft Security Client" call uninstall
    wmic product where name="Microsoft Online Management Client" call uninstall
    wmic product where name="Microsoft Online Management Client Service" call uninstall
    wmic product where name="Microsoft Easy Assist v2" call uninstall
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Microsoft Intune Center" call uninstall
    wmic product where name="Microsoft Online Management Update Manager" call uninstall
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall
    wmic product where name="Microsoft Intune" call uninstall
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall
    wmic product where name="Windows Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Windows Online Management Policy Agent" call uninstall
    wmic product where name="Windows Policy Platform" call uninstall
    wmic product where name="Windows Security Client" call uninstall
    wmic product where name="Windows Online Management Client" call uninstall
    wmic product where name="Windows Online Management Client Service" call uninstall
    wmic product where name="Windows Easy Assist v2" call uninstall
    wmic product where name="Windows Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Windows Intune Center" call uninstall
    wmic product where name="Windows Online Management Update Manager" call uninstall
    wmic product where name="Windows Online Management Agent Installer" call uninstall
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> При отмене регистрации клиента на стороне сервера останется устаревшая запись о соответствующем клиенте. Отмена регистрации осуществляется асинхронно, а так как удалить необходимо девять агентов, процесс может занять до 30 минут.

### <a name="check-the-unenrollment-status"></a>Проверка состояния отмены регистрации

Проверьте адрес "% ProgramFiles%\Microsoft\OnlineManagement" и убедитесь, что в левой части окна отображаются только следующие каталоги.

- AgentInstaller
- Журналы
- Updates
- Общие

### <a name="remove-the-onlinemanagement-folder"></a>Удалите папку OnlineManagement.

В процессе отмены регистрации папка OnlineManagement не удаляется. Подождите 30 минут после удаления и выполните указанную ниже команду. Если выполнить эту команду слишком рано, процесс удаления может еще находиться в неизвестном состоянии. Чтобы удалить папку, запустите командную строку с повышенными привилегиями и выполните следующую команду:

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a>Дальнейшие шаги
[Управление компьютером с Windows с помощью Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Устранение неполадок при настройке клиента](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)
