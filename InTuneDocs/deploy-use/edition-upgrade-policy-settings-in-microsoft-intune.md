---
title: "Параметры политики обновления выпусков Windows | Документы Майкрософт"
description: "Узнайте, как использовать автоматизированное обновление устройств с Windows 10 до последней версии с помощью Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: ae6477866991cec4091ff2790b925b0e464375f9


---

# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Параметры политики обновления выпусков Windows в Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

**Политика обновления выпусков** Microsoft Intune позволяет автоматически обновлять устройства с одной из следующих версий Windows 10 до более нового выпуска:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

Поддерживаются следующие варианты обновления:
- С Windows 10 Pro до Windows 10 Корпоративная
- С Windows 10 Домашняя до Windows 10 для образовательных учреждений
- С Windows 10 Mobile до Windows 10 Mobile Корпоративная
- С Windows 10 Holographic Pro до Windows 10 Holographic Корпоративная

## <a name="before-you-start"></a>Перед началом работы
Перед тем как начать обновление устройств до последней версии, потребуется следующее:
* допустимый ключ продукта для установки новой версии Windows на всех целевых устройствах политики (для выпусков Windows 10 Desktop); Вы можете использовать либо ключи многократной активации (MAK), либо ключи сервера управления ключами (KMS).
**Либо** можно использовать файл лицензии от Майкрософт, который содержит сведения о лицензии для установки новой версии Windows на всех целевых устройствах политики (для выпусков Windows 10 Mobile и Windows 10 Holographic).
* Целевые устройства Windows 10 должны быть зарегистрированы в Microsoft Intune. Политику обновления выпусков нельзя использовать на компьютерах под управлением клиентского программного обеспечения Intune.

## <a name="edition-upgrade-policy-settings"></a>Параметры политики обновления выпусков

|Имя параметра|Подробные сведения|
|-|-|
|**Имя**|Введите имя политики обновления выпусков.|
|**Описание**|При необходимости введите описание политики для идентификации ее в консоли Intune.
|**Выпуск, до которого необходимо обновить**|В раскрывающемся списке выберите версию Windows 10 Desktop, Windows 10 Holographic или Windows 10 Mobile, до которой вы хотите обновить целевые устройства.
|**Ключ продукта**|Укажите ключ продукта, полученный от корпорации Майкрософт, с помощью которого можно обновить все целевые устройства Windows 10 Desktop.<br>После создания политики, содержащей ключ продукта, вы не сможете изменить его позже. Это связано с тем, что ключ скрыт по соображениям безопасности. Чтобы изменить его, необходимо повторно ввести весь ключ.
|**Файл лицензии**|Нажмите кнопку **Обзор**, чтобы выбрать полученный от корпорации Майкрософт файл лицензии. Этот файл лицензии содержит сведения о лицензии для выпуска Windows Holographic или Windows 10 Mobile, до которого нужно обновить целевые устройства.

### <a name="see-also"></a>См. также
[Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->


