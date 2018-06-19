---
title: Очистка мобильных устройств под управлением Exchange
description: Microsoft Intune позволяет очистить или сбросить мобильные устройства, управляемые Exchange ActiveSync (EAS) с помощью соединителя Intune с Exchange.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31016090"
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune позволяет очистить или сбросить мобильные устройства, управляемые посредством Exchange ActiveSync (EAS) с помощью соединителя Intune с Exchange. В приведенной ниже таблице описываются возможности очистки, доступные в Exchange ActiveSync:


|      Тип очистки       |              Windows 8.1 и Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        Полная очистка        |          Удаляет учетную запись почты и кэшированную почту.           |                      Восстановление заводских настроек.                       |                      Восстановление заводских настроек.                       |
|  Выборочная очистка/электронная почта   |                  Удаляет учетную запись электронной почты.                  |                       Не поддерживается.                       |                      Не поддерживается.                       |
| Выборочная очистка/политики | Удаляется применение политики, но параметры не изменяются. | Отменяется применение политики, но параметры не изменяются. | Отменяется применение политики, но параметры не изменяются. |

