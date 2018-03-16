---
title: "Удаленная блокировка управляемых устройств с помощью Intune"
titlesuffix: Azure portal
description: "Сведения о том, как удаленно блокировать управляемые устройства с помощью Intune.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a8f3c93507cde4363570a9a39f8b3b1f69c07df
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Удаленная блокировка управляемых устройств с помощью Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Функция **удаленной блокировки** позволяет заблокировать выбранное устройство. Чтобы его разблокировать, владельцу устройства необходимо ввести секретный код. Удаленно заблокировать можно только устройство, для которого задан ПИН-код или пароль.

## <a name="supported-platforms"></a>Поддерживаемые платформы

Удаленная блокировка поддерживается на указанных ниже платформах.

|Платформа|Состояние поддержки|
|---|---|
|Android|Да|
|iOS|Да|
|macOS|Да|
|Windows 10 Desktop|Нет|
|Windows 10 Mobile|Да|
|Windows Phone|Да, для Windows Phone 8.1 и более поздних версий|

> [!NOTE]  
> Для устройств с macOS необходимо задать ПИН-код восстановления из шести цифр. При блокировке в колонке **Обзор устройства** отображается ПИН-код, пока не будет отправлено другое действие устройства.

## <a name="how-to-remote-lock-a-device"></a>Удаленная блокировка устройства

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства** выберите **Все устройства**.
5. Выберите нужное устройство в списке управляемых устройств, а затем действие **Удаленная блокировка**.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы просмотреть состояние выполненного действия, в колонке **Устройства** выберите **Действия устройства**.
