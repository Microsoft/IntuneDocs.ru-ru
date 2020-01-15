---
title: Использование отчетов Поддержки обновлений для обновлений Windows в Microsoft Intune
titleSuffix: Microsoft Intune
description: Используйте поддержку обновлений OMS для просмотра данных отчета об обновлениях Windows, развернутых с помощью Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f1e493e0d2d562c0f69454d1999e82b528c724a2
ms.sourcegitcommit: e4602481a25a5e12379f673dfe801c611f51c35b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75731285"
---
# <a name="intune-compliance-reports-for-updates"></a>Отчет о соответствии Intune для обновлений

Когда вы используете Intune для развертывания обновления Windows на устройствах Windows 10, просматривайте сведения о поддержке обновлений с помощью Intune или бесплатного решения *Поддержка обновлений*, которое входит в Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Использование Intune

Просмотрите отчет о политиках, чтобы узнать состояние развертывания для настроенных кругов обновления Windows 10:

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Выберите **Устройства** > **Обзор** > **Состояние обновления ПО**. Вы можете просмотреть общие сведения о состоянии всех назначенных кругов обновления.

3. Чтобы просмотреть дополнительные сведения, выберите **Монитор**. Затем в разделе **Обновление программного обеспечения** щелкните **По состоянию развертывания кольца обновления** и выберите круг развертывания для просмотра сведений.

   В разделе **Мониторинг** выберите один из следующих отчетов, чтобы просмотреть более подробные сведения о кольце обновления:

   - **Состояние устройства** — отображается состояние конфигурации устройства. Дополнительные сведения см. в статье [Обновление объекта deviceConfigurationDeviceStatus]( https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationdevicestatus-update?view=graph-rest-1.0).

   - **Состояние пользователя** — отображаются имя пользователя, состояние и дата последнего отчета. Дополнительные сведения см. в статье о [получении списка объектов deviceConfigurationUserStatus](https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationuserstatus-list?view=graph-rest-1.0).

   - **Состояние обновления конечного пользователя** — отображается состояние обновления устройства Windows. Дополнительные сведения см. в статье о [windowsUpdateState](https://docs.microsoft.com/graph/api/resources/intune-shared-windowsupdatestate?view=graph-rest-beta).

## <a name="use-update-compliance"></a>Использование средства "Поддержка обновлений"

Для отслеживания выпуска обновлений Windows 10 можно использовать решение [Поддержка обновлений](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) в Windows Analytics. Решение "Поддержка обновлений" предоставляется через портал Azure бесплатно для устройств, которые отвечают [предварительным требованиям](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Благодаря этому решению можно развернуть коммерческий идентификатор на любых управляемых Intune устройствах с Windows 10, для которых требуется получать отчеты о поддержке обновлений.  

В Intune для настройки коммерческого идентификатора используйте параметры OMA-URI настраиваемой политики. См. статью [Использование настраиваемых параметров для устройств Windows 10 в Intune](../configuration/custom-settings-windows-10.md).

Путь OMA-URI (с учетом регистра) для настройки коммерческого идентификатора выглядит следующим образом: *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

Например, в разделе **Добавление или изменение настройки OMA-URI** можно использовать следующие значения.

- **Имя параметра**: коммерческий идентификатор Windows Analytics.
- **Описание параметра**: настройка коммерческого идентификатора для решений Windows Analytics.
- **OMA-URI** (с учетом регистра): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Тип данных**: Строка
- **Значение**. \<Используйте GUID, показанный на вкладке "Телеметрия Windows" в рабочей области OMS>

> [!NOTE]
> Дополнительные сведения о сервере DM MS см. в статье о [поставщике службы конфигурации DMClient]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Дальнейшие шаги

[Управление обновлениями программного обеспечения в Intune](windows-update-for-business-configure.md)
