---
title: "Параметры политики Windows 10 | Документы Майкрософт"
description: "Здесь приведены параметры политики, с помощью которых можно настроить стандартные и пользовательские параметры для зарегистрированных устройств на базе ОС Windows 10 Desktop и Windows 10 Mobile."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dd81102eb768ab8ad5f9ee1d2f122f15a8e17b89
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Параметры политики Intune для устройств на базе Windows 10 в Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Сведения в этом разделе помогут вам разобраться в параметрах политик Intune, которые можно использовать для управления устройствами на базе ОС Windows 10. Ознакомьтесь с этим разделом, а также обратитесь к процедурам, описанным в разделе [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Можно выбрать один из двух типов политик:

- **Настраиваемая политика** — используйте **настраиваемую политику** Microsoft Intune для Windows 10 и Windows 10 Mobile, чтобы развернуть параметры OMA-URI (универсальный код ресурса Open Mobile Alliance), которые могут применяться для управления функциями на устройствах. В ОС Windows 10 становятся доступными многие параметры CSP, например [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) (Поставщик службы конфигурации (CSP) политик).
- **Общая политика конфигурации** — используйте этот тип политики, если хотите выбрать параметры из встроенного списка, поставляемого вместе с Microsoft Intune.

## <a name="custom-policy-settings"></a>Параметры настраиваемой политики

Укажите следующие параметры в настраиваемой политике.

### <a name="general-settings"></a>Общие параметры

Введите имя и при необходимости описание политики для идентификации ее в консоли Intune.

### <a name="oma-uri-settings"></a>Параметры OMA-URI

Для каждого добавляемого параметра OMA-URI введите указанные ниже сведения. Сведения о параметрах, которые можно использовать, см. в [справочнике по настройкам URI для Windows 10](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) в этом разделе.

- **Имя параметра** — введите уникальное название параметра OMA-URI, чтобы его было проще найти в списке параметров.
- **Описание параметра** — введите необязательное описание параметра.
- **Тип данных** — выберите один из следующих типов данных:
    - **Строка**
    - **Строка (XML)**
    - **Дата и время**
    - **Целое число**
    - **Число с плавающей запятой**
    - **Логическое значение**
- **OMA-URI (с учетом регистра)** — задайте OMA-URI, для которого необходимо указать параметр.
- **Значение** — укажите значение, которое требуется связать с заданным OMA-URI.

### <a name="example"></a>Пример
На следующем снимке экрана параметр **Connectivity/AllowVPNOverCellular** был включен. Это позволяет устройству с Windows 10 открыть VPN-подключение по сети мобильной связи.

> ![Пример настраиваемой политики, содержащей параметры VPN](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Как найти настраиваемые политики

Полный список всех поставщиков служб конфигурации (CSP), поддерживаемых ОС Windows 10, можно найти в [справочнике поставщиков служб конфигурации](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) в библиотеке документации Windows.

Не все параметры совместимы со всеми версиями ОС Windows 10. Таблица в разделе Windows содержит сведения о том, какие версии поддерживаются для каждого поставщика служб конфигурации (CSP).

Кроме того, Intune поддерживает не все параметры, перечисленные в этом разделе. Чтобы узнать, поддерживает ли Intune необходимый параметр, откройте соответствующий раздел для этого параметра. На странице каждого параметра отображаются сведения о поддерживаемых операциях. Для работы с Intune параметр должен поддерживать операции **добавления** или **замены**.

## <a name="general-configuration-policy-settings"></a>Параметры общей политики конфигурации

Используйте **общую политику конфигурации** Microsoft Intune для Windows 10, чтобы настроить встроенные параметры для зарегистрированных устройств на базе Windows 10 Mobile и Windows 10 Desktop.

### <a name="password"></a>Пароль

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Требовать пароль для разблокировки устройств**|-|
|**Требуемый тип пароля**|Указывает, должен ли пароль содержать буквы и цифры или только цифры|
|**Требуемый тип пароля** - **Минимальное число наборов символов**| Указывает, сколько наборов символов (строчных и прописных букв, цифр и символов) должно быть в пароле.|
|**Минимальная длина пароля**|Применяется только для Windows 10 Mobile|
|**Число разрешенных неудачных попыток входа перед очисткой устройства**.|Для устройств под управлением Windows 10: если для устройства включен BitLocker, после указанного числа неудачных попыток входа оно переключается в режим восстановления BitLocker. Если BitLocker для устройства не включен, этот параметр не применяется.<br>Для устройств под управлением Windows 10 Mobile: после указанного числа неудачных попыток входа устройство будет очищено.|
|**Период бездействия до отключения экрана (в минутах)**|Указывает период бездействия устройства, по истечении которого экран блокируется.|
|**Срок действия пароля (дней)**|Указывает время, по истечении которого требуется сменить пароль устройства.|
|**Запоминать историю паролей**|Указывает, следует ли запретить пользователю применять использованные ранее пароли.|
|**Вести журнал паролей** - **Запретить использование предыдущих паролей**|Указывает число предыдущих паролей устройства, которые нельзя использовать.|
|**Требовать пароль при возвращении устройства из состояния простоя**|Указывает, что пользователь должен ввести пароль для разблокировки устройства (только Windows 10 Mobile).|

### <a name="encryption"></a>Encryption

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Требовать шифрование на мобильном устройстве**|Включает шифрование на целевых устройствах.<br>(только для Windows 10 Mobile)|

### <a name="system"></a>System (система)

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить снимок экрана**|Позволяет пользователю сохранять содержимое экрана устройства в виде изображения (только Windows 10 Mobile).|
|**Разрешить регистрацию вручную**|Позволяет пользователю вручную удалить рабочую учетную запись с устройства.|
|**Разрешить установку корневого сертификата вручную**|Применяется к Windows 10 Mobile|
|**Разрешить отправку диагностических данных и данных об использовании в Майкрософт**|Возможные значения:<br><br>**Нет** — данные не передаются в корпорацию Майкрософт.<br>**Основные** — в Майкрософт отправляются ограниченные сведения.<br>**Расширенный** — в Майкрософт отправляются расширенные диагностические сведения.<br>**Полный (рекомендуется)** — отправляются те же данные, что и в режиме **Расширенный**, а также дополнительные сведения о состоянии устройства.|


### <a name="account-and-synchronization"></a>Учетная запись и синхронизация

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить использование учетной записи Майкрософт**|Позволяет пользователю сопоставить учетную запись Майкрософт с устройством.|
|**Разрешить добавление учетных записей сторонних производителей вручную**|Позволяет пользователю добавлять на устройство учетные записи электронной почты, которые не сопоставлены с учетной записью Майкрософт.|
|**Разрешить синхронизацию настроек для учетных записей Майкрософт**|Разрешает синхронизацию параметров устройств и приложений, связанных с учетной записью Майкрософт, между устройствами.|

### <a name="microsoft-edge"></a>Microsoft Edge

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить веб-браузер**|Разрешает использовать браузер Edge на устройстве.<br>(только для Windows 10 Mobile)|
|**Разрешить варианты поиска в адресной строке**|Позволяет поисковой системе предлагать сайты при вводе фраз для поиска.|
|**Разрешить отправку трафика интрасети в Internet Explorer**|Позволяет пользователям открывать сайты интрасети в Internet Explorer.<br>(только для Windows 10 Desktop)|
|**Разрешить Do Not Track**|Настраивает в браузере Edge отправку заголовков Do Not Track на посещаемые веб-сайты.|
|**Включить SmartScreen**||
|**Разрешить выполнение активных сценариев**|Разрешает выполнять скрипты, такие как JavaScript, в браузере Edge.|
|**Разрешить всплывающие окна**|Применяется только для Windows 10 Desktop.|
|**Разрешить файлы cookie**||
|**Разрешить автозаполнение**|Разрешает пользователям изменять параметры автозаполнения в браузере.<br>(только для Windows 10 Desktop)|
|**Разрешить диспетчер паролей**|Включает или отключает функцию диспетчера паролей в Edge.|
|**Расположение списка сайтов режима предприятия**|Указывает, где можно найти список веб-сайтов, которые будут открываться в режиме предприятия. Пользователи не могут изменять этот список.<br>(только для Windows 10 Desktop)|

### <a name="apps"></a>Приложения

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить Магазин приложений**|Применяется только для Windows 10 Mobile|



### <a name="cellular"></a>Сотовая сеть

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить передачу данных в роуминге**|Разрешает роуминг между сетями при доступе к данным.|
|**Разрешить VPN через сеть мобильной связи**|Определяет, может ли устройство получить доступ к VPN-подключениям при подключении к сети мобильной связи.|
|**Разрешить передачу данных VPN в роуминге через сеть мобильной связи**|Определяет, может ли устройство получить доступ к VPN-подключениям при роуминге в сети мобильной связи.|

### <a name="hardware"></a>Оборудование

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|
|**Разрешить камеру**|-|
|**Разрешить съемные носители**|Указывает, можно ли использовать на устройстве внешние запоминающие устройства, например SD-карты.|
|**Разрешить Wi-Fi**|Применяется только для Windows 10 Mobile|
|**Разрешить общий Интернет**|Разрешает использовать на устройстве общий доступ к интернет-подключению.|
|**Разрешить настройку Wi-Fi вручную**|Указывает, может ли пользователь настраивать подключения Wi-Fi либо использовать только подключения на базе профиля Wi-Fi.<br>(только для Windows 10 Mobile)|
|**Разрешить автоматическое подключение к свободным хот-спотам Wi-Fi**|Позволяет устройству автоматически подключаться к хот-спотам Wi-Fi и автоматически принимать любые условия, действующие для такого соединения.|
|**Разрешить геолокацию**|Указывает, может ли устройство использовать сведения о службах определения местоположения.|
|**Разрешить NFC**|Разрешает устройству использовать функции радиочастотной связи ближнего действия (NFC).|
|**Разрешить Bluetooth**|-|
|**Разрешить режим обнаружения Bluetooth**|Разрешает обнаружение устройства другими устройствами, поддерживающими Bluetooth.|
|**Разрешить рекламу по Bluetooth**|Позволяет устройствам получать объявления через Bluetooth.|
|**Разрешить сброс по телефону**|Управляет возможностью сброса пользователем параметров устройства до заводских.|
|**Разрешить USB-подключение**|Указывает, разрешен ли доступ устройства к внешним запоминающим устройствам через USB-подключение.|
|**Разрешить режим защиты от кражи**|Укажите, включен ли режим защиты от кражи Windows.|

### <a name="features"></a>Функции

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить копирование и вставку**|Применяется только для Windows 10 Mobile|
|**Разрешить запись голоса**|Применяется только для Windows 10 Mobile|
|**Разрешить использование Кортаны**|Включает или отключает голосовой помощник — Кортану|
|**Разрешить уведомления центра уведомлений**|Включает или отключает отображение уведомлений из центра уведомлений на экране блокировки устройства<br>(только для Windows 10 Mobile)|

### <a name="windows-defender"></a>Защитник Windows

Все параметры относятся только к Windows 10 Desktop.

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|----------------------|---------------------|
|**Разрешить мониторинг в режиме реального времени**|Позволяет в режиме реального времени проверять наличие вредоносных программ, шпионского ПО и другого нежелательного программного обеспечения.|
|**Разрешить мониторинг поведения**|Позволяет Защитнику отслеживать наличие определенных типичных подозрительных действий на устройствах.|
|**Включить систему проверки сети**|Система проверки сети (NIS) помогает защитить устройства от сетевых эксплойтов, используя сигнатуры известных уязвимостей из Microsoft Endpoint Protection Center для обнаружения и блокировки вредоносного трафика.|
|**Проверять все скачиваемые файлы**|Указывает, проверяет ли Защитник все файлы, загруженные из Интернета.|
|**Разрешить сканирование сценариев**|Позволяет Защитнику проверять скрипты, используемые в Internet Explorer.|
|**Мониторинг действий файлов и программ**|Разрешает Защитнику отслеживать действия, выполняемые с файлами и программами на устройствах.|
|**Дни отслеживания устраненной вредоносной программы**|Позволяет Защитнику продолжить отслеживание устраненной вредоносной программы определенное число дней, чтобы можно было вручную проверить затронутые ранее устройства. Если задать число дней равным **0**, вредоносная программа остается в папке карантина и не удаляется автоматически. |
|**Разрешить доступ к пользовательскому интерфейсу клиента**|Определяет, скрыт ли пользовательский интерфейс Защитника Windows от пользователей.<br>Изменение этого параметра вступает в силу при следующей перезагрузке компьютера.|
|**Запланировать ежедневную быструю проверку**|Позволяет запланировать ежедневную быструю проверку в заданное время.|
|**Запланировать проверку системы**|Позволяет запланировать регулярную полную или быструю проверку системы, указав день и время.|
|**Ограничить загрузку ЦП при проверке**|Позволяет ограничить объем ресурсов ЦП, который может использовать функция проверки (значение от **1** до **100**).|
|**Проверять архивные файлы**|Позволяет Защитнику проверять архивные файлы, такие как ZIP- или CAB-файлы.|
|**Проверять сообщения электронной почты**|Позволяет Защитнику проверять электронные письма при их поступлении на устройство.|
|**Проверять съемные носители**|Позволяет Защитнику проверять съемные носители, например USB-накопители.|
|**Проверять подключенные сетевые диски**|Позволяет Защитнику проверять файлы на сопоставленных сетевых дисках.<br>Если файлы на диске доступны только для чтения, Защитник не сможет удалять обнаруженные в них вредоносные программы.|
|**Проверять файлы, открытые из общих сетевых папок**|Позволяет Защитнику проверять файлы на общих сетевых дисках (например, доступных по UNC-пути).<br>Если файлы на диске доступны только для чтения, Защитник не сможет удалить найденные на нем вредоносные программы.|
|**Интервал обновления сигнатур**|Указывает периодичность, с которой Защитник будет проверять наличие новых файлов сигнатур.|
|**Разрешить защиту в облаке**|Разрешает или запрещает Microsoft Active Protection Service получать от управляемых устройств сведения об активности вредоносных программ. Они используются для улучшения качества службы в будущем.|
|**Запрашивать у пользователей примеры отправляемых файлов**|Указывает, следует ли отправлять файлы, для определения вредоносности которых может потребоваться дополнительный анализ, в корпорацию Майкрософт автоматически.|
|**Обнаружение потенциально нежелательных приложений**|Защищает зарегистрированные настольные устройства Windows от запуска программного обеспечения, которое классифицируется Защитником Windows как потенциально нежелательное. Можно настроить защиту от запуска этих приложений или использовать режим аудита для оповещения об установке потенциально нежелательного приложения.|
|**Файлы и папки, которые следует пропускать при выполнении проверки или использовании защиты в режиме реального времени**|Добавляет один файл или папку либо несколько, такие как **C:\Path** или **%ProgramFiles%\Path\имя_файла.exe**, в список исключений. Эти файлы и папки не учитываются при проверках в режиме реального времени или по расписанию.|
|**Расширения файлов, которые следует пропускать при проверке или использовании защиты в режиме реального времени**|Добавляет одно или несколько расширений файла, например **jpg** или **txt**, в список исключений. Все файлы с такими расширениями не учитываются при проверках в режиме реального времени или по расписанию.|
|**Процессы, которые следует пропускать при проверке или использовании защиты в режиме реального времени**|Добавляет один процесс или несколько типа **.exe**, **.com** или **.scr** в список исключений. Эти процессы не учитываются при проверках в режиме реального времени или по расписанию.|


### <a name="updates"></a>Updates

|Имя параметра|Дополнительные сведения (если требуются)|
|----------------|---------------|
|**Разрешить автоматические обновления**|Разрешает автоматические обновления. Настройте один из следующих параметров, чтобы контролировать поведение при обновлении.<br />**Уведомление о загрузке**<br />**Автоматическая установка во время обслуживания**<br />**Автоматическая установка и перезагрузка во время обслуживания**<br />**Автоматическая установка и перезагрузка в запланированное время**. Примечание. При выборе этого параметра можно также настроить следующие параметры: **Не отображать уведомления для конечного пользователя** и **Указать день установки запланированных обновлений**.<br>(только для Windows 10 Desktop)|
|**Разрешить функции предварительной версии**|Позволяет корпорации Майкрософт развертывать на устройствах Windows 10 предварительные версии настроек и компонентов. Вы можете разрешить установку только настроек или всех настроек и компонентов, находящихся на этапе предварительной версии.|

### <a name="see-also"></a>См. также
[Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
