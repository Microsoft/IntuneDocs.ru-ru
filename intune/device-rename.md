---
title: Переименование устройств с Windows с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Переименуйте устройство с Windows с помощью Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dfdc3641d583fc045346034ee8543feff1e7cbf
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "59567105"
---
# <a name="rename-a-windows-device-in-intune"></a>Переименование устройства с Windows в Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Действие **переименования устройства** позволяет переименовать корпоративное устройство с Windows, зарегистрированное в Intune. Имя устройства изменяется в Intune и на устройстве. 

Сейчас эта функция не поддерживает переименование гибридных устройств Windows Azure AD.

## <a name="rename-a-device"></a>переименовывать устройство;

1. Войдите на [портал Azure](https://portal.azure.com).
2. Щелкните **Все службы**, выберите **Intune** и щелкните **Microsoft Intune**.
3. Щелкните **Устройства** > **Все устройства**, выберите устройство с Windows, затем щелкните **Дополнительно** > **Переименовать устройство**.
4. В колонке **Переименование устройства** введите новое имя в текстовое поле. Имя может содержать буквы, цифры или дефисы. Имя должно содержать хотя бы одну букву или дефис.
5. Если вы хотите перезагрузить устройство после его переименования, щелкните **Да** рядом с параметром **Перезапуск после переименования**.
6. Нажмите кнопку **Переименовать**.



## <a name="next-steps"></a>Дальнейшие шаги

Чтобы увидеть состояние действия **переименования устройства**, перейдите на страницу **Обзор** устройства.
