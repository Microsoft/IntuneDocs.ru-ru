---
title: Аутентификация в хранилище данных, предназначенная только для приложений
titleSuffix: Microsoft Intune
description: В этой статье рассматривается проверка подлинности в хранилище данных, предназначенная только для приложений.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d7166563-6bb5-4624-b8c8-6b300a997c3a
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e926d3d9e9dfbf6025fb36fd54e64f28b662fc89
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2018
---
# <a name="intune-data-warehouse-application-only-authentication"></a>Аутентификация в хранилище данных, предназначенная только для приложений

Вы можете настроить приложение с помощью Azure Active Directory (Azure AD) и выполнить аутентификацию в хранилище данных Intune. Этот процесс целесообразно использовать для веб-сайтов, приложений и фоновых процессов, в которых приложения не должны иметь доступ к учетным данным пользователя. Выполнив следующие шаги, вы авторизуете свое приложение в Azure AD с помощью OAuth 2.0.

## <a name="authorization"></a>Авторизация

Azure Active Directory (Azure AD) использует OAuth 2.0, чтобы предоставить возможность санкционировать доступ к веб-приложениям и веб-API в клиенте Azure AD. В этом руководстве показано, как выполнить аутентификацию приложения с помощью C#. Поток кода аутентификации OAuth 2.0 описан в разделе 4.1 спецификации OAuth 2.0. Дополнительные сведения см. в разделе [Разрешение доступа к веб-приложениям с помощью OAuth 2.0 и Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).


## <a name="azure-keyvault"></a>Azure Key Vault

В следующем процессе используется частный метод для обработки и преобразования ключа приложения. Этому частному методу присвоено имя SecureString. В качестве альтернативы для хранения ключа приложения можно использовать Azure Key Vault. Дополнительные сведения см. в описании [Key Vault](https://azure.microsoft.com/services/key-vault/).

## <a name="create-a-web-app"></a>Создание веб-приложения

В этом разделе вы введете сведения о веб-приложении, которое нужно указать в Intune. Веб-приложение — это приложение на основе архитектуры "клиент-сервер". Сервер предоставляет веб-приложение, включая его пользовательский интерфейс, содержимое и функциональные возможности. Приложение такого типа размещается в Интернете. С помощью Intune вы предоставите веб-приложению доступ к Intune. Поток данных инициирует веб-приложение. 

1.  Войдите на [портал Azure](https://portal.azure.com).
2.  Воспользуйтесь полем **Поиск ресурсов, служб и документов** в верхней части портала Azure, чтобы найти **Azure Active Directory**.
3.  В раскрывающемся меню выберите **Azure Active Directory** в разделе **Службы**.
4.  Выберите **Регистрация приложений**.
5.  Щелкните **Регистрация нового приложения** для отображения колонки **Создание**.
6.  В колонке **Создание** укажите сведения о своем приложении.

    - Имя приложения, например *Intune App-Only Auth*.
    - Выберите **тип приложения**. Выберите **Веб-приложение или API**, чтобы добавить приложение, представляющее веб-приложение, веб-API или и то, и другое.
    - **URL-адрес для входа** для приложения. Это расположение, к которому пользователи переходят автоматически во время аутентификации. Пользователи должны подтвердить свою личность. Дополнительные сведения см. в статье [Что такое доступ к приложениям и единый вход с помощью Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

7.  Щелкните **Создать** в нижней части колонки **Создание**.

    >[!NOTE] 
    > Скопируйте **идентификатор приложения** в колонке **Зарегистрированное приложение** для последующего использования.

## <a name="create-a-key"></a>Создание ключа

В этом разделе Azure AD создаст значение ключа для приложения.

1.  В колонке **Регистрация приложений** выберите только что созданное приложение, чтобы отобразилась колонка приложения.
2.  Выберите **Параметры** в верхней части колонки для отображения колонки **Параметры**.
3.  В колонке **Параметры** выберите **Ключи**.
4.  Введите **описание** ключа, длительность **срока действия** и **значение** ключа.
5.  Нажмите кнопку **Сохранить**, чтобы сохранить и обновить ключи приложения.
6.  Вам нужно скопировать сгенерированное значение ключа (в кодировке Base64).

    >[!NOTE] 
    > Это значение исчезнет, когда вы закроете колонку **Ключи**. Позже вы не сможете получить ключ из этой колонки. Скопируйте его, чтобы использовать в дальнейшем.

## <a name="grant-application-permissions"></a>Предоставление разрешений приложению

В этом разделе вы предоставите разрешения для приложений.

1.  В колонке **Параметры** выберите **Необходимые разрешения**.
2.  Нажмите кнопку **Добавить**.
3.  Выберите **Добавить API** для отображения колонки **Выбор API**.
4.  В колонке **Выбор API** выберите **Microsoft Intune API (MicrosoftIntuneAPI)** и нажмите кнопку **Выбрать**. После этого вы перейдете на шаг **Выбор разрешений** и отобразится колонка **Разрешить доступ**.
5.  В разделе **Разрешения приложений** выберите параметр **Получать сведения о хранилище данных из Microsoft Intune**.
6.  Нажмите кнопку **Выбрать** в колонке **Разрешить доступ**.
7.  В колонке **Добавить доступ через API** нажмите кнопку **Готово**.
8.  В колонке **Необходимые разрешения** щелкните **Предоставить разрешения** и щелкните **Да** при появлении запроса на обновление всех существующих разрешений для этого приложения.

## <a name="generate-token"></a>Создание токена

С помощью Visual Studio создайте проект консольного приложения (.NET Framework), который поддерживает .NET Framework и использует C# в качестве языка программирования.

1.  Последовательно выберите **Файл** > **Создать** > **Проект**, чтобы отобразилось диалоговое окно **Создание проекта**.
2.  В левой части окна выберите **Visual C#**, чтобы отобразились все проекты .NET Framework.
3.  Выберите **Консольное приложение (.NET Framework)**, добавьте имя приложения и нажмите кнопку **ОК**, чтобы создать приложение.
4.  В **обозревателе решений** выберите **Program.cs** для отображения кода.
5.  В контекстном меню выберите пункты **Добавить** > **Новый элемент**. Появится диалоговое окно **Добавление нового элемента**.
6.  В левой части окна в разделе **Visual C#** выберите **Код**.
7.  Выберите **Класс**, измените имя класса на *IntuneDataWarehouseClass.cs* и нажмите кнопку **Добавить**.
8.  Добавьте в метод <code>Main</code> следующий код:

    ``` csharp
         var applicationId = ConfigurationManager.AppSettings["appId"].ToString();
         SecureString applicationSecret = ConvertToSecureStr(ConfigurationManager.AppSettings["appKey"].ToString()); // Load as SecureString from configuration file or secret store (i.e. Azure KeyVault)
         var tenantDomain = ConfigurationManager.AppSettings["tenantDomain"].ToString();
         var adalContext = new AuthenticationContext($"https://login.windows.net/" + tenantDomain + "/oauth2/token");
    
         AuthenticationResult authResult = adalContext.AcquireTokenAsync(
             resource: "https://api.manage.microsoft.com/",
             clientCredential: new ClientCredential(
                 applicationId,
                 new SecureClientSecret(applicationSecret))).Result;
    ``` 

9. Добавьте пространства имен, вставив следующий код в верхней части файла кода:

    ``` csharp
     using System.Security;
     using Microsoft.IdentityModel.Clients.ActiveDirectory;
     using System.Configuration;
    ``` 

10. После метода <code>Main</code> добавьте следующий частный метод для обработки и преобразования ключа приложения:

    ``` csharp
    private static SecureString ConvertToSecureStr(string appkey)
    {
        if (appkey == null)
            throw new ArgumentNullException("AppKey must not be null.");
    
        var secureAppKey = new SecureString();
    
        foreach (char c in appkey)
            secureAppKey.AppendChar(c);
    
        secureAppKey.MakeReadOnly();
        return secureAppKey;
    }
    ```

11. В **обозревателе решений** щелкните правой кнопкой мыши **Ссылки**, а затем выберите **Управление пакетами NuGet**.
12. Выполните поиск по фразе *Microsoft.IdentityModel.Clients.ActiveDirectory* и установите соответствующий пакет Microsoft NuGet.
13. В **обозревателе решений** выберите и откройте файл *App.config*.
14. Добавьте раздел <code>appSettings</code>, чтобы XML-документ выглядел следующим образом:

    ``` xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup> 
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <appSettings>
          <add key="appId" value="App ID created from 'Create a Web App' procedure"/>
          <add key="appKey" value="Key created from 'Create a key' procedure" />
          <add key="tenantDomain" value="contoso.onmicrosoft.com"/>
        </appSettings>
    </configuration>
    ``` 

15. Обновите значения <code>appId</code>, <code>appKey</code> и <code>tenantDomain</code> в соответствии со своими уникальными значениями для приложения.
16. Скомпилируйте приложение.

    >[!NOTE] 
    > Дополнительный код реализации см. в [примере кода Intune-Data-Warehouse](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/CSharp ).

## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения об Azure Key Vault см. в статье [Что такое хранилище ключей Azure?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)

