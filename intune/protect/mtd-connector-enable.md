---
title: Включение соединителя Mobile Threat Defense в Microsoft Intune
titleSuffix: Microsoft Intune
description: Включение соединителя между партнером по Mobile Threat Defense (MTD) и Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac49edcd4ea71bdbc83cfa093f2bb5e42aefd54
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722076"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Включение соединителя Mobile Threat Defense в Intune

> [!NOTE] 
> Этот раздел относится ко всем партнерам по Mobile Threat Defense.

Во время установки Mobile Threat Defense (MTD) вы настроили политику классификации угроз на консоли партнера по MTD и создали политику соответствия устройств требованиям в Intune. Если вы уже настроили соединитель Intune на консоли партнера по MTD, можете включить соединение с MTD для партнерских приложений MTD.

При интеграции нового приложения с Intune Mobile Threat Defense и активации подключения к Intune служба Intune создает классическую политику условного доступа в Azure Active Directory. Каждое интегрируемое приложение MTD, включая [Защитник ATP](advanced-threat-protection.md) или любое из наших дополнительных [партнерских приложений MTD](mobile-threat-defense.md#mobile-threat-defense-partners), создает новую классическую политику условного доступа. Эти политики можно игнорировать, но нельзя изменять, удалять или отключать.

Классические политики условного доступа для приложений MTD: 

- Используются Intune MTD для обязательной регистрации устройств в Azure AD, чтобы они имели идентификатор устройства перед установлением связи с партнерами MTD. Этот идентификатор необходим для того, чтобы устройства могли успешно сообщить свое состояние в Intune;  
- Не влияют на другие облачные приложения или ресурсы.  
- отличаются от политик условного доступа, которые могут быть созданы для помощи в управлении MTD;
- по умолчанию не взаимодействуют с другими политиками условного доступа, используемыми для оценки.  

Чтобы просмотреть классические политики условного доступа в [Azure](https://portal.azure.com/#home), перейдите в раздел **Azure Active Directory** > **Условный доступ** > **Классические политики**.


## <a name="to-enable-the-mtd-connector"></a>Включение соединителя MTD

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. На **панели мониторинга Intune** выберите **Соответствие устройства**, а затем щелкните **Mobile Threat Defense** в разделе **Установка**.

5. На панели **Mobile Threat Defense** выберите **Добавить**.

6. Выберите решение MTD в раскрывающемся списке **Настраиваемый соединитель Mobile Threat Defense**.

    ![Настройка MTD на портале Intune Azure](./media/mtd-connector-enable/enable-mtd-connector-1.png)

7. Установите переключатели параметров в соответствии с требованиями вашей организации. Отображаемые переключатели зависят от партнера MTD.

## <a name="mtd-toggle-options"></a>Переключатели параметров MTD

Установите переключатели параметров MTD в соответствии с требованиями вашей организации. Подробнее:

- **Подключить устройства Android 4.1+ к [имя параметра MTD] for Work MTD**. При выборе этого параметра устройства с Android версии 4.1 и более поздней могут отправлять отчеты о рисках безопасности в Intune.
  - **Пометить как несоответствующее при отсутствии данных**. Если Intune не получает сведения об устройстве на этой платформе от партнера MTD, устройство считается несоответствующим.
<br></br>
- **Подключить устройства iOS 8.0+ к [имя параметра MTD] for Work MTD**. При выборе этого параметра устройства с iOS версии 8.0 и более поздней могут отправлять отчеты о рисках безопасности в Intune.
  - **Пометить как несоответствующее при отсутствии данных**. Если Intune не получает сведения об устройстве на этой платформе от партнера MTD, устройство считается несоответствующим.
<br></br>
- **Включение синхронизации приложений для устройств с iOS**. Позволяет партнеру Mobile Threat Defense запрашивать в Intune метаданные приложений iOS. Эти метаданные будут использоваться для анализа угроз.

- **Блокировать неподдерживаемые версии ОС**. Блокировка устройств с операционной системой, версия которой ниже минимальной поддерживаемой.

- **Число дней, через которое партнер считается неотвечающим**. Период отсутствия активности в днях, по истечении которого Intune считает партнера неотвечающим из-за потери соединения. Intune не учитывает состояние соответствия неотвечающих партнеров MTD.

> [!IMPORTANT] 
> При возможности рекомендуем перед созданием правил для политик соответствия устройств и условного доступа добавить и назначить приложения MTD. Это помогает гарантировать, что приложение MTD будет готово к работе и доступно для установки конечными пользователями, прежде чем они смогут получать доступ к электронной почте или другим корпоративным ресурсам.

> [!TIP]
> На панели Mobile Threat Defense вы увидите соответствующие значения в полях **Состояние подключения** и **Последняя синхронизация** для Intune и партнера по MTD.