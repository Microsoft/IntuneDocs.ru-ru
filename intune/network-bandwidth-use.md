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
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 030aa380a1491eb3be4fd8f480b0ddc9a7860448
ms.contentlocale: ru-ru
ms.lasthandoff: 06/08/2017


---

# <a name="intune-network-bandwidth-use"></a>Использование пропускной способности сети Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

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

Для управления компьютерами, находящимися за брандмауэрами и прокси-серверами, необходимо настроить эти брандмауэры и прокси-серверы для разрешения подключения к Intune. Для управления компьютерами, находящимися за прокси-сервером, необходимо учесть следующие моменты.

-   Прокси-сервер должен поддерживать протоколы **HTTP (80)** и **HTTPS (443)**, так как клиенты Intune используют оба этих протокола.
-   Intune поддерживает не прошедшие проверку подлинности прокси-серверы.

Можно изменить параметры прокси-сервера на отдельных клиентских компьютерах или воспользоваться параметрами групповой политики, чтобы изменить параметры для всех клиентских компьютеров, которые размещены за указанным прокси-сервером.

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

