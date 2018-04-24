---
title: Данные, отправляемые Intune в Google
titleSuffix: Microsoft Intune
description: Список данных, которые Intune отправляет Google.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78fef57849b8742bb10ece1717234af5cce3f4ba
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="data-intune-sends-to-google"></a>Данные, отправляемые Intune в Google

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Если на устройстве включено управление устройством Android, Microsoft Intune устанавливает соединение с Google и делится с Google сведениями о пользователе и устройстве. Чтобы установить соединение с Microsoft Intune, необходимо создать учетную запись Google.

В следующей таблице перечислены данные, которые Microsoft Intune отправляет Google, когда на устройстве включено управление устройствами:


| Данные, отправляемые Google | Подробные сведения | Назначение | Пример |
|:---:|:---:|:---:|:---:|
| Корпоративный идентификатор | Создается в Google при привязке учетной записи Gmail к Intune. | Основной идентификатор, используемый для взаимодействия между Intune и Google.  Это взаимодействие включает настройку политик, управление устройствами и привязку или отмену привязки предприятия Android к Intune. | Уникальный идентификатор, пример формата: LC04eik8a6 |
| Текст политики | Создается в Intune при сохранении новой политики приложения или конфигурации. | Применение политики к устройствам. | Это коллекция всех настроенных параметров для политики приложения или конфигурации. Может содержать сведения о клиенте, если они указаны в политике, например имя сети, имена приложений и параметры отдельных приложений. |
| Данные устройства | Настройка устройств для рабочего профиля начинается с регистрации в Intune. Настройка управления устройствами начинается с регистрации в Google. | Intune и Google обмениваются сведениями об устройстве в различных целях, например для применения политик, управления устройствами и отчетности. | **Уникальный идентификатор для обозначения имени устройства.** Пример: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Уникальный идентификатор для обозначения имени пользователя.** Пример: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Состояние устройства.** Примеры: активно, отключено, подготовка.<br>**Состояния соответствия требованиям.** Примеры: параметр не поддерживается, отсутствуют требуемые приложения<br>**Сведения о программе.** Примеры: версии программного обеспечения и уровень обновления.<br>**Сведения о сети.** Примеры: IMEI, MEID, WifiMacAddress<br>**Параметры устройства.** Примеры: сведения об уровнях шифрования и допустимости неизвестных приложений на устройстве.<br> Ниже приведен пример сообщения JSON. |
| newPassword | Создается в Intune. | Сброс секретного кода. | Строка с новым паролем. |
| Пользователь Google | Google | Управление рабочим профилем в сценарии BYOD. | Уникальный идентификатор для обозначения привязанной учетной записи Gmail. Пример: 114223373813435875042 |
| Данные приложения | Создается в Intune при сохранении политики приложений. |  | Строка имени приложения. Пример: app:com.microsoft.windowsintune.companyportal |
| Учетная запись службы для предприятия | Создается в Google по запросу Intune. | Используется для проверки подлинности между Intune и Google для транзакций, относящихся к этому клиенту. | Состоит из нескольких частей:<br> **Корпоративный идентификатор**: как описано ранее.<br>**Имя участника-пользователя**: созданное имя участника-пользователя, которое используется для проверки подлинности от имени клиента.<br>Пример: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Ключ**: зашифрованный в кодировке Base64 большой двоичный объект, который используется в запросах проверки подлинности, хранится в службе и выглядит следующим образом:<br> Уникальный идентификатор для обозначения ключа клиента<br>Пример: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Пример данных устройства**

Ниже приведен пример сообщения JSON от Google:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Чтобы прекратить управление устройством Android через Microsoft Intune и удалить данные, необходимо отключить управление устройством Android в Microsoft Intune и удалить учетную запись Google. Сведения об управлении учетными записями см. в учетной записи Google.


