---
title: "Интеграция управления доступом к сети с Intune"
titleSuffix: Intune on Azure
description: "Интеграция управления доступом к сети (NAC) с Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6037ec4638b487c0bae8fcecf2d9bd010e3bc59a
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Интеграция управления доступом к сети (NAC) с Intune

Intune интегрируется с партнерами по управлению доступом сети, чтобы помочь организациям защитить корпоративные данные, когда устройства пытаются обратиться к локальным ресурсам.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Как решения NAC и Intune помогают защитить ресурсы вашей организации?

Решения NAC отвечают за проверку состояния регистрации и соответствия устройств в Intune для принятия решений по управлению доступом. Если устройство не зарегистрировано либо зарегистрировано, но не удовлетворяет политикам соответствия устройств Intune, его требуется перенаправить в Intune для регистрации и (или) для проверки соответствия.

### <a name="example"></a>Пример

Если устройство зарегистрировано и является соответствующим в рамках Intune, решение NAC должно предоставить ему доступ к корпоративным ресурсам. Например, можно разрешать или запрещать доступ пользователям, пытающимся обратиться к корпоративным ресурсам Wi-Fi или VPN.

## <a name="nac-and-conditional-access"></a>NAC и условный доступ

NAC использует условный доступ для принятия решений по управлению доступом.

- Ознакомьтесь с дополнительными сведениями о [стандартных способах использования условного доступа с помощью Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Принцип работы интеграции с NAC

Ниже приведен обзор работы интеграции NAC с Intune, в первых трех шагах объясняется процесс подключения. Типичная работа после интеграции решения NAC с Intune описана в шагах 4–9.

![Работа NAC с Intune](./media/ca-intune-common-ways-2.png)

1.  Зарегистрируйте партнерское решение NAC в Azure Active Directory (AAD) и предоставьте делегированные разрешения API Intune NAC.

2.  Настройте партнерское решения NAC с помощью соответствующих параметров, включая URL-адрес обнаружения Intune.

3.  Настройте партнерское решение NAC для проверки подлинности сертификата.

4.  Пользователь подключается к корпоративной точке доступа Wi-Fi или выполняет запрос на VPN-подключение.

5.  Партнерское решение NAC перенаправляет сведения об устройстве в Intune и запрашивает там состояние регистрации и соответствия устройства.

6.  Если устройство не является соответствующим или не зарегистрировано, партнерское решение NAC просит пользователя зарегистрировать устройство или обеспечить его соответствие.

7.  Устройство пытается повторно проверить свое состояние соответствия и (или) регистрации.

8.  После регистрации и обеспечения соответствия устройства партнерское решение NAC получает это состояние из Intune.

9.  Устанавливается соединение, предоставляющее устройству доступ к корпоративным ресурсам.

## <a name="next-steps"></a>Дальнейшие действия

-   [Интеграция Cisco ISE с Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Интеграция Citrix NetScaler с Intune](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Интеграция HP Aruba Clear Pass с Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
