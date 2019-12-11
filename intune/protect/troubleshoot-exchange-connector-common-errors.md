---
title: Устранение распространенных ошибок соединителя Intune Exchange
titleSuffix: Microsoft Intune
description: Диагностика и устранение распространенных ошибок в локальной соединитель Microsoft Intune с Exchange
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
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
ms.openlocfilehash: b30a7e843850d6918abc2e76f84397a1f197516f
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508855"
---
# <a name="resolve-common-errors-for-the-intune-exchange-connector"></a>Устранение распространенных ошибок для соединителя Intune Exchange

Эта статья поможет администратору Intune устранить определенные ошибки и сообщения о работе соединителя Intune Exchange.  

## <a name="configuration-failed-and-returned-error-code-0x0000001"></a>Сбой настройки, возвращен код ошибки 0x0000001

**Проблема.**  
При попытке настроить соединитель Microsoft Intune с Exchange появляется следующее сообщение об ошибке:

```
   The Microsoft Intune Exchange Connector cannot connect to the Microsoft Exchange server.  
   The following Microsoft Exchange Server address could not be reached <Exchange server Name FQDN>  
   Verify that the FQDN of the exchange server address and credentials that you entered is correct and the server is running. The Microsoft Intune Exchange Connector does not support Exchange server arrays.  
   Error code: 0x0000001  
```

Эта проблема может возникать, если параметры прокси-сервера Интернета настроены неправильно.

**Решение**.  
Настройка параметров прокси-сервера:
1. Обратитесь к администратору локальной сети, чтобы убедиться, что параметры прокси-сервера настроены правильно. 
2. Используйте команду **netsh WinHTTP** , чтобы настроить прокси-сервер и добавить необходимый список исключений. Пример.  

   ```
   Netsh winhttp set proxy proxy-server="http=proxy.corp.domain.com" bypass-list"34*.*;134.132.*.*;10.*.*;localhost;*.corp.domain.com;*.staging.domain.com"
   ```

## <a name="configuration-failed-and-returned-error-code-0x000000b"></a>Сбой настройки, возвращен код ошибки 0x000000b   

**Проблема.**  
При попытке настроить соединитель Microsoft Intune с Exchange появляется следующее сообщение об ошибке:  

```
   The Microsoft Intune Exchange Connector experienced an error:  
   CertEnroll::CX509PrivateKey::Create: The system cannot find the file specified. 0x80070002 (WIN32: 2  
   ERROR_FILE_NOT_FOUND  
   Error code: 0x000000b  
```
Эта проблема может возникать, если учетная запись, используемая для входа в Intune, не является учетной записью глобального администратора Intune.

**Решение**.  
Войдите в Intune с помощью учетной записи глобального администратора или добавьте свою учетную запись в глобальную группу администраторов. Дополнительные сведения см. в разделе [Управление доступом на основе ролей (RBAC) с помощью Microsoft Intune](../fundamentals/role-based-access-control.md).

## <a name="configuration-failed-and-returned-error-code-0x0000006"></a>Сбой настройки, возвращен код ошибки 0x0000006

**Проблема.**  
При попытке настроить соединитель Microsoft Intune с Exchange появляется следующее сообщение об ошибке:  

```  
   The Microsoft Intune Exchange Connector cannot connect to Microsoft Intune  
   Verify that you are connected to the Internet, check the Microsoft Intune Service Status, and try to connect again.  
   Error code: 0x00000006  
```  
Эта ошибка может возникать, если прокси-сервер используется для подключения к Интернету и блокирует трафик к службе Intune. Чтобы определить, используется ли прокси-сервер, выберите **Панель управления** > **Свойства обозревателя**, перейдите на вкладку **Подключение** и нажмите кнопку **Параметры локальной сети**.

**Решение**.  

- **Вариант 1** . Удалите параметры прокси-сервера, чтобы разрешить компьютеру подключаться к Интернету, не используя прокси-сервер.  

- **Вариант 2** . Настройте прокси-сервер, чтобы разрешить обмен данными со службой Intune, как описано в статье [требования к соединителю Intune Exchange](exchange-connector-install.md#intune-exchange-connector-requirements).



## <a name="event-7000-or-7041-microsoft-intune-exchange-connector-service-wont-start"></a>Событие 7000 или 7041: служба соединитель Microsoft Intune с Exchange не запускается

**Проблема.**  
Устройство iOS не регистрируется в Intune и создает одно из следующих сообщений об ошибке:  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Task Category: None
   Level:               Error
   Keywords:        Classic
   User:                N/A
   Computer:      <computer>
   Description:
   The Microsoft Intune Exchange Connector Service service failed to start because of the following error:  
   The service did not start because of a logon failure.
```  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Event ID:          7041
   Task Category: None
   Level:               Error   
   Keywords:        Classic
   User:                N/A
   Computer:       <computer>
   Description:
   The WIEC service was unable to log on as .\WIEC_USER with the currently configured password because of the following error:
   Logon failure: the user has not been granted the requested logon type at this computer.
   Service: WIEC
   Domain and account: .\WIEC_USER
   This service account does not have the required user right "Log on as a service."  
```
Эта проблема может возникать, если учетной записи **WIEC_User** не назначено право входа в систему **как службы** в локальной политике.

**Решение**.  
На компьютере, на котором работает соединитель Intune Exchange, назначьте учетной записи службы **WIEC_Userа** право **Вход в качестве службы** . Если компьютер является узлом кластера, убедитесь, что для учетной записи службы кластеров на всех узлах кластера назначено право *входа в качестве службы* .  

Чтобы назначить права пользователя " **Вход в качестве службы** " учетной записи службы **WIEC_User** на компьютере, выполните следующие действия.

1. Войдите в систему с учетной записью администратора или члена группы "Администраторы".
2. Запустите **secpol. msc** , чтобы открыть локальную политику безопасности.
3. Перейдите в раздел **Параметры безопасности** > **Локальные политики**, а затем выберите **Назначение прав пользователя**.
4. На правой панели дважды щелкните **Вход в качестве службы**.
5. Выберите **Добавить пользователя или группу**, добавьте **WIEC_USER** в политику, а затем нажмите кнопку **ОК** два раза.

Если право **входа в качестве пользователя службы** было назначено **WIEC_User** но впоследствии было удалено, обратитесь к администратору домена, чтобы определить, перезапишет ли параметр Групповая политика.  

## <a name="next-steps"></a>Дальнейшие шаги  

Следующие статьи помогут устранить определенные ошибки.
- [Устранение распространенных проблем с соединителем Intune Exchange Connector](troubleshoot-exchange-connector-common-problems.md). git 

Обратитесь за помощью в службу поддержки или в сообщество Intune.
- Ознакомьтесь со [статьей получение поддержки](../fundamentals/get-support.md) для использования консоли Intune для помощи в устранении неполадок, а также о том, как открыть обращение в службу поддержки Майкрософт. 
- Опубликуйте свой вопрос на [Microsoft Intune форумах](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
