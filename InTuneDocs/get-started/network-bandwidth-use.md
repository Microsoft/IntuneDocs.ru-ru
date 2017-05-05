---
title: "Использование пропускной способности сети Intune | Документация Майкрософт"
description: "использование пропускной способности сети Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 5211d2222e5e8ef9328f60ed13f0146925194c5f
ms.lasthandoff: 04/26/2017


---

# <a name="intune-network-bandwidth-use"></a>Использование пропускной способности сети Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Это руководство поможет понять администраторам Intune требования к сети для службы Intune. Эти сведения содержат требования к пропускной способности, IP-адрес и параметры порта, необходимые для настройки прокси-сервера.

## <a name="average-network-traffic"></a>Средний объем сетевого трафика
В этой таблице указан примерный объем и частота типичного содержимого, передаваемого по сети, для каждого клиента.

> [!NOTE]
> Чтобы компьютеры и мобильные устройства получали необходимые обновления и содержимое из службы Intune, их нужно периодически подключать к Интернету. Время, затраченное на получение обновлений или контента, будет разным. Однако, как правило, они должны оставаться непрерывно подключенными к Интернету по крайней мере 1 час каждый день.

|Тип контента|Примерный размер|Частота и подробные сведения|
|----------------|--------------------|-------------------------|
|Установка клиента Intune<br /><br />**Указанные ниже требования необходимо выполнить помимо установки клиента Intune**|125 МБ|**Один раз**<br /><br />Объем загружаемых данных клиента различается в зависимости от операционной системы клиентского компьютера.|
|Пакет регистрации клиента|15 МБ|**Один раз**<br /><br />Дополнительные загрузки возможны при наличии обновлений для этого типа содержимого.|
|Агент Endpoint Protection|65 МБ|**Один раз**<br /><br />Дополнительные загрузки возможны при наличии обновлений для этого типа содержимого.|
|Агент Operations Manager|11 МБ|**Один раз**<br /><br />Дополнительные загрузки возможны при наличии обновлений для этого типа содержимого.|
|Агент политики|3 МБ|**Один раз**<br /><br />Дополнительные загрузки возможны при наличии обновлений для этого типа содержимого.|
|Удаленная помощь через агента Microsoft Easy Assist|6 МБ|**Один раз**<br /><br />Дополнительные загрузки возможны при наличии обновлений для этого типа содержимого.|
|Ежедневные операции клиента|6 МБ|**Ежедневно**<br /><br />Клиент Intune регулярно взаимодействует со службой Intune для проверки наличия обновлений и политик, а также для передачи данных о статусе клиента в службу.|
|Обновления определений вредоносных программ Endpoint Protection|Различается<br /><br />Как правило, от 40 КБ до 2 МБ|**Ежедневно**<br /><br />До трех раз в день.|
|Обновление модуля Endpoint Protection|5 МБ|**Ежемесячно**|
|Обновления программного обеспечения|Различается<br /><br />Объем зависит от развертываемых обновлений.|**Ежемесячно**<br /><br />Как правило, обновления программного обеспечения выпускаются каждый второй вторник месяца.<br /><br />Недавно зарегистрированные или развернутые компьютеры могут использовать больше пропускной способности при загрузке полного набора ранее выпущенных обновлений.|
|Пакеты обновления|Различается<br /><br />Объем зависит от каждого развертываемого пакета обновления.|**Различается**<br /><br />Зависит от времени развертывания пакетов обновления.|
|Распространение программного обеспечения|Различается<br /><br />Объем зависит от развертываемого программного обеспечения.|**Различается**<br /><br />Зависит от времени развертывания программного обеспечения.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Сокращение используемой пропускной способности сети
Сократить нагрузку на полосу пропускания сети для клиентов Intune можно одним из следующих способов.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Использование прокси-сервера для кэширования запросов содержимого
Чтобы сократить дублирование загрузок и использование полосы пропускания сети клиентами, запрашивающими содержимое из Интернета, можно использовать прокси-сервер, который может кэшировать содержимое.

Прокси-сервер кэширования получает запросы содержимого с клиентских компьютеров в сети организации, получает это содержимое из Интернета, а затем может кэшировать как HTTP-ответы, так и двоичные загрузки. Сервер использует кэшированные данные для ответа на последующие запросы от клиентских компьютеров Intune.

Ниже приведены типичные параметры для использования при настройке прокси-сервера, кэширующего содержимое для клиентов Intune.

|Параметр|Рекомендованное значение|Подробные сведения|
|-----------|---------------------|-----------|
|Размер кэша|От 5 до 30 ГБ|Значение зависит от числа клиентских компьютеров в сети и используемых конфигураций. Чтобы предотвратить слишком быстрое удаление файлов, скорректируйте размер кэша в соответствии с вашей средой.|
|Размер отдельного файла кэша|950 МБ|Этот параметр может быть доступен не на всех прокси-серверах кэширования.|
|Типы объектов, подлежащих кэшированию|HTTP<br /><br />HTTPS<br /><br />BITS|Пакеты Intune представляют собой CAB-файлы, извлеченные при скачивании фоновой интеллектуальной службы передачи (BITS) по HTTP.|
Дополнительные сведения об использовании прокси-сервера для кэширования содержимого см. в документации по вашему решению прокси-сервера.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Использование фоновой интеллектуальной службы передачи данных (BITS) на компьютерах
Intune поддерживает использование фоновой интеллектуальной службы передачи (BITS) на компьютерах Windows, чтобы сократить нагрузку на полосу пропускания сети, используемую компьютером в заданное время. Политику для службы BITS можно настроить на странице **Пропускная способность сети** политики агента Intune.

Дополнительные сведения о службе BITS и компьютерах Windows см. в статье [Background Intelligent Transfer Service (Служба BITS)](http://technet.microsoft.com/library/bb968799.aspx) библиотеки TechNet.

### <a name="use-branchcache-on-computers"></a>Использование BranchCache на компьютерах
Клиенты Intune могут использовать функцию BranchCache для сокращения трафика глобальной сети. Следующие операционные системы, поддерживаемые в качестве клиентов, также поддерживают BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Для использования BranchCache на клиентском компьютере должна быть включена функция BranchCache и выполнена настройка для работы в **режиме распределенного кэша**.

По умолчанию BranchCache и режим распределенного кэша включаются на компьютере во время установки клиента Intune. Однако если на клиенте уже есть групповая политика, отключающая BranchCache, Intune не переопределяет эту политику и функция BranchCache остается отключенной на этом компьютере.

При использовании BranchCache необходимо связаться с другими корпоративными администраторами, управляющими групповой политикой и политикой брандмауэра Intune, чтобы убедиться, что они не развертывают политику, отключающую BranchCache или исключения брандмауэра. Дополнительные сведения о BranchCache см. в статье [Обзор BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Требования к сетевому подключению

Сетевое подключение необходимо включить между управляемыми устройствами, устройствами для управления подпиской Intune и веб-сайтами, которые требуются для облачных служб.

Intune не использует локальную инфраструктуру, например серверы, на которых выполняется программное обеспечение Intune. Однако существуют варианты использования локальной инфраструктуры, включая средства Exchange и инструменты синхронизации Active Directory.

Для управления компьютерами, находящимися за брандмауэрами и прокси-серверами, необходимо настроить эти брандмауэры и прокси-серверы для разрешения подключения к Intune.

### <a name="requirements-for-proxy-servers"></a>Требования к прокси-серверам
Для управления компьютерами, находящимися за прокси-сервером, необходимо учесть следующие моменты.

-   Прокси-сервер должен поддерживать протоколы **HTTP** и **HTTPS**, так как клиенты Intune используют оба этих протокола.
-   Intune поддерживает не прошедшие проверку подлинности прокси-серверы.

Можно изменить параметры прокси-сервера на отдельных клиентских компьютерах или воспользоваться параметрами групповой политики, чтобы изменить параметры для всех клиентских компьютеров, которые размещены за указанным прокси-сервером.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Требования к брандмауэрам, портам и доменам
Управляемые устройства должны иметь конфигурации с выбранным параметром **Все пользователи**, чтобы все пользователи могли получать доступ к службам через брандмауэры.

В следующей таблице приводится перечень доменов и служб, к которым обращается клиент Intune.

|**Домен**|**Порты**|**IP-адрес**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 и 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 и 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 и 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 и 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 и 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 и 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 и 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 и 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 и 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 и 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 и 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 и 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 и 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 и 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 и 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 и 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 и 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 и 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 и 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 и 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 и 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 и 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 и 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 и 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 и 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 и 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 и 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 и 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 и 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 и 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 и 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 и 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 и 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 и 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 и 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 и 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 и 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 и 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 и 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 и 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 и 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 и 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 и 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 и 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 и 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 и 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 и 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 и 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 и 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 и 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 и 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 и 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 и 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 и 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 и 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 и 443|111.221.76.60
|msua01.manage.microsoft.com|80 и 443|157.55.50.182
|msua02.manage.microsoft.com|80 и 443|134.170.49.121
|msua04.manage.microsoft.com|80 и 443|134.170.49.126
|msua05.manage.microsoft.com|80 и 443|157.55.240.190
|msub01.manage.microsoft.com|80 и 443|94.245.121.50
|msub02.manage.microsoft.com|80 и 443|94.245.121.58
|msub03.manage.microsoft.com|80 и 443|94.245.121.56
|msub05.manage.microsoft.com|80 и 443|157.56.113.123
|msuc01.manage.microsoft.com|80 и 443|104.44.84.187
|msuc02.manage.microsoft.com|80 и 443|104.44.84.188
|msuc03.manage.microsoft.com|80 и 443|104.44.84.189
|msuc05.manage.microsoft.com|80 и 443|111.221.76.60
|msua06.manage.microsoft.com|80 и 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 и 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 и 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 и 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 и 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 и 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 и 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 и 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 и 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 и 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 и 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 и 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 и 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 и 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 и 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 и 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 и 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 и 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 и 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 и 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 и 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 и 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 и 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 и 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 и 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 и 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 и 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 и 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 и 443|134.170.49.114
|ssu2.manage.microsoft.com|80 и 443|157.55.99.181
|status.manage.microsoft.com|80 и 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 и 443|93.184.215.200
|*.microsoftonline-p.com|80 и 443||
|has.spserv.microsoft.com<br>Требуется для службы аттестации работоспособности устройств|443||
|*.microsoftonline-p.net|80 и 443||
|*.portal.office.com|80 и 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 и 443||
|c1.microsoft.com|80 и 443||
|blob.core.windows.net|80 и 443||
|ajax.aspnetcdn.com|80 и 443||
|*.googleapis.com<br>Этот домен необходим для поддержки JQuery при использовании веб-сайта корпоративного портала.|80 и 443||
|wustat.microsoft.com|80 и 443||
|Службы Центра обновления Майкрософт|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 и 443|
|Запросы на просмотр DNS|manage.microsoft.com.nsatc.net|80|
|Взаимодействие устройства Samsung KNOX Standard через брандмауэр|Чтобы разрешить устройствам Samsung KNOX Standard взаимодействовать с серверами KNOX Standard через брандмауэр, следуйте инструкциям на странице с часто задаваемыми вопросами о Samsung KNOX Standard.||
|Передача данных условным доступом|443|204.79.197.200|
|Документация, справка и поддержка</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||


>[!div class="step-by-step"]

>[&larr; **Предварительные требования**](what-to-know-before-you-start-microsoft-intune.md)     [**Подписка** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  

