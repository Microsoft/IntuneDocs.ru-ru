---
title: "Рекомендации по управлению устройствами Windows с помощью Intune в Azure"
description: "Рекомендации по использованию Intune в Azure для управления устройствами Windows в вашей организации."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4018f505626b05dc84be509ca1e42cefff94b90
ms.sourcegitcommit: dc2595bec05206a826cd10cb834bf6043145c917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2017
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Intune в консоли Azure и устаревшем клиенте компьютера Intune

Недавно Intune был перемещен на архитектуру службы приложений SaaS на основе Azure. Служба Azure предоставляет значительные улучшения масштабирования, емкости и производительности. При этом переходе также предлагаются улучшенные возможности администрирования Intune и оптимизированные рабочие процессы на портале Azure. 

При использовании Intune в Azure для управления устройствами Windows в вашей организации учитывайте следующее:

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Устаревшие функции клиента компьютера доступны только в консоли Silverlight

Рабочие процессы управления клиента компьютера Intune используют [консоль администрирования Intune на базе Silverlight](https://manage.microsoft.com/), что приводит к следующим последствиям:

- Для всех задач управления (кроме управления группами) с помощью клиента компьютера Intune необходимо использовать консоль Silverlight.
- При управлении группами необходимо использовать [Intune на портале Azure](https://portal.azure.com/). Это требование появилось, потому что теперь Intune использует группы Azure Active Directory вместо устаревших групп Intune. 

Из-за этого фильтрация "на основе группы" в представлениях панели мониторинга консоли Silverlight немного изменилась. Чтобы выполнить фильтрацию в обновленном пользовательском интерфейсе Silverlight, сделайте следующее:

1. Выберите представление.
2. В поле **Фильтры** введите имя группы, для которой необходимо выполнить фильтрацию, и нажмите клавишу ВВОД. В этой группе выполнится фильтрация списка представлений для устройств.

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a>Управление устройствами с Windows 10 с помощью MDM

Мы рекомендуем использовать [управление мобильными устройствами (MDM) для управления устройствами с Windows 10](https://docs.microsoft.com/intune/device-restrictions-windows-10) вместо устаревшего клиента компьютера Intune. Возможность управлять устройствами с Windows 10 с помощью MDM доступна в Intune на портале Azure. При таком управлении предоставляется множество новых возможностей управления и обеспечения безопасности, которые недоступны в устаревшем клиенте компьютера Intune.

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Управление устройствами с Windows 7 с помощью клиента компьютера Intune

Для устройств с Windows 7, которыми нельзя управлять с помощью MDM, мы продолжим предоставлять поддержку имеющихся возможностей клиента компьютера Intune только в консоли Silverlight. Рассмотрите возможность перехода на управление MDM при обновлении до Windows 10.

## <a name="mdm-capabilities"></a>Возможности управления мобильными устройствами

Подробное сравнение возможностей клиента компьютера и MDM см. в статье [Сравнение возможностей для управления ПК Windows как компьютерами или мобильными устройствами](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison). Для зарегистрированных с помощью MDM устройств с Windows 10 продолжают появляться новые возможности, включая параметры оценки для приложений Win 32. Ознакомьтесь со статьей [Новые возможности Microsoft Intune](https://docs.microsoft.com/intune/whats-new), чтобы узнать о последних изменениях в службе.

## <a name="switch-from-pc-client-to-mdm"></a>Переход от клиента компьютера к управлению мобильными устройствами

Чтобы перейти от управления устройствами с Windows 10 с помощью клиента Intune к управлению с помощью MDM, сделайте следующее:

1. В консоли Silverlight выполните **выборочную очистку** для отмены регистрации устройства в клиенте компьютера.
  ![](media/intune_on_azure/image02.png)
2. Повторно зарегистрируйте устройство с помощью [MDM (или путем присоединения к Azure Active Directory)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Дальнейшие действия
[Регистрация устройств с Windows](https://docs.microsoft.com/intune/windows-enroll)

 