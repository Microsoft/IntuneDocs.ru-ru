---
title: Требования к сети и сведения о пропускной способности для Microsoft Intune
titleSuffix: ''
description: Требования к конфигурации сети и сведения о ее пропускной способности для Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2019
ms.locfileid: "59570797"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Требования к конфигурации сети Intune и ее пропускная способность

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

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


|          Параметр           |           Рекомендованное значение           |                                                                                                  Подробные сведения                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Размер кэша         |             От 5 до 30 ГБ             | Значение зависит от числа клиентских компьютеров в сети и используемых конфигураций. Чтобы предотвратить слишком быстрое удаление файлов, скорректируйте размер кэша в соответствии с вашей средой. |
| Размер отдельного файла кэша |                950 МБ                 |                                                                     Этот параметр может быть доступен не на всех прокси-серверах кэширования.                                                                     |
|   Типы объектов, подлежащих кэшированию    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Пакеты Intune представляют собой CAB-файлы, извлеченные при скачивании фоновой интеллектуальной службы передачи (BITS) по HTTP.                                               |
> [!NOTE]
> Если прокси-сервер используется для кэширования запросов содержимого, обмен данными шифруется только между клиентом и прокси-сервером и при передаче данных с прокси-сервера в Intune. Подключение от клиента к Intune не будет полностью зашифровано.

Дополнительные сведения об использовании прокси-сервера для кэширования содержимого см. в документации по вашему решению прокси-сервера.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Использование фоновой интеллектуальной службы передачи данных (BITS) на компьютерах
В настроенное время на компьютере Windows можно использовать BITS для снижения пропускной способности сети. Политику BITS можно настроить на странице **Пропускная способность сети** политики агента Intune.

> [!NOTE]
> Для управления MDM в Windows только интерфейс управления ОС для типа приложения MobileMSI выполняет скачивание с помощью BITS. AppX/MsiX использует собственный стек скачивания, отличный от BITS, а приложения Win32 через агент Intune используют оптимизацию доставки вместо BITS.

Дополнительные сведения о службе BITS и компьютерах Windows см. в статье [Background Intelligent Transfer Service (Служба BITS)](http://technet.microsoft.com/library/bb968799.aspx) библиотеки TechNet.

### <a name="use-branchcache-on-computers"></a>Использование BranchCache на компьютерах
Клиенты Intune могут использовать функцию BranchCache для сокращения трафика глобальной сети. BranchCache поддерживают следующие операционные системы.

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Для использования BranchCache на клиентском компьютере должна быть включена функция BranchCache и выполнена настройка для работы в **режиме распределенного кэша**.

После того как на компьютерах установлен клиент Intune, BranchCache и режим распределенного кэша включаются по умолчанию. Но если групповая политика отключила BranchCache, Intune не переопределяет эту политику и BranchCache остается отключенным.

Если вы используете BranchCache, для управления групповой политикой и политикой брандмауэра Intune обратитесь к другим администраторам в организации. Они не должны развертывать политику, которая отключает BranchCache или исключения брандмауэра. Дополнительные сведения о BranchCache см. в статье [Обзор BranchCache](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Требования к сетевому подключению

Разрешите обмен данными по сети между устройствами, которыми вы управляете, и конечными точками, необходимыми для облачных служб.

Как облачная служба, Intune не требует локальной инфраструктуры, такой как серверы или шлюзы.

Для управления устройствами, защищенными брандмауэрами и прокси-серверами, нужно включить возможность обмена данными с Intune.

- Прокси-сервер должен поддерживать протоколы **HTTP (80)** и **HTTPS (443)**, так как клиенты Intune используют оба этих протокола.
- Для некоторых задач (например, скачивание программного обеспечения и обновлений) Intune требуется доступ к manage.microsoft.com через прокси-сервер без проверки подлинности.

Параметры прокси-сервера можно изменить на отдельных клиентских компьютерах. Кроме того, с помощью параметров групповой политики можно изменить параметры для всех клиентских компьютеров, защищенных указанным прокси-сервером.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Управляемые устройства должны иметь конфигурации с выбранным параметром **Все пользователи**, чтобы все пользователи могли получать доступ к службам через брандмауэры.

В приведенной ниже таблице перечислены порты и службы, к которым обращается клиент Intune.

|**Домены**|**IP-адрес**|
|---------------------|-----------|
|login.microsoftonline.com | Дополнительные сведения о [URL-адресах и диапазонах IP-адресов Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Сведений о сети на устройстве Apple


|Назначение|Имя узла (IP-адрес/подсеть)|Протокол|Port|
|-----|--------|------|-------|
|Получение push-уведомлений из службы Intune через Cлужбу push-уведомлений Apple (APNs). Документацию компании Apple см. [здесь](https://support.apple.com/en-us/HT203609).|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Отправление отзывов в службу Intune через Cлужбу push-уведомлений Apple (APNs)|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Извлечение и отображение содержимого с серверов Apple|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Обмен данными с серверами APNs|#-courier.push.apple.com (17.0.0.0/8)<br># — это случайное число от 0 до 50.|    TCP     |  5223 и 443  |
|Различные функциональные возможности, включая доступ к Интернету, магазину iTunes, магазину приложений macOS, iCloud, службе сообщений и т. д. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 или 443   |

Дополнительные сведения см. в статьях [Порты TCP и UDP, используемые программными продуктами Apple](https://support.apple.com/en-us/HT202944), [Фоновые процессы iTunes и подключения к серверам macOS, iOS и iTunes](https://support.apple.com/en-us/HT201999) и [Если клиенты macOS и iOS не получают push-уведомления от Apple](https://support.apple.com/en-us/HT203609) на сайте Apple.
