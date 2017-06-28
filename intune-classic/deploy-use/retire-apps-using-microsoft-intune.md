---
title: "Снятие приложений с учета"
description: "Узнайте, как прекратить использование приложений или удалить их с помощью Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1851fa03d36ffe42a49fd557cdd0c2c6250726f4
ms.contentlocale: ru-ru
ms.lasthandoff: 06/08/2017


---

# <a name="retire-apps-using-microsoft-intune"></a>Снятие приложений с учета с помощью Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Для снятия приложения с учета можно просто удалить его. При развертывании приложений и управлении ими с помощью Intune процесс удаления приложения одинаков для мобильных устройств и компьютеров на базе Windows. Для успешного выполнения этой процедуры приложение должно поддерживать процесс удаления.

## <a name="uninstall-an-app"></a>Удаление приложения

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Приложения** &gt; **Приложения**.

2.  Выберите приложение, которое необходимо удалить (которое было ранее развернуто), и выберите **Управление развертыванием**.

3.  На странице **Действие развертывания** выберите **Удалить** в столбце **Утверждение** .

Когда устройство или компьютер выполнит в следующий раз проверку приложений, данное приложение будет удалено.

### <a name="see-also"></a>См. также
[Добавление приложений в Microsoft Intune](add-apps.md)

