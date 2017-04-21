---
title: "Известные проблемы в предварительной версии Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Узнайте об известных проблемах в предварительной версии продукта."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 24498abc504f05bd22dc7309bc22948292f9b1e6
ms.openlocfilehash: 4c81c17ba1419f0b5bdc4910be7d26a5893b32e0
ms.lasthandoff: 04/13/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Известные проблемы в предварительной версии Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Из этой статьи вы узнаете об известных проблемах в предварительной версии Intune.

Чтобы сообщить об ошибке, которая не описана в этой статье, [создайте запрос на поддержку](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Чтобы отправить запрос на добавление новой функции в Intune, заполните заявку на нашем сайте [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Группы, созданные с помощью Intune во время миграции, могут влиять на производительность других продуктов корпорации Майкрософт

При миграции с классического портала Intune на портал Azure может появиться новая группа с именем **Все пользователи — b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Обратите внимание, что в эту группу входят все пользователи в Azure Active Directory, а не только лицензированные пользователи Intune. Это может вызвать проблемы совместимости с другими продуктами Майкрософт, если ожидается, что некоторые существующие или новые пользователи не будут включены в какую-либо из групп.

## <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Изменение групп, созданных в помощью Intune во время миграции, приведет к задержке миграции

При подготовке к миграции группы копируются из Intune в Azure AD. Дальнейшие изменения, внесенные на классическом портале Intune, будут отражены в группе Azure AD. При этом изменения, вносимые в Azure AD, не синхронизируются в классической консоли Intune. В результате может возникнуть ошибка миграции на портал Azure с последующей задержкой миграции.

## <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Политики соответствия Intune не будут отображаться в новой консоли. 

Все политики соответствия, созданные на классическом портале Intune, переносятся, но не отображаются на портале Azure. Это происходит из-за изменения макета на портале Azure. Политики соответствия, созданные на классическом портале Intune, по-прежнему применяются, но вам нужно просмотреть и изменить их на классическом портале.
Кроме того, новые политики соответствия, созданные на портале Azure, не будут отображаться на классическом портале.
См. дополнительные сведения о [соответствии устройств требованиям](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance).




## <a name="administration-and-accounts"></a>Администрирование и учетные записи

Глобальные администраторы (также известные, как администраторы клиентов) могут продолжать выполнять повседневные административные задачи без отдельной лицензии Intune или Enterprise Mobility Suite (EMS). Однако если глобальным администраторам необходимо воспользоваться службой, например зарегистрировать личное устройство, корпоративное устройство или воспользоваться корпоративным порталом Intune, им потребуется лицензия Intune или EMS так же, как любому другому пользователю.

## <a name="apple-enrollment-profile-migration"></a>Миграция профилей регистрации Apple
Через несколько месяцев Intune позволит управлять вашей программой регистрации устройств Apple и регистрациями Apple Configurator с помощью нового портала Azure. Если удалить токен программы регистрации устройств Apple и не отправить обновленный токен, то в процессе миграции учетной записи Intune исходный токен будет восстановлен на новом портале Azure. Чтобы удалить этот токен и предотвратить регистрацию DEP, просто удалите токен на портале Azure. 

