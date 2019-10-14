---
title: Активация режима пропажи на устройствах iOS с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Включите или запустите режим пропажи с помощью Microsoft Intune, чтобы настроить сообщение, которое будет отображаться на экране блокировки потерянного или украденного устройства iOS. И ознакомьтесь со сведениями о безопасности и конфиденциальности при использовании действия "Режим пропажи".
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac83160e6604b7a679e03bb244e1dd5081a5fc5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728641"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Включение режима пропажи на устройствах iOS с помощью Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Действие устройства **Режим пропажи** позволяет активировать режим пропажи на потерянных или украденных устройствах iOS. Этот режим позволяет ввести сообщение и номер телефона, которые отображаются на экране блокировки устройства. Для использования режима пропажи это должно быть корпоративное устройство с iOS, которое находится в защищенном режиме.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- iOS 9.3 и более поздние версии.

Эта возможность не поддерживается в следующих системах: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Включение режима пропажи

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Выберите **Устройства**, а затем — **Все устройства**.
4. Выберите нужное устройство iOS в списке управляемых устройств и щелкните **Дополнительно**. Затем выберите удаленное действие **Режим пропажи**.
5. В разделе **режима пропажи** включите эту функцию. Затем введите сообщение, которое будет отображаться, и номер контактного телефона.
6. Нажмите кнопку **OK**, чтобы сохранить изменения.

Если режим пропажи включен, устройство будет полностью заблокировано. Пока данный режим не будет отключен, пользователь не сможет получить доступ к устройству. Когда режим пропажи включен, можно использовать действие [Найти устройство](device-locate.md), чтобы узнать, где находится устройство.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Сведения о безопасности и конфиденциальности для режима пропажи и действия "Найти устройство"
- Сведения о расположении устройства будут отправляться в Intune только в том случае, когда это действие включено.
- При использовании действия "Найти устройство" координаты широты и долготы устройства отправляются в Intune и отображаются на портале Azure.
- Данные будут храниться в течение 24 часов, а затем будут удалены. Данные о расположении удалить вручную нельзя.
- Данные о расположении шифруются как во время хранения, так и во время передачи.
- В сообщении, которое будет отображаться на экране блокировки, укажите подробные сведения для возврата потерянного устройства.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы отобразились сведения о состоянии режима пропажи (включен или отключен), откройте раздел **Устройства** и выберите **Действия устройства**.