---
title: Переименование устройств с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Переименуйте устройство с помощью Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35fae5ea1b3294772db4f4db51179892e08ed5d1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728511"
---
# <a name="rename-a-device-in-intune"></a>Переименование устройства в Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Действие **Rename Device** (Переименовать устройство) позволяет переименовать устройство, зарегистрированное в Intune. Имя устройства изменяется в Intune и на устройстве.

Вы можете переименовать устройства следующих типов:
- корпоративные устройства под управлением Windows; 
- отслеживаемые устройства под управлением iOS
- корпоративные устройства MacOS 10

Сейчас эта функция не поддерживает переименование гибридных устройств Windows Azure AD.

## <a name="rename-a-device"></a>переименовывать устройство;

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Щелкните **Устройства** > **Все устройства**, выберите устройство, затем щелкните **Дополнительно** > **Переименовать устройство**.
4. В колонке **Переименование устройства** введите новое имя в текстовое поле. Имя может содержать буквы, цифры или дефисы. Имя должно содержать хотя бы одну букву или дефис.
5. Если вы хотите перезагрузить устройство после его переименования, щелкните **Да** рядом с параметром **Перезапуск после переименования**.
6. Нажмите кнопку **Переименовать**.



## <a name="next-steps"></a>Дальнейшие шаги

Чтобы увидеть состояние действия **переименования устройства**, перейдите на страницу **Обзор** устройства.
