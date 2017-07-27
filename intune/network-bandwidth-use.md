---
title: "Использование пропускной способности сети Intune"
description: "использование пропускной способности сети Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 531112301d0c3827ec7eb3ab4087218caa331b90
ms.sourcegitcommit: 2b7d644c7a4f85315e11a7d0c5885cc66975c2ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2017
---
# <a name="intune-network-bandwidth-use"></a>Использование пропускной способности сети Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Это руководство поможет понять администраторам Intune требования к сети для службы Intune. Эти сведения содержат требования к пропускной способности, IP-адрес и параметры порта, необходимые для настройки прокси-сервера.

## <a name="average-network-traffic"></a>Средний объем сетевого трафика
В этой таблице указан примерный объем и частота типичного содержимого, передаваемого по сети, для каждого клиента.

> [!NOTE]
> Чтобы устройства получали обновления и содержимое из Intune, они должны периодически подключаться к Интернету. Необходимое для получения обновлений или содержимого время может быть разным, но устройства должны каждый день подключаться к Интернету как минимум на час без прерывания соединения.

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
Прокси-сервер может кэшировать получаемое из Интернета содержимое, чтобы сократить дублирование при скачивании и уменьшить нагрузку на пропускную способность сети.

Сервер, к которому поступают запросы на содержимое от клиентов, может получать это содержимое и кэшировать ответы и загрузки из Интернета. Кэшированные данные используются для ответа на последующие запросы клиентов.

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
Клиенты Intune могут использовать функцию BranchCache для сокращения трафика глобальной сети. BranchCache поддерживают следующие операционные системы.

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Для использования BranchCache на клиентском компьютере должна быть включена функция BranchCache и выполнена настройка для работы в **режиме распределенного кэша**.

По умолчанию BranchCache и режим распределенного кэша включаются на компьютерах с установленным клиентом Intune. Но если групповая политика отключила BranchCache, Intune не переопределяет эту политику и BranchCache остается отключенным.

Если вы используете BranchCache, для управления групповой политикой и политикой брандмауэра Intune обратитесь к другим администраторам в организации. Они не должны развертывать политику, которая отключает BranchCache или исключения брандмауэра. Дополнительные сведения о BranchCache см. в статье [Обзор BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Требования к сетевому подключению

Разрешите обмен данными по сети между устройствами, которыми вы управляете, и веб-сайтами, необходимыми для облачных служб.

Intune не использует локальную инфраструктуру, например серверы, на которых выполняется программное обеспечение Intune. Однако существуют варианты использования локальной инфраструктуры, включая средства Exchange и инструменты синхронизации Active Directory.

Для управления компьютерами, защищенными брандмауэрами и прокси-серверами, нужно включить возможность обмена данными с Intune.

-   Прокси-сервер должен поддерживать протоколы **HTTP (80)** и **HTTPS (443)**, так как клиенты Intune используют оба этих протокола.
-   Для некоторых задач, таких как скачивание программного обеспечения и обновлений, Intune требуется доступ к manage.microsoft.com через прокси-сервер без проверки подлинности.

Можно изменить параметры прокси-сервера на отдельных клиентских компьютерах или воспользоваться параметрами групповой политики, чтобы изменить параметры для всех клиентских компьютеров, которые размещены за указанным прокси-сервером.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Управляемые устройства должны иметь конфигурации с выбранным параметром **Все пользователи**, чтобы все пользователи могли получать доступ к службам через брандмауэры.

В приведенной ниже таблице перечислены порты и службы, к которым обращается клиент Intune.

|**Домены**|**IP-адрес**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
