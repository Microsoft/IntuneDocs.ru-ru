---
title: Устранение распространенных проблем с соединителем Exchange Intune
titleSuffix: Microsoft Intune
description: Устраните распространенные проблемы с локальным соединителем Microsoft Intune Exchange и устраните их.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: de365312a7d293527c3c83fbbd84ab55de41d530
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547674"
---
# <a name="resolve-common-problems-with-the-intune-exchange-connector"></a>Устранение распространенных проблем с соединителем Exchange Intune
 
Эта статья поможет администратору Intune устранить распространенные проблемы с работой соединителя Intune Exchange.

Прежде чем начать устранение неполадок, ознакомьтесь со статьей [Устранение неполадок локального соединителя Exchange Intune](troubleshoot-exchange-connector.md) , чтобы получить основные сведения о соединителе. Также ознакомьтесь с общими проблемами для конфигурации соединителя.

## <a name="an-exchange-activesync-device-isnt-discovered-from-exchange"></a>Устройство Exchange ActiveSync не обнаруживается из Exchange

Если устройство Exchange ActiveSync не обнаруживается из Exchange, [Отслеживайте действие Exchange Connector](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) , чтобы узнать, синхронизирован ли соединитель Exchange с сервером Exchange. Если с момента подключения устройства синхронизация не возникала, собирайте журналы синхронизации и вложите их в запрос на поддержку. При успешном завершении полной синхронизации или быстрой синхронизации с момента соединения устройства проверьте наличие следующих проблем.

- Убедитесь, что у пользователей есть лицензия Intune. В противном случае соединитель Exchange не обнаружит свои устройства.

- Если основной SMTP-адрес пользователя отличается от его имени субъекта-пользователя в Azure Active Directory (Azure AD), то соединитель Exchange не сможет обнаружить устройства для этого пользователя. Для устранения проблемы исправьте основной SMTP-адрес.

- Если в вашей среде используются серверы почтовых ящиков Exchange 2010 и Exchange 2013, рекомендуется нацелить соединитель Exchange на сервер клиентского доступа Exchange 2013 (CAS). Если соединитель Exchange настроен для взаимодействия с сервером клиентского доступа Exchange 2010, соединитель Exchange не сможет обнаружить устройства пользователей в Exchange 2013.

- Для выделенных сред Exchange Online необходимо указывать соединитель Exchange для центров сертификации Exchange 2013 (а не для ЦС Exchange 2010) в выделенной среде во время первоначальной установки. Соединитель будет обмениваться данными только с центрами сертификации Exchange 2013 при выполнении командлетов PowerShell.

## <a name="problems-with-the-notification-email-message"></a>Проблемы с сообщением электронной почты с уведомлением

Чтобы обеспечить условный доступ для локальных почтовых ящиков на устройствах, которые не работают под управлением Android Knox, убедитесь, что регистрация Intune начинается с сообщения электронной почты, которое соединитель Intune Exchange отправляет. Запуск регистрации из сообщения гарантирует, что устройство получает уникальный АктивесинЦид на всех платформах (Exchange, Azure AD, Intune).

Пользователь может не получить уведомление по электронной почте по следующим причинам:

- Учетная запись уведомления настроена неправильно.
- Не удалось выполнить автообнаружение для учетной записи уведомления.
- Не удалось выполнить запрос веб-служб Exchange (EWS) на отправку сообщения электронной почты.

Ознакомьтесь со следующими разделами, чтобы устранить неполадки с уведомлениями по электронной почте.

### <a name="check-the-notification-account-that-retrieves-autodiscover-settings"></a>Проверка учетной записи уведомления, получающей параметры автообнаружения

1. Убедитесь, что служба автоматического обнаружения и веб-службы Exchange настроены в службах клиентского доступа Exchange. Дополнительные сведения см. в разделе [службы клиентского доступа](https://docs.microsoft.com/Exchange/architecture/client-access/client-access) и [Служба автообнаружения в Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).

2. Убедитесь, что ваша учетная запись уведомления соответствует следующим требованиям.

   - Учетная запись содержит активный почтовый ящик, размещенный на локальном сервере Exchange.

   - Имя участника-пользователя учетной записи совпадает с адресом SMTP.

3. Для автообнаружения требуется DNS-сервер с записью DNS для **autodiscover.SMTPdomain.com** (например, autodiscover.contoso.com), указывающей на сервер клиентского доступа Exchange. Чтобы проверить запись, укажите полное доменное имя вместо *autodiscover.SMTPdomain.com* и выполните следующие действия.

   1. В командной строке введите *nslookup*.

   2. Введите *autodiscover.SMTPdomain.com*. Результат должен выглядеть примерно как на следующем изображении: ![Результаты Nslookup](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
      )

   Службу автообнаружения можно также протестировать из Интернета по адресу https://testconnectivity.microsoft.com. Или протестируйте его из локального домена с помощью средства Microsoft Connectivity Analyzer. Дополнительные сведения см. в разделе [средство Microsoft Connectivity Analyzer Tool](https://docs.microsoft.com/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)).


### <a name="check-autodiscovery"></a>Проверка автообнаружения

Если не удается выполнить автообнаружение, попробуйте выполнить следующие действия.

1. [Настройте допустимую запись DNS автообнаружения](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)).

2. Жестко закодировать URL-адрес EWS в файле конфигурации соединителя Intune Exchange:

   1. Определите URL-адрес EWS. URL-адрес EWS по умолчанию для Exchange — `https://<mailServerFQDN>/ews/exchange.asmx`, но URL-адрес может отличаться. Обратитесь к администратору Exchange, чтобы проверить правильный URL-адрес вашей среды.

   2. Откройте для редактирования файл *OnPremisesExchangeConnectorServiceConfiguration.xml*. По умолчанию файл расположен в *соединителе Exchange%Програмдата%\микрософт\виндовс Intune* на компьютере, на котором работает соединитель Exchange. Откройте файл в текстовом редакторе, а затем измените следующую строку в соответствии с URL-адресом EWS для вашей среды: `<ExchangeWebServiceURL>https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`

3. Сохраните файл, а затем перезагрузите компьютер или перезапустите службу соединителя Exchange Microsoft Intune.

>[!NOTE]
> В этой конфигурации соединитель Intune Exchange останавливается с помощью автообнаружения, а подключается напрямую к URL-адресу EWS.

## <a name="next-steps"></a>Дальнейшие шаги

Чтобы получить справку по конкретным ошибкам, попробуйте [устранить распространенные ошибки соединителя Intune Exchange](troubleshoot-exchange-connector-common-errors.md).

Чтобы получить поддержку или получить помощь из сообщества Intune:

- См. раздел [Получение поддержки](../fundamentals/get-support.md) для использования консоли Intune для устранения неполадок или открытия обращения в службу поддержки Майкрософт.
- Опубликуйте свой вопрос на [Microsoft Intune форумах](https://social.technet.microsoft.com/Forums/home?forum=microsoftintuneprod).