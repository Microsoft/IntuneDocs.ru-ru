---
title: На устройстве отсутствует необходимый сертификат | Документация Майкрософт
titlesuffix: Microsoft Intune
description: На устройстве отсутствует сертификат, требуемый службой поддержки вашей компании.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
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
ms.custom: intune-enduser; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc86a53dd790059297430fd6b08f1a699aafbc84
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850664"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Устройство не имеет необходимого сертификата

## <a name="whats-a-certificate"></a>Что такое сертификат?

[Криптография](https://technet.microsoft.com/library/cc962030.aspx) — это наука о методах обеспечения защиты данных. Традиционно криптография использовалась для передачи зашифрованных сообщений, обеспечивая [секретность обмена данными](https://technet.microsoft.com/library/cc962019.aspx). Самым простым методом шифрования является замещение или перестановка букв для создания зашифрованных сообщений: нечитаемых, скремблированных или скрытых. Только пользователь со специальным ключом или _сертификатом_ может преобразовать зашифрованное сообщение в исходную форму, пригодную для чтения. Устройства Android используют сертификаты в Intune, чтобы обезопасить обмен данными между устройством и корпоративными ресурсами, включая сообщения электронной почты и документы.

## <a name="fixing-certificate-issues"></a>Устранение проблем сертификата

Если устройство Android не зарегистрировано в Intune и на нем отсутствует определенный сертификат, требуемый службе поддержки вашей компании, вы не сможете войти в приложение "Корпоративный портал". При попытке войти вы увидите следующее сообщение:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Сначала вам нужно узнать, [есть ли на устройстве сертификат (обычно он предустановлен)](your-device-is-missing-a-preinstalled-certificate-android.md).

Если проблемы с сертификатом не удалось решить, служба поддержки вашей компании может [потребовать установить второй сертификат как дополнительное средство защиты](your-device-is-missing-an-IT-required-certificate-android.md).

По-прежнему нужна помощь? Обратитесь в службу поддержки вашей компании. Его контактные данные доступны на [веб-сайте корпоративного портала](https://go.microsoft.com/fwlink/?linkid=2010980).
