---
title: Снятие компьютера Windows с учета
titlesuffix: Microsoft Intune
description: Сведения о снятии с учета компьютера Windows, управляемого Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0bafdfd4d688ccbbd547c41e0495af19f0b691e4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461113"
---
# <a name="retire-a-windows-pc"></a>Снятие компьютера Windows с учета

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Воспользуйтесь указанными ниже сведениями, чтобы снять с учета настольные системы Windows, которые управляются как компьютеры с помощью программного клиента Intune на них. При снятии компьютера с учета он удаляется из системы управления Intune. Вы не можете выполнить из Intune очистку ПК для возврата к заводским значениям параметров.

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) щелкните **Группы** &gt; **Все устройства** (или другую группу с компьютером, который требуется снять с учета).

2.  Выберите устройства для снятия с учета, а затем щелкните **Снять с учета/очистить**.

Чтобы повторно зарегистрировать компьютер в Intune, переустановите программный клиент на компьютере, используя сведения в разделе [Установка клиента на компьютере Windows с помощью Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Если компьютеру не удается подключиться к Intune, в рабочей области **Панель мониторинга** отобразится сообщение.

При снятии компьютера с учета происходит следующее:

-   Он удаляется из системы управления и инвентаризации Intune, а связанная с ним лицензия становится доступной для использования. Процедуры снятия с учета и очистки удаляют клиентское программное обеспечение Intune, но не удаляют приложения и данные с компьютера. Такое снятие с учета не приводит к полной очистке компьютера.

-   Его состояние больше не отображается в консоли Intune.

-   Intune удаляет программный клиент с компьютера. Если компьютер не подключен к службе Intune, программный клиент будет удален при следующем подключении.

-   Microsoft Intune Endpoint Protection удаляется с компьютера. Если на компьютере установлено другое приложение конечной точки, которое было отключено, его можно повторно включить после удаления Microsoft Intune Endpoint Protection, чтобы обеспечить защиту компьютеров.

-   Все политики удаляются с компьютера, а значения, заданные политикой, изменяются.

-   Компьютер перестает получать обновления программного обеспечения и определений вредоносных программ от службы Intune.

-   В зависимости от настроек снятые с учета компьютеры могут продолжать получать обновления с помощью служб Windows Server Update Services, Центра обновления Windows или Центра обновления Майкрософт.

    > [!IMPORTANT]
    > Если клиентское ПО устанавливалось с помощью объекта групповой политики, его необходимо удалить, прежде чем можно будет удалить клиентское ПО, чтобы предотвратить повторную установку программного обеспечения.

    Если не удается удалить клиент Endpoint Protection, прочтите раздел [Устранение неполадок Endpoint Protection](/intune/troubleshoot-endpoint-protection-in-microsoft-intune) для получения дополнительных сведений.

### <a name="see-also"></a>См. также

[Общие задачи управления ПК с Windows с программным клиентом Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
