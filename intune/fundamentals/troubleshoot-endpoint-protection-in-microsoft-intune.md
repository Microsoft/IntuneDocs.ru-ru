---
title: Распространенные сообщения Endpoint Protection в Microsoft Intune в Azure | Документация Майкрософт
description: Узнайте о распространенных сообщениях и возможных решениях проблем при использовании и устранении неполадок с Endpoint Protection и Microsoft Defender в Microsoft Intune.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 819586a923f5c0f3a81a6d59c4a3895898182f6b
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059156"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Устранение неполадок с Endpoint Protection и возможные решения проблем в Microsoft Intune

В этой статье описаны возможные причины возникновения и способы устранения некоторых ошибок и предупреждений. Эти сведения помогут вам решить проблемы, связанные с использованием Endpoint Protection.

## <a name="microsoft-defender-error-codes"></a>Коды ошибок защитника Майкрософт

Просмотрите журналы событий и коды ошибок, чтобы [устранить неполадки с антивирусной программой Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Распространенные ошибки, связанные с использованием Intune, и возможные решения проблем

### <a name="endpoint-protection-engine-unavailable"></a>Модуль Endpoint Protection недоступен

**Возможная причина**. Модуль Intune Endpoint Protection поврежден или удален.

**Возможные решения**.

- Если Endpoint Protection не работает или не обновляется, обновите или переустановите программу.
- Примените принудительное обновление. В клиентской программе Endpoint Protection (возможно, на панели задач) выберите **Обновить**.
- Откройте на панели управления раздел "Программы" и выберите **Агент Microsoft Intune Endpoint Protection**. Удалите приложение.
- При следующей синхронизации обновлений диспетчер обновления Microsoft Online Management обнаружит, что программа отсутствует, и переустановит ее в запланированное время установки.

### <a name="features-are-disabled"></a>Функции отключены

Может появиться сообщение о том, что некоторые функции отключены. Это сообщение может отображаться, если Intune Endpoint Protection или Microsoft Defender отключены администратором с помощью профиля конфигурации. Также эти программы могут быть отключены пользователем на устройстве. Возможные сообщения.

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Возможные решения**. Включите эти функции. См. подробнее:

- [Добавление параметров Endpoint Protection](../protect/endpoint-protection-configure.md)
- [Антивирусная программа Microsoft Defender](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)
- [Включение пользователем защиты в реальном времени для доступа к ресурсам компании](/intune-user-help/turn-on-defender-windows)

### <a name="malware-definitions-out-of-date"></a>Определения вредоносных программ устарели

Это состояние возникает, если с даты последнего обновления определений вредоносных программ на устройстве прошло более 14 дней. Например, это сообщение может отображаться, если устройство отключено от Интернета или если определения вредоносных программ устарели.

[Возможные решения](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus). Если определения вредоносных программ устарели, их можно обновить с помощью **антивирусной программы Microsoft Defender**.

### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Полная или быстрая проверки просрочены

Полная или быстрая проверки не выполнялись более 14 дней. Такая ситуация возникает, если устройство перезапускается во время полной проверки.

**Возможные решения**. Если проверка просрочена, можно выполнить однократную проверку или запланировать регулярную полную проверку. См. раздел [антивирусная программа Microsoft Defender](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="another-endpoint-protection-application-running"></a>Запущено другое приложение защиты конечных точек

Запущено другое приложение Endpoint Protection, и устройство находится в работоспособном состоянии.

**Возможные решения**. Если установлено другое приложение Endpoint Protection, и Intune обнаружит такое приложение, устройство может работать нестабильно.

## <a name="next-steps"></a>Дальнейшие шаги

Получите [поддержку от корпорации Майкрософт](get-support.md) или обратитесь на [форумы сообщества](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
