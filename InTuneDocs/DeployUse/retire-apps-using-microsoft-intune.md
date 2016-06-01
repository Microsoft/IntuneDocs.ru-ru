---
# required metadata

title: Снятие приложений с учета | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Снятие приложений с учета с помощью Microsoft Intune

Для снятия приложения с учета можно просто удалить его. При развертывании и управлении приложениями с помощью Intune процесс удаления приложения одинаков для мобильных устройств и компьютеров на базе Windows. Для успешного выполнения этой процедуры приложение должно поддерживать процесс удаления.

## Удаление приложения

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Приложения** &gt; **Приложения**.

2.  Выберите приложение, которое необходимо удалить (которое было ранее развернуто), и щелкните **Управление развертыванием**.

3.  На странице **Действие развертывания** выберите **Удалить** в столбце **Утверждение** .

Когда устройство или компьютер выполнит в следующий раз проверку приложений, данное приложение будет удалено.

### См. также
[Добавление приложений в Microsoft Intune](add-apps.md)


<!--HONumber=May16_HO2-->


