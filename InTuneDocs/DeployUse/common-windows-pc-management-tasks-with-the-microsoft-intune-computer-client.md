---
title: "Общие задачи управления компьютерами с Windows | Microsoft Intune"
description: "В этом разделе рассматривается управление компьютерами, на которых выполняется клиентское программное обеспечение Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 385ed597e4af569dc5a2b559d693b6c8421f86fa
ms.openlocfilehash: e08fe1cdaa45ba957986511afb60a54da8152677


---

# Общие задачи управления ПК Windows с клиентом Microsoft Intune
В этом разделе рассматривается управление компьютерами, на которых выполняется клиентское программное обеспечение Intune. Если вы еще не установили клиент на своих компьютерах, см. статью [Установка клиента на компьютере Windows с помощью Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Использование политик для упрощения управления компьютерами
### Управление брандмауэром Windows
Политики упрощают администрирование параметров брандмауэра Windows на управляемых компьютерах. Подробные сведения см. в статье [Защита компьютеров с Windows с помощью политик брандмауэра Windows в Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Управление Microsoft Intune Center
Microsoft Intune Center позволяет пользователям:

-   получать приложения с корпоративного портала;

-   проверять наличие обновлений;

-   управлять программой Microsoft Intune Endpoint Protection;

<!--- -   Request remote assistance.--->

Microsoft Intune Center устанавливается на всех управляемых компьютерах. В политике Intune Center можно настроить следующие параметры, которые будут отображаться для пользователей в Microsoft Intune Center:

|Параметр политики|Подробные сведения|
|------------------|--------------------|
|**Имя**|Имя администратора, который управляет компьютером.<br /><br />Максимальная длина: 40 символов|
|**Номер телефона**|Номер телефона администратора, который управляет компьютером.<br /><br />Максимальная длина: 20 символов.|
|**Адрес электронной почты**|Адрес электронной почты администратора, который управляет компьютером.<br /><br />Максимальная длина: 40 символов|
|**Название веб-сайта**|Название веб-сайта технической поддержки для пользователей.<br /><br />Максимальная длина: 40 символов|
|**URL-адрес веб-сайта**|URL-адрес веб-сайта технической поддержки.<br /><br />Максимальная длина: 150 символов.|
|**Примечания**|Примечание, отображаемое для пользователей.<br /><br />Максимальная длина: 120 символов.|

### Настройка параметров обновления программного обеспечения
Используйте политики для настройки параметров, которые используются управляемыми компьютерами для поиска и загрузки обновлений программного обеспечения Майкрософт и других поставщиков. Дополнительные сведения см. в разделе [Обновление программного обеспечения на компьютерах Windows с помощью Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Настройка параметров Endpoint Protection
Используйте политики для настройки параметров для Endpoint Protection и развертывания их на управляемых компьютерах. Они включают расписания проверок, действия при обнаружении вредоносных программ и многое другое. Дополнительные сведения см. в статье [Обеспечение защиты компьютеров с ОС Windows с помощью Endpoint Protection для Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Просмотр данных инвентаризации оборудования и программного обеспечения
Intune собирает подробные сведения об оборудовании и программном обеспечении управляемых компьютеров. Ниже приведены процедуры

-   создания отчета, содержащего данные об аппаратных возможностях компьютеров;

-   создания отчета, содержащего список программного обеспечения, установленного на каждом компьютере;

-   обновления данных инвентаризации компьютеров для гарантии актуальности данных в отчете.

### Вывод сведений о компьютерах

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Отчеты** &gt; **Отчеты об инвентаризации компьютеров**.

2.  На странице **Создать новый отчет** примите значения по умолчанию или настройте их для фильтрации результатов, возвращаемых отчетом. Например, можно выбрать для отображения в отчете только те компьютеры, на которых выполняется Windows 8.1.

3.  Щелкните **Просмотреть отчет**, чтобы открыть **Отчет об инвентаризации компьютеров** в новом окне.

    Отчет можно отсортировать по любому столбцу, например **Имя**, **Тип корпуса** или **Изготовитель**, щелкнув заголовок столбца.

### Вывод сведений о программном обеспечении, установленном на компьютерах

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Отчеты** &gt; **Отчеты об обнаруженном ПО**.

2.  На странице **Создать новый отчет** примите значения по умолчанию или настройте их для фильтрации результатов, возвращаемых отчетом. Например, можно выбрать для отображения в отчете только программное обеспечение, выпущенное корпорацией Майкрософт.

3.  Щелкните **Просмотреть отчет**, чтобы открыть **Отчет об обнаруженном ПО** в новом окне.

    Отчет можно отсортировать по любому столбцу, например **Имя**, **Издатель** или **Категория**, щелкнув заголовок столбца. Развернув обновления в списке с помощью стрелки рядом с элементом списка, можно просмотреть дополнительные сведения (например, о компьютерах, на которых установлено обновление).

### Обновление данных инвентаризации компьютера для гарантии их актуальности

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Группы** &gt; **Все устройства** (или другую группу с компьютером, инвентаризационные данные которого требуется обновить).

2.  Выберите компьютер или нажмите и удерживайте клавишу **CTRL** , чтобы выбрать несколько компьютеров.

3.  На панели задач щелкните **Удаленные задачи** &gt; **Обновить данные инвентаризации**.

4.  Чтобы просмотреть состояние задачи, щелкните **Удаленные задачи** в правом нижнем углу страницы.

    В диалоговом окне **Состояние задачи** указываются текущие удаленные задачи, состояние задач, имена устройств и ошибки, а также ссылка на сведения об устранении неполадок.


## Удаленная перезагрузка компьютера Windows

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Группы** &gt; **Все устройства** (или другую группу с компьютером, который требуется перезапустить).

2.  Выберите один или несколько компьютеров, а затем щелкните **Удаленные задачи** &gt; **Перезагрузить компьютер**.

3.  Чтобы просмотреть состояние задачи, щелкните **Удаленные задачи** в правом нижнем углу страницы.

4.  В диалоговом окне **Состояние задачи** просмотрите текущие удаленные задачи, состояние задач, имена устройств и сообщения об ошибках.

## Снятие компьютера с учета

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Группы** &gt; **Все устройства** (или другую группу с компьютером, который требуется снять с учета).

2.  Выберите устройства для снятия с учета, а затем щелкните **Снять с учета/очистить**.

Чтобы повторно зарегистрировать компьютер в Intune, переустановите клиентское программное обеспечение на компьютере, используя сведения в разделе [Установка клиента на компьютере Windows с помощью Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Если компьютеру не удается подключиться к Intune, в рабочей области **Панель мониторинга** отобразится сообщение.

При снятии компьютера с учета происходит следующее.

-   Он удаляется из данных инвентаризации Intune, а связанная с ним лицензия становится доступной для повторного использования.

-   Его состояние больше не отображается в консоли Intune.

-   Intune удаляет клиентское программное обеспечение с компьютера. Если компьютер не подключен к службе Intune, клиентское программное обеспечение будет удалено при следующем подключении.

-   Microsoft Intune Endpoint Protection удаляется с компьютера. Если на компьютере установлено другое приложение конечной точки, которое было отключено, его можно повторно включить после удаления Microsoft Intune Endpoint Protection, чтобы обеспечить защиту компьютеров.

-   Все политики удаляются с компьютера, а значения, заданные политикой, изменяются.

-   Компьютер перестает получать обновления программного обеспечения и определений вредоносных программ от службы Intune.

-   В зависимости от настроек снятые с учета компьютеры могут продолжать получать обновления с помощью служб Windows Server Update Services, Центра обновления Windows или Центра обновления Майкрософт.

    > [!IMPORTANT]
    > Если клиентское ПО устанавливалось с помощью объекта групповой политики, его необходимо удалить, прежде чем можно будет удалить клиентское ПО, чтобы предотвратить повторную установку программного обеспечения.

    Если не удается удалить клиент, прочтите раздел [Устранение неполадок Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) для получения дополнительных сведений.

## Управление связыванием пользователей и устройств
Прежде чем программное обеспечение можно будет развернуть для пользователя, необходимо связать его с компьютером. Пользователя можно связать с несколькими компьютерами, однако каждый компьютер связывается только с одним пользователем. Пользователи автоматически связываются с компьютерами, которые они регистрируют в Intune, используя корпоративный портал.

### Связывание пользователя с компьютером

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Группы** &gt; **Все устройства** (или другую группу с компьютером, который требуется связать с пользователем).

2.  Выберите компьютер, который требуется связать с пользователем, а затем щелкните **Связать пользователя**.

    В диалоговом окне **Связывание пользователя** выводится список доступных пользователей с их отображаемыми именами, идентификаторами и числом компьютеров, с которым каждый пользователь связан на данный момент. Если пользователь уже связан с выбранным компьютером, имя и идентификатор этого пользователя отображаются в разделе **Текущий пользователь**. Если компьютер не связан ни с одним пользователем, в разделе **Текущий пользователь** отображается **Нет пользователей**.

3.  Выполните одно из следующих действий.

    -   Чтобы оставить компьютер связанным с его текущим пользователем (если таковой существует), нажмите кнопку **Отмена**.

    -   Чтобы удалить связь с текущим пользователем (при его наличии), щелкните **Удалить связь**&gt; **ОК**.

    -   Чтобы связать компьютер с новым пользователем, в списке **Все пользователи** выберите пользователя. Убедитесь в том, что указаны правильные данные пользователя, и нажмите кнопку **ОК**.

> [!TIP]
> Если вы хотите ограничить возможность пользователей связываться с компьютерами, включите параметр **Ограничить возможность пользователей связываться с компьютерами** в политике **Параметры агента Microsoft Intune**.

<!--- ## Request and provide remote assistance to Windows PCs that use the Intune client software

> [!IMPORTANT]
> You might not see the options to configure TeamViewer integration for remote assistance in the Intune admin console. This capability is not currently available to all customers, but will be rolling our more widely soon.


Microsoft Intune can use the [TeamViewer](https://www.teamviewer.com) software to let users of PCs that run the Intune client software get remote assistance help from you. When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.
This functionality replaces the existing Windows Remote Assistance functionality in Intune.


### Before you start

Before you begin to establish and respond to remote assistance requests, you must ensure the following prerequisites are in place:

- You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log into the TeamViewer website.
- Windows PCs that you want to administer must be [managed by the Windows PC client](manage-windows-pcs-with-microsoft-intune.md)
- All Windows PC operating systems supported by Intune can be administered.

### Configure the TeamViewer Connector

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.
2. In the **Admin** workspace, choose **TeamViewer**.
3. On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.
4. In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms. If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.
5. After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.
6. On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.
7. In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.


### Open a remote assistance request (end user)

1. On a client Windows PC, open the **Microsoft Intune Center**.
2. Under **Remote Assistance**, choose **Request Remote Assistance**.
3. After you approve the request (see below), TeamViewer opens on the client. The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.
4. The user sees a message asking if you can control their PC. They must accept this message to continue.
5. During the remote assistance session, the user sees a window that shows them you are connected. If they close this window, the remote session ends.

### Respond to a remote assistance request

1. When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**. For example:
> ![Screenshot of a remote assistance request](./media/team-viewer.png)

<br>If a request goes unanswered for more than 4 hours, it is removed.
2. To accept the request, choose **Approve request and launch Remote Assistance**.
3. In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**. If it's not already installed, TeamViewer will install any necessary apps on your computer.
4. TeamViewer then notifies the end user that you want to take control of their PC. After the user has accepted the request, the TeamViewer windows opens, and you can control the PC.

While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC. For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.

### Close the remote assistance session

From the **Actions** menu of the **TeamViewer** window, choose **End Session**.--->



<!--HONumber=Jul16_HO4-->


