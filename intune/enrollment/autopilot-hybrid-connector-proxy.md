---
title: Настройка параметров прокси-сервера для соединителя Intune для Active Directory
description: В этой статье описывается настройка соединителя Intune для Active Directory для работы с имеющимися локальными прокси-серверами.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 529bf4cbf3658d492776afc0433926d85535b1f8
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723363"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Работа с имеющимися локальными прокси-серверами

В этой статье описывается, как настроить соединитель Intune для Active Directory для работы с исходящими прокси-серверами. Она предназначена для клиентов, имеющих в своей сетевой среде прокси-серверы.

Дополнительные сведения о работе соединителей см. в разделе [Сведения о соединителях Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Обход исходящих прокси-серверов

Соединители содержат базовые компоненты ОС, которые отправляют исходящие запросы. Эти компоненты пытаются автоматически обнаружить в сети прокси-сервер при помощи автообнаружения веб-прокси (WPAD).

Компоненты ОС попытаться обнаружить прокси-сервер, выполняя поиск в DNS по имени wpad.domainsuffix. Если DNS разрешает запрос, то затем выполняется HTTP-запрос на IP-адрес для wpad.dat. Этот запрос становится сценарием конфигурации прокси-сервера в вашей среде. Соединитель использует этот сценарий для выбора исходящего прокси-сервера. Тем не менее трафик соединителя по-прежнему может не проходить из-за дополнительных параметров конфигурации, необходимых для прокси-сервера.

Можно настроить соединитель для обхода вашего локального прокси-сервера, чтобы убедиться, что он использует прямое подключение к службам Azure. Это рекомендуемый подход в случае, если это допускает ваша сетевая политика, поскольку это сократит количество настроек, которые необходимо поддерживать.

Чтобы отключить в соединителе использование исходящего прокси-сервера, измените файл :\Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config и добавьте адрес и порт прокси-сервера в раздел, показанный в следующем примере кода:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```

Для того чтобы служба средства обновления соединителей также обходила прокси-сервер, сделайте аналогичные изменения в файле C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Обязательно сделайте копии исходных файлов на случай, если вам понадобится вернуться к файлам конфигурации по умолчанию.

После внесения изменений в файл конфигурации необходимо перезапустить службу соединителя Intune. 

1. Откройте **services.msc**.
2. Найдите и выберите **Служба соединителя ODJ Intune**.
3. Выберите **Перезапуск**.

![Снимок экрана: перезапуск службы](./media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Дальнейшие шаги

[Управление вашими устройствами](../remote-actions/device-management.md)