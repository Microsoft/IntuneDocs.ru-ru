---
title: Использование отчетов Поддержки обновлений для обновлений Windows в Microsoft Intune
titleSuffix: Microsoft Intune
description: Используйте поддержку обновлений OMS для просмотра данных отчета об обновлениях Windows, развернутых с помощью Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09f3cafc16d8a08885731aa244a089367c6c0933
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728108"
---
# <a name="intune-compliance-reports-for-updates"></a>Отчет о соответствии Intune для обновлений
Когда вы используете Intune для развертывания обновления Windows на устройствах Windows 10, просматривайте сведения о поддержке обновлений с помощью Intune или бесплатного решения *Поддержка обновлений*, которое входит в Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Использование Intune
Просмотрите отчет о политиках, чтобы узнать состояние развертывания для настроенных кругов обновления Windows 10: 
1. Войдите на [портал Azure](https://portal.azure.com/).
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Выберите **Обновления программного обеспечения** > **Обзор**. Вы можете просмотреть общие сведения о состоянии всех назначенных кругов обновления.
4. Откройте один из указанных ниже отчетов.  

   **Для всех кругов развертывания**:
   1. На панели **Обновления программного обеспечения** > **Круги обновлений Windows 10**.
   2. В разделе **Мониторинг** выберите **По состоянию развертывания кольца обновления**.  

   **Для определенных кругов развертывания**:  

   1. На панели **Обновления программного обеспечения** > **Круги обновлений Windows 10** выберите круг развертывания для просмотра.  
   2. В разделе **Мониторинг** выберите один из следующих отчетов, чтобы просмотреть более подробные сведения о кольце обновления:  
      - **Состояние устройства**  
      - **Состояние пользователя**  

## <a name="use-update-compliance"></a>Использование средства "Поддержка обновлений"
Для отслеживания выпуска обновлений Windows 10 можно использовать решение [Поддержка обновлений](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) в Windows Analytics. Решение "Поддержка обновлений" предоставляется через портал Azure бесплатно для устройств, которые отвечают [предварительным требованиям](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Благодаря этому решению можно развернуть коммерческий идентификатор на любых управляемых Intune устройствах с Windows 10, для которых требуется получать отчеты о поддержке обновлений.  

В консоли Intune для настройки коммерческого идентификатора можно использовать параметры OMA-URI настраиваемой политики. Дополнительные сведения см. в разделе [Параметры политики Intune для устройств с Windows 10 в Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

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

