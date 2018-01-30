---
title: "Интеграция управления доступом к сети с Intune"
titlesuffix: Azure portal
description: "Интеграция управления доступом к сети (NAC) с Intune"
keywords: 
author: bruceperlerMS
ms.author: bruceper
manager: dougeby
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4673a6c6d0b83c7f31eecc919bcaa0e952f373a0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="network-access-control-nac-integration-with-intune"></a>Интеграция управления доступом к сети (NAC) с Intune

Intune интегрируется с партнерами по управлению доступом сети, чтобы помочь организациям защитить корпоративные данные, когда устройства пытаются обратиться к локальным ресурсам.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Как решения NAC и Intune помогают защитить ресурсы вашей организации?

Решения NAC отвечают за проверку состояния регистрации и соответствия устройств в Intune для принятия решений по управлению доступом. Если устройство не зарегистрировано либо зарегистрировано, но не удовлетворяет политикам соответствия устройств Intune, его требуется перенаправить в Intune для регистрации и (или) для проверки соответствия.

### <a name="example"></a>Пример

Если устройство зарегистрировано и является соответствующим в рамках Intune, решение NAC должно предоставить ему доступ к корпоративным ресурсам. Например, можно разрешать или запрещать доступ пользователям, пытающимся обратиться к корпоративным ресурсам Wi-Fi или VPN.

## <a name="feature-behaviors"></a>Поведение функции

Устройства, которые активно синхронизируются с Intune, нельзя переключить из состояния **Совместимый** / **Несовместимый** в состояние **Несинхронизированный** (или **Неизвестный**). Состояние **Неизвестный** используется только для новых зарегистрированных устройств, которые еще не были проверены на предмет соответствия.

Если для устройств заблокирован доступ к ресурсам, служба блокировки должна перенаправлять всех пользователей [портала управления](https://portal.manage.microsoft.com), чтобы определить причину блокировки устройства.  Если пользователи посетят эту страницу, их устройства будут синхронно проверены на предмет соответствия.

## <a name="nac-and-conditional-access"></a>NAC и условный доступ

NAC использует условный доступ для принятия решений по управлению доступом. См. дополнительные сведения о [стандартных способах использования условного доступа с помощью Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Принцип работы интеграции с NAC

Ниже описаны особенности интеграции NAC с Intune. В шагах 1–3 объясняется процесс подключения. Типичная работа после интеграции решения NAC с Intune описана в шагах 4–9.

![Работа NAC с Intune](./media/ca-intune-common-ways-2.png)

1. Зарегистрируйте партнерское решение NAC в Azure Active Directory (AAD) и предоставьте делегированные разрешения API Intune NAC.
2. Настройте партнерское решения NAC с помощью соответствующих параметров, включая URL-адрес обнаружения Intune.
3. Настройте партнерское решение NAC для проверки подлинности сертификата.
4. Пользователь подключается к корпоративной точке доступа Wi-Fi или выполняет запрос на VPN-подключение.
5. Партнерское решение NAC перенаправляет сведения об устройстве в Intune и запрашивает там состояние регистрации и соответствия устройства.
6. Если устройство не является соответствующим или не зарегистрировано, партнерское решение NAC просит пользователя зарегистрировать устройство или обеспечить его соответствие.
7. Устройство пытается повторно проверить свое состояние соответствия и (или) регистрации.
8. После регистрации и обеспечения соответствия устройства партнерское решение NAC получает это состояние из Intune.
9. Устанавливается соединение, предоставляющее устройству доступ к корпоративным ресурсам.

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция Cisco ISE с Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Интеграция Citrix NetScaler с Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Интеграция HP Aruba Clear Pass с Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
