---
title: Пользовательские параметры Microsoft Intune для устройств с Windows Holographic for Business
titlesuffix: ''
description: Здесь приведены сведения о параметрах, доступных в пользовательском профиле Windows Holographic for Business.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5cdba24c10b90756d9a2b9f08fd7d4dcd727303
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Настраиваемые параметры в Microsoft Intune для устройств под управлением Windows Holographic for Business в Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Пользовательский** профиль Microsoft Intune для Windows Holographic for Business позволяет развертывать параметры универсального кода ресурса Open Mobile Alliance (OMA-URI) для управления функциями устройств. Windows Holographic for Business открывает доступ ко множеству параметров поставщиков служб конфигурации (CSP). Обзор CSP см. в разделе [Введение в поставщики служб конфигурации (CSP) для ИТ-специалистов](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Также см. [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Если вам нужен какой-то конкретный параметр, не забывайте, что [профиль ограничения устройств с Windows Holographic for Business](device-restrictions-windows-holographic.md) содержит множество встроенных параметров и не требует указывать ваши собственные значения.

1. Для начала выполните инструкции из статьи [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Как настроить пользовательские параметры устройств в Microsoft Intune).
2. В колонке **Создать профиль** выберите **Параметры**, чтобы добавить один или несколько параметров OMA URI.
3. В колонке **Настраиваемые параметры OMA URI** выберите **Добавить**, чтобы добавить новое значение. Можно также щелкнуть **Экспорт**, чтобы создать список всех настроенных значений в файле с разделителями-запятыми (CSV).
4. Для каждого добавляемого параметра OMA-URI укажите следующее:
    - **Имя параметра** — введите уникальное имя для параметра OMA-URI, чтобы его было проще найти в списке параметров.
    - **Описание параметра** — введите необязательное описание параметра.
    - **Тип данных** — выберите одно из значений:
        - **Строка**
        - **Строка (XML)**
        - **Дата и время**
        - **Целое число**
        - **Число с плавающей запятой**
        - **Логическое значение**
    - **OMA-URI (с учетом регистра)** — задайте OMA-URI, для которого необходимо указать параметр.
    - **Значение** — укажите значение, которое требуется сопоставить с заданным OMA-URI.
1. По завершении вернитесь в колонку **Создать профиль** и щелкните **Создать**.
Созданный профиль отобразится в списке профилей.

## <a name="recommended-custom-settings"></a>Рекомендованные пользовательские параметры

Следующие параметры также применимы к устройствам с Windows Holographic for Business.


|Имя параметра|OMA-URI|Тип данных  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Целое число<br>0 — запрещено<br>1 — разрешено (по умолчанию)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Целое число<br>0 — запрещено<br>1 — разрешено (по умолчанию)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Целое число<br>0 — обновление службы запрещено <br>1 — обновление службы разрешено (по умолчанию).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Строка<br>URL-адрес — устройство будет проверять наличие обновлений на сервере WSUS по указанному URL-адресу.<br>Не настроено — устройство будет проверять наличие обновлений в центре обновления Майкрософт.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Целое число<br>0 — не настроено. Устройство устанавливает все доступные обновления.<br>1 — устройство устанавливает только обновления, которые применимы и при этом находятся в списке разрешенных обновлений. Установите значение 1 для этой политики, если отдел ИТ хочет контролировать развертывание обновлений на устройствах, например, когда требуется предварительное тестирование.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Важно**<br>Необходимо прочитать и принять лицензионные соглашения обновлений от имени конечных пользователей. Несоблюдение этого правила является нарушением юридических или договорных обязательств.|Узел для утверждения обновлений и принятия лицензионного соглашения от имени конечного пользователя.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Важно**<br>В статье о поставщике служб конфигурации AppLocker содержатся примеры с экранированным языком XML. Для настройки этих параметров в пользовательских профилях Intune необходимо использовать обычный XML.|Строка<br>Дополнительные сведения см. в статье [Поставщик служб конфигурации AppLocker](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).

## <a name="how-to-find-the-policies-you-can-configure"></a>Как найти настраиваемые политики

Полный список поставщиков служб конфигурации (CSP), поддерживаемых Windows Holographic, приведен в разделе [Поставщики служб конфигурации, поддерживаемые в Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Некоторые параметры не совместимы с некоторыми версиями Windows Holographic. Таблица в статье Windows содержит сведения о том, какие версии поддерживаются для каждого поставщика служб конфигурации (CSP).

Кроме того, Intune поддерживает не все параметры, перечисленные в этой статье. Чтобы узнать, поддерживает ли Intune необходимый параметр, откройте соответствующую статью для этого параметра. На странице каждого параметра отображаются сведения о поддерживаемых операциях. Для работы с Intune параметр должен поддерживать операции **добавления** или **замены**.
