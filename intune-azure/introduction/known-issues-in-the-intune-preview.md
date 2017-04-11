---
title: "Известные проблемы в предварительной версии Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте об известных проблемах в предварительной версии продукта."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Известные проблемы в предварительной версии Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Из этой статьи вы узнаете об известных проблемах в предварительной версии Intune.

Чтобы сообщить об ошибке, которая не описана в этой статье, [создайте запрос на поддержку](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Чтобы отправить запрос на добавление новой функции в Intune, заполните заявку на нашем сайте [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="administration-and-accounts"></a>Администрирование и учетные записи

- Глобальные администраторы (также известные, как администраторы клиентов) могут продолжать выполнять повседневные административные задачи без отдельной лицензии Intune или Enterprise Mobility Suite (EMS). Однако если глобальным администраторам необходимо воспользоваться службой, например зарегистрировать личное устройство, корпоративное устройство или воспользоваться корпоративным порталом Intune, им потребуется лицензия Intune или EMS так же, как любому другому пользователю.

## <a name="apple-enrollment-profile-migration"></a>Миграция профилей регистрации Apple
- Через несколько месяцев Intune позволит управлять вашей программой регистрации устройств Apple и регистрациями Apple Configurator с помощью нового портала Azure. Если удалить токен программы регистрации устройств Apple и не отправить обновленный токен, то в процессе миграции учетной записи Intune исходный токен будет восстановлен на новом портале Azure. Чтобы удалить этот токен и предотвратить регистрацию DEP, просто удалите токен на портале Azure. 

