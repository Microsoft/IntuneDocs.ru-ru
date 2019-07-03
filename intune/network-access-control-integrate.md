---
title: Интеграция управления доступом к сети в Microsoft Intune в Azure | Документы Майкрософт
description: Решения по управлению доступом к сети (NAC) используются для проверки состояния регистрации и соответствия устройств в Intune. В NAC поддерживаются определенные режимы и работа с условным доступом. Ознакомьтесь с действиями по адаптации и получению списка партнерских решений.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 400de55e26076a8d612ac31388d5c5daec68d4a0
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044534"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Интеграция управления доступом к сети (NAC) с Intune

Intune интегрируется с партнерами по управлению доступом сети, чтобы помочь организациям защитить корпоративные данные, когда устройства пытаются обратиться к локальным ресурсам.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Как решения NAC и Intune помогают защитить ресурсы вашей организации?

Решения NAC проверяют состояние регистрации и соответствия устройств в Intune для принятия решений по управлению доступом. Если устройство не зарегистрировано либо зарегистрировано, но не удовлетворяет политикам соответствия устройств Intune, его требуется перенаправить в Intune для регистрации или проверки соответствия.

### <a name="example"></a>Пример

Если устройство зарегистрировано и является соответствующим в рамках Intune, решение NAC должно предоставить ему доступ к корпоративным ресурсам. Например, можно разрешать или запрещать доступ пользователям, пытающимся обратиться к корпоративным ресурсам Wi-Fi или VPN.

## <a name="feature-behaviors"></a>Поведение функции

Устройства, которые активно синхронизируются с Intune, нельзя переключить из состояния **Соответствующее** / **Несоответствующее** в состояние **Несинхронизированное** (или **Неизвестное**). Состояние **Неизвестное** используется только для новых зарегистрированных устройств, которые еще не были проверены на предмет соответствия.

Если для устройств заблокирован доступ к ресурсам, служба блокировки должна перенаправлять всех пользователей [портала управления](https://portal.manage.microsoft.com), чтобы определить причину блокировки устройства.  Если пользователи посетят эту страницу, их устройства будут синхронно проверены на предмет соответствия.

## <a name="nac-and-conditional-access"></a>NAC и условный доступ

NAC использует условный доступ для принятия решений по управлению доступом. См. дополнительные сведения о [стандартных способах использования условного доступа с помощью Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Принцип работы интеграции с NAC

Ниже описаны особенности интеграции NAC с Intune. В шагах 1–3 объясняется процесс подключения. Типичная работа после интеграции решения NAC с Intune описана в шагах 4–9.

![Схематическое изображение принципов работы NAC с Intune](./media/ca-intune-common-ways-2.png)

1. Зарегистрируйте партнерское решение NAC в Azure Active Directory (AAD) и предоставьте делегированные разрешения API Intune NAC.
2. Настройте партнерское решения NAC с помощью соответствующих параметров, включая URL-адрес обнаружения Intune.
3. Настройте партнерское решение NAC для проверки подлинности сертификата.
4. Пользователь подключается к корпоративной точке доступа Wi-Fi или выполняет запрос на VPN-подключение.
5. Партнерское решение NAC перенаправляет сведения об устройстве в Intune и запрашивает там состояние регистрации и соответствия устройства.
6. Если устройство не соответствует требованиям или не зарегистрировано, партнерское решение NAC просит пользователя зарегистрировать устройство или обеспечить его соответствие.
7. Устройство пытается повторно проверить свое состояние соответствия и регистрации.
8. После регистрации и обеспечения соответствия устройства партнерское решение NAC получает это состояние из Intune.
9. Устанавливается соединение, предоставляющее устройству доступ к корпоративным ресурсам.

## <a name="use-nac-for-vpn-on-your-ios-devices"></a>Использование NAC для VPN на устройствах iOS  

- Служба NAC доступна для следующих виртуальных частных сетей без включения NAC в профиле VPN:

  - NAC для Cisco Legacy AnyConnect
  - F5 Access прежних версий
  - Citrix VPN

- Служба NAC также доступна для Citrix SSO и F5 Access. Чтобы включить NAC для Citrix SSO, сделайте следующее:

  - Используйте Citrix Gateway 12.0.59 или более поздней версии.  
  - Пользователям нужно использовать Citrix SSO 1.1.6 или более поздней версии.
  - Выполните [интеграцию NetScaler с Intune для NAC](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html), как описано в документации по продуктам Citrix.
  - В профиле VPN выберите **Базовые параметры** > **Включить управление сетевым доступом (NAC)** > выберите **Принять**.

  VPN-подключение разрывается каждые 24 часа из соображений безопасности. VPN-подключение может сразу же быть переустановлено.

- Чтобы включить NAC для F5 Access:

  - Используйте F5 BIG-IP 13.1.1.5. BIG-IP 14 не поддерживается.
  - Интеграция BIG-IP с Intune для NAC. Эти шаги перечислены в руководстве F5 [Обзор: настройка APM для проверки состояния устройства с системами управления конечными точками](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
  - В профиле VPN выберите **Базовые параметры** > **Включить управление сетевым доступом (NAC)** > выберите **Принять**.

  VPN-подключение разрывается каждые 24 часа из соображений безопасности. VPN-подключение может сразу же быть переустановлено.

- Управление сетевым доступом сейчас не поддерживается для следующих клиентов VPN в iOS:
  - Cisco AnyConnect

Мы с нашими партнерами работаем над выпуском решения NAC для этих клиентов. Когда решения будут готовы, в этой статье будет появляться дополнительная информация.

## <a name="next-steps"></a>Дальнейшие шаги

- [Интеграция Cisco ISE с Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Интеграция Citrix NetScaler с Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Интеграция F5 BIG-IP Access Policy Manager с Intune](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-13-0-0/6.html)
- [Интеграция HP Aruba ClearPass с Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Интеграция Squadra security Removable Media Manager (secRMM) с Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
