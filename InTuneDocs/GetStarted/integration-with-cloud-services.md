---
title: "Интеграция Intune с облачными службами (Майкрософт) | Microsoft Intune"
description: "Интеграция Intune с облачными службами и продуктами Майкрософт, а также с другими продуктами Майкрософт"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: b2df2a2ec092ed9bb7d12b7f51a4fd9c9858f041


---

# Интеграция Intune с облачными службами и продуктами Майкрософт

Перед настройкой [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] ознакомьтесь с этим разделом и другими требованиями в статье [Предварительные сведения для установки Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Интеграция с другими облачными службами Майкрософт


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] использует ту же основу, что и другие облачные службы Майкрософт. При наличии одной учетной записи для подписки на несколько облачных служб эти службы используют одну инфраструктуру Microsoft Azure AD и являются клиентами Azure AD. Azure AD обеспечивает основные возможности управления каталогами и удостоверениями для облачных служб Майкрософт.

Дополнительные сведения об [администрировании Azure AD](http://technet.microsoft.com/library/hh967611.aspx) см. в библиотеке TechNet.

## Интеграция с другими продуктами Майкрософт
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] можно использовать как автономную облачную службу или как облачную службу, интегрированную с другими продуктами. В настоящее время поддерживается прямая интеграция [!INCLUDE[cmshort](../includes/cmshort_md.md)] только с [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Решение об интеграции [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] с [!INCLUDE[cmshort](../includes/cmshort_md.md)] нельзя отменить. В рамках этого решения центр управления мобильными устройствами необходимо задать в консоли [!INCLUDE[cmshort](../includes/cmshort_md.md)], а не в [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. После настройки центра управления мобильными устройствами нельзя изменить или отменить эту конфигурацию.

При использовании [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] с [!INCLUDE[cmshort](../includes/cmshort_md.md)] для управления [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] не используется [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], вместо нее применяется консоль [!INCLUDE[cmshort](../includes/cmshort_md.md)]. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] по-прежнему использует свое облачное хранилище в Azure для размещения программного обеспечения, развертываемого на устройствах, которыми вы управляете с помощью [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Дополнительные сведения см. в разделе [Управление мобильными устройствами с помощью Configuration Manager и Windows Intune](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) раздела документации по [!INCLUDE[cm5short](../includes/cm5short_md.md)] с пакетом обновления 1 (SP1).

### См. также
[Предварительные сведения перед началом работы с Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


