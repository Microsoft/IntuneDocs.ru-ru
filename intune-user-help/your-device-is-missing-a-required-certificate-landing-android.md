---
title: На устройстве отсутствует необходимый сертификат | Документация Майкрософт
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c61a4807e55c3af5038c67c05157b9ad14002347
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31018555"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Устройство не имеет необходимого сертификата

## <a name="whats-a-certificate"></a>Что такое сертификат?

[Криптография](https://technet.microsoft.com/library/cc962030.aspx) — это наука о методах обеспечения защиты данных. Традиционно криптография использовалась для передачи зашифрованных сообщений, обеспечивая [секретность обмена данными](https://technet.microsoft.com/library/cc962019.aspx). Самым простым криптографическим методом является замещение или перестановка букв для создания зашифрованных сообщений: нечитаемых, скремблированных или скрытых. Только пользователь со специальным ключом или _сертификатом_ может преобразовать зашифрованное сообщение в исходную форму, пригодную для чтения. Устройства Android используют сертификаты в Intune, чтобы обезопасить обмен данными между устройством и корпоративными ресурсами, включая сообщения электронной почты и документы.

## <a name="fixing-certificate-issues"></a>Устранение проблем сертификата

Если устройство Android не зарегистрировано в Intune и на нем отсутствует определенный сертификат, требуемый службе поддержки вашей компании, вы не сможете войти в приложение "Корпоративный портал". При попытке войти вы увидите следующее сообщение:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Сначала вам нужно узнать, [есть ли на устройстве сертификат (обычно он предустановлен)](your-device-is-missing-a-preinstalled-certificate-android.md).

Если это не так, служба поддержки вашей компании может [потребовать установить второй сертификат как дополнительное средство защиты](your-device-is-missing-an-IT-required-certificate-android.md).

По-прежнему нужна помощь? Обратитесь в службу поддержки вашей компании. Его контактные данные доступны на [веб-сайте корпоративного портала](https://portal.manage.microsoft.com#HelpDeskDialog).
