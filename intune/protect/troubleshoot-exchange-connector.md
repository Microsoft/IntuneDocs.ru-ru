---
title: Устранение проблем в работе соединителя с Exchange
titleSuffix: Microsoft Intune
description: Устранение неполадок, связанных с работой соединителя Intune с локальной организацией Exchange.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 962e66a9fdf6d8abcf6855f645775026ee4db850
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508843"
---
# <a name="troubleshoot-the-intune-exchange-connector"></a>Устранение неполадок с соединителем Intune Exchange

Эта статья описывает устранение неполадок, связанных с работой соединителя Intune Exchange.

## <a name="before-you-start"></a>Перед началом работы

Прежде чем начать устранение неполадок с Exchange Connector в Intune, собирайте основные сведения, чтобы вы работали с надежной основой. Этот подход может помочь лучше понять природу проблемы и ускорить его решение.

- Убедитесь, что процесс соответствует требованиям к установке. Перейдите к статье [Настройка локального соединителя Exchange для Intune](exchange-connector-install.md).
- Убедитесь, что у вашей учетной записи есть разрешения администратора Exchange и Intune.
- Обратите внимание на полный и точный текст сообщения об ошибке, сведения и место отображения сообщения.
- Определить время запуска проблемы: 
  - Вы настраиваете соединитель в первый раз? 
  - Правильно ли работает соединитель, а затем произошел ли сбой?
  - Если он работал, какие изменения произошли в среде Intune, среде Exchange или на компьютере, где работает программное обеспечение соединителя?
- Что такое центр MDM? Если System Center Configuration Manager, какая версия Configuration Manager используется?
- Какую версию Exchange вы используете?

### <a name="use-powershell-to-get-more-data-on-exchange-connector-issues"></a>Использование PowerShell для получения дополнительных сведений о неполадках в работе соединителя Exchange

- Чтобы получить список всех мобильных устройств для почтового ящика, используйте `Get-ActiveSyncDeviceStatistics -mailbox mbx`
- Чтобы получить список SMTP-адресов для почтового ящика, используйте `Get-Mailbox -Identity user | select emailaddresses | fl`
- Чтобы получить подробные сведения о состоянии доступа устройства, используйте команду `Get-CASMailbox <upn> | fl`.

## <a name="review-the-connector-configuration"></a>Проверка конфигурации соединителя

Ознакомьтесь с [требованиями локального соединителя Exchange](exchange-connector-install.md#intune-exchange-connector-requirements) , чтобы убедиться, что среда и соединитель настроены правильно. 

### <a name="general-considerations-for-the-connector"></a>Общие рекомендации для соединителя

- Убедитесь, что брандмауэр и прокси-серверы разрешают обмен данными между сервером, на котором размещается соединитель Intune Exchange, и службой Intune.

- Компьютер, на котором размещается соединитель Intune Exchange, и сервер клиентского доступа Exchange (CAS) должны быть присоединены к домену и находиться в одной локальной сети. Убедитесь, что для учетной записи, используемой соединителем Exchange Intune, добавлены необходимые разрешения.

- Учетная запись уведомления используется для получения параметров *автообнаружения* . Дополнительные сведения о Аутодисовер в Exchange см. в разделе [Служба автообнаружения в Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/autodiscover?view=exchserver-2016).

- Соединитель Intune Exchange отправляет запрос к URL-адресу EWS с помощью учетных данных учетной записи уведомления для отправки уведомлений по электронной почте вместе со ссылкой « *Начало работы* » (для регистрации в Intune). Использование ссылки *Get Started* для регистрации является обязательным для устройств Android без-Knox. В противном случае эти устройства будут заблокированы с помощью условного доступа.

### <a name="common-issues-for-connector-configurations"></a>Распространенные проблемы, связанные с конфигурациями соединителей

- **Разрешения учетной записи**: в диалоговом окне "Соединитель Microsoft Intune Exchange" убедитесь, что указана учетная запись пользователя, имеющая соответствующие разрешения на выполнение [необходимых командлетов Exchange в Windows PowerShell](exchange-connector-install.md#exchange-cmdlet-requirements).
- **Сообщения электронной почты с уведомлениями**: Включение уведомлений и указание учетной записи уведомления.
- **Синхронизация сервера клиентского доступа**. при настройке соединителя Exchange укажите центры сертификации с наименьшей задержкой в сети на сервере, на котором размещен соединитель Exchange. Задержка взаимодействия между CAS и соединителем Exchange может привести к задержкам обнаружения устройств, особенно при использовании Exchange Online (цен. категория "Выделенный").
- **Расписание синхронизации**: Пользователь с только что зарегистрированным устройством может испытывать задержки доступа, пока соединитель Exchange синхронизируется с Exchange CAS. Полная синхронизация выполняется один раз в день, а разностная (быстрая) синхронизация — несколько раз в день. Чтобы минимизировать задержки, вы можете [принудительно выполнить быструю или полную синхронизацию вручную](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).

## <a name="next-steps"></a>Дальнейшие шаги
Следующие статьи помогут устранить распространенные проблемы и определенные ошибки.

- [Устранение распространенных проблем с соединителем Exchange Intune](troubleshoot-exchange-connector-common-problems.md).
- [Устранение распространенных ошибок для соединителя Intune Exchange](troubleshoot-exchange-connector-common-errors.md).

Обратитесь за помощью в службу поддержки или в сообщество Intune:

- Ознакомьтесь со [статьей получение поддержки](../fundamentals/get-support.md) для использования консоли Intune для помощи в устранении неполадок, а также о том, как открыть обращение в службу поддержки Майкрософт. 
- Опубликуйте свой вопрос на [Microsoft Intune форумах](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
