---
title: Параметры оптимизации доставки в Windows 10 для Intune | Документация Майкрософт
description: Параметры оптимизации доставки для устройств Windows 10, которые можно развернуть с помощью Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 58c199a908198295bf3e52d0a5fcf01d3ebf5a2d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048382"
---
# <a name="delivery-optimization-settings-for-intune"></a>Параметры оптимизации доставки для Intune

В этой статье перечислены параметры оптимизации доставки, поддерживаемые Intune для устройств под управлением Windows 10 или более поздней версии.  

Большинству параметров в консоли Intune напрямую сопоставлены параметры оптимизации доставки, которые подробно описаны в документации по Windows; здесь приведены ссылки на соответствующее содержимое.  Параметры, относящиеся к Intune, не содержат ссылки на дополнительное содержимое.  

Приведенные здесь таблицы включают:  

- **Параметры**: параметры, отображаемые в Intune. Параметры, которые являются ссылками, ведут на соответствующую запись в разделе [Настройка доставки оптимизации для обновлений Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) в документации по Windows, где есть дополнительные сведения о параметре.

- **Версия Windows**: минимальная версия Windows 10, которая включает поддержку для этого параметра.  

- **Сведения**: краткое описание того, как Intune реализует параметр, в том числе значение по умолчанию в Intune. Если возможно, приводятся ссылки на записи [поставщика службы конфигурации политики оптимизации доставки](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization).  

Чтобы настроить Intune для использования этих параметров, см. раздел [Доставка обновлений](delivery-optimization-windows.md).  

## <a name="delivery-optimization"></a>Оптимизация доставки  

|Параметр  |Версия Windows  |Подробные сведения  |
|---------|-----------------|---------|
| [Режим скачивания](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode)     | 1511         | Укажите способ скачивания содержимого для этой оптимизации доставки.<br><ul><li>**Не настроено**. Пользователи самостоятельно определяют способы доставки обновлений. Это может быть *Центр обновления Windows или параметры оптимизации доставки*, доступные в операционной системе. </li> <li> **Только HTTP, без пиринга (0)** . Получение обновлений только из Интернета. Этот вариант исключает получение обновлений с других компьютеров в одноранговой (пиринговой) сети. </li> <li> **Сочетание HTTP с пирингом за общим NAT (1)** . Получение обновлений из Интернета и с других компьютеров в локальной сети. </li> <li> **Сочетание HTTP с пирингом в частной группе (2)** . Пиринговое соединение возможно между устройствами, находящимися в одном сайте Active Directory (если он существует) или в одном домене. Если выбран этот параметр, пиринговое соединение возможно с устройствами, IP-адреса которых находятся вне вашего диапазона IP-адресов для NAT. </li> <li> **Сочетание HTTP с интернет-пирингом (3)** . Получение обновлений из Интернета и с других компьютеров в локальной сети. </li> <li> **Режим простого скачивания без пиринга (99)** . Получение обновлений из Интернета непосредственно от владельца обновления, например Майкрософт. Если выбрать этот вариант, облачные службы оптимизации доставки не задействованы. </li> <li> **Режим обхода (100)** . Получение обновлений с помощью фоновой интеллектуальной службы передачи (BITS). Оптимизация доставки не используется. </li></ul> **Значение по умолчанию**: не настроено  <br><br> CSP политики: [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)  <br><br>  |
| [Ограничить выбор однорангового узла](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#select-a-method-to-restrict-peer-selection)          | 1803        | Требуется задать **Режим скачивания** как *Сочетание HTTP с пирингом за общим NAT (1)* или *Сочетание HTTP с пирингом в частной группе (2)* .<br/><br/>Ограничивает выбор однорангового узла определенной группой устройств.<br/><br/>**Значение по умолчанию**: не настроено <br/><br/>CSP политики: [DORestrictPeerSelectionBy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dorestrictpeerselectionby)<br><br>      |
| [Источник идентификатора группы](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#select-the-source-of-group-ids)     | 1803        | Требуется задать **Режим скачивания** как *Сочетание HTTP с пирингом в частной группе (2)* .<br><br>Ограничивает выбор однорангового узла определенной группой устройств по источнику.<br><br>При выборе варианта **Настраиваемый** настройте **Идентификатор группы (как GUID)** . Используйте идентификатор GUID в качестве идентификатора группы, если вам нужно создать одну группу для пиринга в локальной сети для филиалов, которые находятся в разных доменах или не в одной и той же локальной сети.<br><br>**Значение по умолчанию**: не настроено <br><br>CSP политики: [DOGroupId](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dogroupid)     |

## <a name="bandwidth"></a>Пропускная способность  

|Параметр  |Версия Windows  |Подробные сведения  |
|---------|---------|---------|
|Тип оптимизации пропускной способности     | *См. подробности*        | Выберите, каким образом Intune определяет максимальное значение пропускной способности, которую оптимизация доставки может использовать для всех действий параллельного скачивания.<br><br>Возможны следующие значения.<br><ul><li>**Не настроено**.</li><br><li>**Абсолютное** — укажите значения [Макс. пропускная способность скачивания (в КБ/с)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#maximum-download-bandwidth) и [Макс. пропускная способность отправки (в КБ/с)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#max-upload-bandwidth), которые устройство может использовать при оптимизации загрузки для всех параллельных действий скачивания.<br><br>Требуется Windows 1607<br><br>CSP политики: [DOMaxDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxdownloadbandwidth) и [DOMaxUploadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxuploadbandwidth)</li><br><li>**Процент** — укажите значения [Макс. пропускная способность скачивания переднего плана (в %)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#maximum-foreground-download-bandwidth) и [Макс. фоновая пропускная способность скачивания (в %)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#maximum-foreground-download-bandwidth), которые устройство может использовать при оптимизации загрузки для всех параллельных действий скачивания.<br><br>Требуется Windows 1803<br><br>CSP политики: [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth) и [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)    <br><br><li>**Процент в рабочее время** — для максимальной пропускной способности скачивания [переднего плана](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#set-business-hours-to-limit-foreground-download-bandwidth) и максимальной [фоновой](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#set-business-hours-to-limit-background-download-bandwidth) пропускной способности скачивания можно настроить начало и окончание рабочего времени, а затем указать процент пропускной способности для использования в нерабочее время. <br><br>Требуется Windows 1803 <br><br>CSP политики: [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth) и [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)<br><br>   |
|[Задержка фонового скачивания по HTTP (в секундах)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#delay-background-download-from-http-in-secs) | 1803        | Используйте этот параметр, чтобы настроить максимальное время задержки для фонового скачивания содержимого по протоколу HTTP. Это относится только к скачиваемым файлам, которые поддерживают одноранговый источник скачивания. Во время этой задержки устройство выполняет поиск однорангового узла с доступным содержимым. Во время ожидания однорангового источника скачивание выглядит "зависшим" для конечного пользователя.   <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 60 секунд   <br><br>CSP политики: [DODelayBackgroundDownloadFromHttp](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaybackgrounddownloadfromhttp) <br><br>    |
| [Задержка скачивания переднего плана по HTTP (в секундах)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#delay-foreground-download-from-http-in-secs)      | 1803       | Используйте этот параметр, чтобы настроить максимальное время задержки для скачивания содержимого на переднем плане (интерактивного) по протоколу HTTP. Это относится только к скачиваемым файлам, которые поддерживают одноранговый источник скачивания. Во время этой задержки устройство выполняет поиск однорангового узла с доступным содержимым. Во время ожидания однорангового источника скачивание выглядит "зависшим" для конечного пользователя.   <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 60 секунд   <br><br>CSP политики: [DODelayForegroundDownloadFromHttp](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelayforegrounddownloadfromhttp) <br><br>         |


## <a name="caching"></a>Кэширование  

|Параметр  |Версия Windows  |Подробные сведения  |
|---------|---------|---------|
|[Минимальный объем ОЗУ, необходимый для однорангового кэширования (в ГБ)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#minimum-ram-allowed-to-use-peer-caching)      | 1703        | Укажите минимальный объем ОЗУ в ГБ на устройстве, который должен быть отведен под кэширование членов одноранговой группы. <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 4 ГБ. <br><br>CSP политики: [DOMinRAMAllowedToPeer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dominramallowedtopeer) <br><br>        |
|[Минимальный размер диска для однорангового кэширования (в ГБ)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#minimum-disk-size-allowed-to-use-peer-caching)      | 1703        | Укажите минимальный размер диска в ГБ на устройстве, который должен быть отведен под кэширование членов одноранговой группы. <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 32 ГБ.   <br><br>CSP политики: [DOMinDiskSizeAllowedToPeer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domindisksizeallowedtopeer) <br><br>    |
|[Минимальный размер файла содержимого для однорангового кэширования (в МБ)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#minimum-peer-caching-content-file-size)      | 1703        | Укажите минимальный размер в МБ, которому должен соответствовать файл для кэширования членов одноранговой группы.  <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 10 МБ   <br><br>CSP политики: [DOMinFileSizeToCache](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dominfilesizetocache)  <br><br>      |
|[Минимальный заряд батареи, необходимый для отправки (в %)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#allow-uploads-while-the-device-is-on-battery-while-under-set-battery-level)      | 1709        | Укажите в процентах минимальный уровень заряда батареи на устройстве для отправки данных одноранговым узлам. При падении уровня заряда ниже указанного значения система автоматически приостановит все активные скачивания.   <br><br>**По умолчанию**: *значение не настроено*  <br><br>**Рекомендуется**: 40 %   <br><br>CSP политики: [DOMinBatteryPercentageAllowedToUpload](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dominbatterypercentageallowedtoupload) <br><br>        |
|[Изменение кэша диска](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#modify-cache-drive)        | 1607        | Указать диск, который оптимизация доставки использует для своего кэша. Можно использовать переменную среды, букву диска или полный путь.  <br><br>**По умолчанию**: %SystemDrive% <br><br>CSP политики: [DOModifyCacheDrive](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domodifycachedrive) <br><br>        |
| [Максимальный возраст кэша (в днях)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#max-cache-age)    | 1511         | Укажите, как долго после успешного скачивания каждый файл хранится в кэше оптимизации доставки на устройстве.   <br><br>С помощью Intune можно указать возраст кэша в днях. Число дней, которые можно задать, преобразуется в соответствующее количество секунд, потому что именно так Windows определяет этот параметр. Например, настроив в Intune 3 дня, вы зададите на устройстве 259 200 секунд (3 дня).  <br><br>**По умолчанию**: *значение не настроено*     <br><br>**Рекомендуется**: 7   <br><br>CSP политики: [DOMaxCacheAge](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxcacheage)  <br><br>          |
| Тип максимального размера кэша  | *См. подробности*    | Выберите способ управления объемом дискового пространства на устройстве, которое используется для оптимизации доставки. Если значение не задано, размер кэша по умолчанию составит 20 % свободного места.  <br><ul><li>**Не настроено** (по умолчанию)</li><br><li>**Абсолютный** — укажите [Абсолютный максимальный размер кэша (в ГБ)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#absolute-max-cache-size) для настройки максимального объема места на диске, которое устройство может использовать для оптимизации доставки. Если задано значение 0 (ноль), размер кэша не ограничен; при этом оптимизация доставки будет очищать кэш, когда на устройстве недостаточно места на диске. <br><br>Требуется Windows 1607<br><br> CSP политики: [DOAbsoluteMaxCacheSize](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-doabsolutemaxcachesize) </li><br><li>**Процент** — укажите [Максимальный размер кэша (в %)](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#max-cache-size) для настройки максимального объема места на диске, которое устройство может использовать для оптимизации доставки. Это процент свободного дискового пространства; оптимизация доставки постоянно оценивает объем свободного места на диске и очищает кэш, чтобы удерживать максимальный размер кэша в соответствии с заданным значением. <br><br>Требуется Windows 1511<br><br>CSP политики: [DOMaxCacheSize](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxcachesize)  |
| [Кэширование членов одноранговой группы VPN](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#enable-peer-caching-while-the-device-connects-via-vpn)  | 1709  | Выберите **Включено**, чтобы настроить устройство для участия в одноранговом кэшировании при подключении по VPN к доменной сети. Участвующие устройства могут обмениваться данными с другими сетевыми устройствами домена по VPN или в корпоративной доменной сети.  <br><br>**Значение по умолчанию**: не настроено  <br><br>CSP политики: [DOAllowVPNPeerCaching](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxcacheage)    |

## <a name="next-steps"></a>Дальнейшие шаги

[Настройка оптимизации доставки в Intune](delivery-optimization-windows.md)