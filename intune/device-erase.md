---
title: Очистка устройства с macOS
titleSuffix: Microsoft Intune
description: Сведения о том, как удалить все данные, в том числе операционную систему, на устройстве с macOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 64f8b31c4fab5b247ae466df52a0b965f1be813b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179972"
---
# <a name="erase-all-data-from-a-macos-device"></a>Очистка всех данных на устройстве с macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Вы можете удалить на устройстве с macOS все данные, включая операционную систему. Устройство также будет удалено из системы управления Intune. Предупреждение для конечного пользователя отображаться не будет.

1. В [Intune на портале Azure](https://aka.ms/intuneportal) перейдите в раздел **Устройства** > **Все устройства** и выберите устройство, которое хотите очистить.
![Снимок экрана](./media/device-erase/choosedevice.png)
2. Выберите пункты **Дополнительно** > **Очистить** и укажите шестизначный **ПИН-код восстановления**. Это ПИН-код, который должен указать пользователь для переустановки операционной системы на своем устройстве. Обязательно запомните или запишите этот ПИН-код, так как он не будет отображаться после завершения очистки.
![Снимок экрана](./media/device-erase/providepin.png)
3. Нажмите кнопку **ОК**, чтобы очистить устройство.
