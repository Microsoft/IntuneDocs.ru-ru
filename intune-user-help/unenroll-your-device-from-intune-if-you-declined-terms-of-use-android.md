---
title: Удаление устройства из системы управления при отказе от условий использования | Документы Майкрософт
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 169007541bccfc3e26184ac71197265931afbfdd
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508107"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Удаление устройства из системы управления при отказе от условий использования

Если вы отклонили условия использования при попытке войти в приложение корпоративного портала, ваши дальнейшие попытки входа блокируются. Поэтому для удаления устройства из Intune воспользуйтесь этим обходным решением.

При удалении приложения корпоративного портала также удаляется устройство из Intune. Ваше устройство больше не будет иметь доступ к ресурсам компании. Дополнительные сведения о том, что происходит при удалении устройства из системы управления, см. в статье [Что происходит при отмене регистрации устройства в Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Перед удалением приложения корпоративного портала необходимо перейти к параметру **Device administrators** (Администраторы устройства) и отключить **корпоративный портал**. Конкретные действия могут немного отличаться в зависимости от используемого устройства Android.

## <a name="removing-the-device-from-the-company-portal-app"></a>Удаление устройства из приложения корпоративного портала

Чтобы удалить устройство из Intune и удалить приложение корпоративного портала, выполните следующие действия.

1. Последовательно выберите пункты **Параметры** &gt; **Безопасность &amp; Блокировка экрана** &gt; **Администраторы устройств**.

    При выполнении этого шага регистрация устройства сразу же отменяется.

2. Снимите флажок рядом с параметром **Корпоративный портал** или отключите его.

    Теперь можно удалить приложение корпоративного портала.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Удаление данных, собранных приложением корпоративного портала

Чтобы удалить все данные, сохраненные приложением корпоративного портала для Android на вашем устройстве, выполните следующие действия.

- Удалите данные приложения, выбрав "Приложения", щелкнув приложение и нажав кнопку "Очистить данные".
- Удалите папку \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.


По-прежнему нужна помощь? Обратитесь в службу поддержки вашей компании (см. контактные данные на [веб-сайте корпоративного портала](https://go.microsoft.com/fwlink/?linkid=2010980)) или отправьте письмо <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">команде разработчиков Майкрософт для Android</a>.
