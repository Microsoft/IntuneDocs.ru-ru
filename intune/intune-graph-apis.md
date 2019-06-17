---
title: Доступ к интерфейсам API Intune в Microsoft Graph с использованием Azure AD
titleSuffix: Microsoft Intune
description: В этом разделе описывается порядок доступа к интерфейсам API Intune в Microsoft Graph с использованием Azure AD.
keywords: intune graphapi c# powershell роли разрешений
author: dougeby
manager: dougeby
ms.author: dougeby
ms.date: 03/08/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4d838d0cd0d0f92cb344592d18d9e04e18d7e456
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819741"
---
# <a name="how-to-use-azure-ad-to-access-the-intune-apis-in-microsoft-graph"></a>Доступ к интерфейсам API Intune в Microsoft Graph с использованием Azure AD

[API Microsoft Graph](https://developer.microsoft.com/graph/) теперь поддерживает службу Microsoft Intune с соответствующими API и ролями разрешений.  API Microsoft Graph использует Azure Active Directory (Azure AD) для проверки подлинности и управления доступом.  
Для доступа к интерфейсам API Intune в Microsoft Graph требуется следующее:

- Идентификатор приложения со следующими характеристиками:

    - Разрешение на вызов Azure AD и интерфейсов Microsoft API Graph.
    - Области разрешений, соответствующие задачам конкретного приложения.

- Учетные данные пользователя со следующими характеристиками:

    - Разрешение на доступ к клиенту Azure AD, связанному с приложением.
    - Разрешения ролей, необходимые для поддержки областей разрешений приложения.

- Конечный пользователь предоставляет приложению разрешение на выполнение задач приложения для своего клиента Azure.

В этой статье:

- Демонстрируется порядок регистрации приложения с доступом к API Microsoft Graph и соответствующими ролями разрешений.

- Описываются роли разрешений API Intune.

- Приводятся образцы проверки подлинности API Intune для C# и PowerShell.

- Описывается структура поддержки нескольких клиентов.

Дополнительные сведения см. в следующих ресурсах:

- [Разрешение доступа к веб-приложениям с помощью OAuth 2.0 и Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [Общие сведения о проверке подлинности Azure AD](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [Интеграция приложений с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [Общие сведения об OAuth 2.0](https://oauth.net/2/)

## <a name="register-apps-to-use-the-microsoft-graph-api"></a>Регистрация приложений для использования API Microsoft Graph

Чтобы зарегистрировать приложение для использования API Microsoft Graph, выполните указанные ниже действия.

1.  Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) в качестве администратора.

    При необходимости вы можете использовать следующие учетные записи:
    - Учетная запись администратора клиента.
    - Учетная запись пользователя клиента с включенным параметром **Пользователи могут регистрировать приложения**.

2.  В меню выберите **Azure Active Directory** &gt; **Регистрация приложений**.

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  Щелкните **Регистрация нового приложения** для создания нового приложения или выберите существующее приложение.  (Если выбрано существующее приложение, пропустите следующий шаг.)

4.  В колонке **Создать** укажите следующие сведения:

    1.  **Имя** приложения (отображается при входе пользователей в систему).

    2.  Значения в полях **Тип приложения** и **URI перенаправления**.

        Эти значения задаются в соответствии с требованиями. Например, если вы используете [библиотеку проверки подлинности](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) Azure AD (ADAL), укажите в поле **Тип приложения** значение `Native`, а в поле **URI перенаправления** значение `urn:ietf:wg:oauth:2.0:oob`.

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        Дополнительные сведения см. в статье [Сценарии проверки подлинности в Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

5.  В колонке приложения выполните следующие действия:

    1.  Запишите значение в поле **Идентификатор приложения**.

    2.  Выберите **Параметры** &gt; **Доступ к API** &gt; **Необходимые разрешения**.

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  В колонке **Необходимые разрешения** выберите **Добавить** &gt; **Добавить доступ через API** &gt; **Выбор API**.

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  В колонке **Выбор API** щелкните **Microsoft Graph** &gt; **Выбрать**.  Откроется колонка **Разрешить доступ** со списком областей разрешений, доступных для вашего приложения.

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    Выберите роли, необходимые для приложения, с помощью соответствующих флажков слева от их названий.  Дополнительные сведения о конкретных областях разрешений Intune см. в статье [Области разрешений Intune](#intune-permission-scopes).  Дополнительные сведения о других областях разрешений API Graph см. в статье [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).

    В целях оптимизации рекомендуется выбирать минимальное число ролей, необходимых для реализации вашего приложения.

    По завершении настройки щелкните **Выбрать** и **Готово**, чтобы сохранить изменения.

На этом этапе можно также выполнить следующие действия:

- Предоставьте всем учетным записям клиента разрешения на использование приложения без ввода учетных данных.  

    Для этого выберите **Предоставить разрешения** и подтвердите свои действия в появившемся окне запроса.

    При первом запуске приложения появится запрос на предоставление ему разрешений на выполнение выбранных ролей.

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- Предоставьте доступ к вашему приложению пользователям за пределами клиента.  (Как правило, это требуется только для партнеров, поддерживающих несколько клиентов или организаций.)  

    Для этого выполните следующие действия.

  1. Выберите **Манифест** в колонке приложения. Откроется колонка **Изменение манифеста**.

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. Измените значение параметра `availableToOtherTenants` на `true`.

  3. Сохраните внесенные изменения.

## <a name="intune-permission-scopes"></a>Области разрешений Intune

Azure AD и Microsoft Graph используют области разрешений для управления доступом к корпоративным ресурсам.  

Области разрешений также называются _областями OAuth_ и позволяют контролировать доступ к определенным сущностям Intune и их свойствам. В этом разделе обобщаются области разрешений для функций API Intune.

Дополнительные сведения:
- [Проверка подлинности Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [Области разрешений приложения](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

Предоставляя разрешения на доступ к Microsoft Graph, вы можете указать следующие области управления доступом к Intune, которые будут определяться приведенными ниже областями разрешений API Intune.  В первом столбце приводится имя функции, которое отображается на портале Azure, а во втором — имя соответствующей области разрешений.

Значение параметра _Разрешить доступ_ | Имя области
:--|:--
__Выполнение удаленных действий, затрагивающих пользователей, на устройствах Microsoft Intune__ | [DeviceManagementManagedDevices.PrivilegedOperations.All](#mgd-po)
__Чтение и запись устройств Microsoft Intune__ | [DeviceManagementManagedDevices.ReadWrite.All](#mgd-rw)
__Чтение устройств Microsoft Intune__ | [DeviceManagementManagedDevices.Read.All](#mgd-ro)
__Чтение и запись параметров управления доступом на основе ролей Microsoft Intune__ | [DeviceManagementRBAC.ReadWrite.All](#rac-rw)
__Чтение параметров управления доступом на основе ролей Microsoft Intune__ | DeviceManagementRBAC.Read.All
__Чтение и запись приложений Microsoft Intune__ | [DeviceManagementApps.ReadWrite.All](#app-rw)
__Чтение приложений Microsoft Intune__ | [DeviceManagementApps.Read.All](#app-ro)
__Чтение и запись конфигурации и политик устройств Microsoft Intune__ | DeviceManagementConfiguration.ReadWrite.All
__Чтение конфигурации и политик устройств Microsoft Intune__ | [DeviceManagementConfiguration.Read.All](#cfg-ro)
__Чтение и запись конфигурации Microsoft Intune__ | [DeviceManagementServiceConfig.ReadWrite.All](#svc-rw)
__Чтение конфигурации Microsoft Intune__ | DeviceManagementServiceConfig.Read.All

Эта таблица содержит параметры, отображаемые на портале Azure. В следующих разделах области описываются в алфавитном порядке.

На данный момент для всех областей разрешений Intune требуется доступ с правами администратора.  Это означает, что при выполнении приложений и скриптов, запрашивающих доступ к ресурсам API Intune, вам потребуются соответствующие учетные данные.

### <a name="app-ro"></a>DeviceManagementApps.Read.All

- Значение параметра **Разрешить доступ**: __Чтение приложений Microsoft Intune__

- Разрешает доступ с правами на чтение к свойствам и сведениям о состоянии следующих сущностей:
    - Клиентские приложения
    - Категории мобильных приложений
    - Политики защиты приложений
    - Конфигурации приложений

### <a name="app-rw"></a>DeviceManagementApps.ReadWrite.All

- Значение параметра **Разрешить доступ**: __Чтение и запись приложений Microsoft Intune__

- Разрешает те же операции, что и область __DeviceManagementApps.Read.All__

- Также позволяет вносить изменения в следующие сущности:

    - Клиентские приложения
    - Категории мобильных приложений
    - Политики защиты приложений
    - Конфигурации приложений

### <a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All

- Значение параметра **Разрешить доступ**: __Чтение конфигурации и политик устройств Microsoft Intune__

- Разрешает доступ с правами на чтение к свойствам и сведениям о состоянии следующих сущностей:
    - Конфигурация устройства
    - Политика соответствия устройств
    - Уведомления

### <a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All

- Значение параметра **Разрешить доступ**: __Чтение и запись конфигурации и политик устройств Microsoft Intune__

- Разрешает те же операции, что и область __DeviceManagementConfiguration.Read.All__

- Приложения также могут создавать, назначать, удалять и изменять следующие сущности:
    - Конфигурация устройства
    - Политика соответствия устройств
    - Уведомления

### <a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All

- Значение параметра **Разрешить доступ**: __Выполнение удаленных действий, затрагивающих пользователей, на устройствах Microsoft Intune__

- Разрешает выполнение следующих удаленных действий на управляемом устройстве:
    - Прекратить использование
    - Очистка
    - Сбросить и восстановить секретный код
    - Удаленная блокировка
    - Включить и отключить режим пропажи
    - Очистить компьютер
    - Перезагрузить
    - Удалить пользователя с общего устройства

### <a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All

- Значение параметра **Разрешить доступ**: __Чтение устройств Microsoft Intune__

- Разрешает доступ с правами на чтение к свойствам и сведениям о состоянии следующих сущностей:
    - Управляемое устройство
    - Категория устройств
    - Обнаруженное приложение
    - Удаленные действия
    - Сведения о вредоносных программах

### <a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All

- Значение параметра **Разрешить доступ**: __Чтение и запись устройств Microsoft Intune__

- Разрешает те же операции, что и область __DeviceManagementManagedDevices.Read.All__

- Приложения также могут создавать, удалять и изменять следующие сущности:
    - Управляемое устройство
    - Категория устройств

- Также разрешаются следующие удаленные действия:
    - Найти устройства
    - Обход блокировки активации
    - Запрос удаленной помощи

### <a name="rac-ro"></a>DeviceManagementRBAC.Read.All

- Значение параметра **Разрешить доступ**: __Чтение параметров управления доступом на основе ролей Microsoft Intune__

- Разрешает доступ с правами на чтение к свойствам и сведениям о состоянии следующих сущностей:
    - Назначение ролей
    - Определения ролей
    - Операции с ресурсами

### <a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All

- Значение параметра **Разрешить доступ**: __Чтение и запись параметров управления доступом на основе ролей Microsoft Intune__

- Разрешает те же операции, что и область __DeviceManagementRBAC.Read.All__

- Приложения также могут создавать, назначать, удалять и изменять следующие сущности:
    - Назначение ролей
    - Определения ролей

### <a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All

- Значение параметра **Разрешить доступ**: __Чтение конфигурации Microsoft Intune__

- Разрешает доступ с правами на чтение к свойствам и сведениям о состоянии следующих сущностей:
    - Регистрация устройств
    - Сертификат push-уведомлений Apple
    - программа регистрации устройств Apple;
    - Apple Volume Purchase Program
    - Соединитель Exchange
    - Условия
    - Управление затратами на телекоммуникации
    - Облачная инфраструктура открытых ключей
    - Branding
    - Mobile Threat Defense

### <a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All

- Значение параметра **Разрешить доступ**: __Чтение и запись конфигурации Microsoft Intune__

- Разрешает те же операции, что и область DeviceManagementServiceConfig.Read.All_

- Приложения также могут настраивать следующие функции Intune:
    - Регистрация устройств
    - Сертификат push-уведомлений Apple
    - программа регистрации устройств Apple;
    - Apple Volume Purchase Program
    - Соединитель Exchange
    - Условия
    - Управление затратами на телекоммуникации
    - Облачная инфраструктура открытых ключей
    - Branding
    - Mobile Threat Defense

## <a name="azure-ad-authentication-examples"></a>Образцы библиотеки проверки подлинности Azure AD

В этом разделе показано, как встраивать Azure AD в проекты C# и PowerShell.

В каждом образце необходимо указывать идентификатор приложения, которому назначена область разрешений не ниже `DeviceManagementManagedDevices.Read.All` (см. выше).

При тестировании любого образца могут появляться ошибки с кодом состояния HTTP 403 (запрещено) следующего вида:

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

В этом случае убедитесь, что выполняются следующие требования:

- Вы указали новый идентификатор приложения с разрешениями на использование API Microsoft Graph и областью разрешений `DeviceManagementManagedDevices.Read.All`.

- Ваши учетные данные клиента поддерживают функции администратора.

- Ваш код похож на приведенные образцы.


### <a name="authenticate-azure-ad-in-c"></a>Проверка подлинности Azure AD в C\#

В этом образце для C# демонстрируется, как извлечь список устройств, связанных с вашей учетной записью Intune.

1.  Запустите Visual Studio и создайте новый проект консольного приложения Visual C# (.NET Framework).

2.  Введите имя проекта и другие необходимые сведения.

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  С помощью обозревателя решений добавьте в проект пакет Microsoft ADAL NuGet.

    1.  Щелкните правой кнопкой мыши в обозревателе решений.
    2.  Выберите **Управление пакетами NuGet…** &gt; **Обзор**.
    3.  Затем выберите `Microsoft.IdentityModel.Clients.ActiveDirectory` и нажмите **Установить**.

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  Добавьте следующие операторы в начало файла **Program.cs**:

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  Добавьте метод для создания заголовка авторизации:

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    Не забудьте заменить значение `application_ID` на идентификатор, которому назначена область разрешений не ниже `DeviceManagementManagedDevices.Read.All` (см. выше).

6. Добавьте метод для извлечения списка устройств:

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  Добавьте в процедуру **Main** вызов метода **GetMyManagedDevices**:

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  Скомпилируйте и запустите программу.  

При первом запуске программы должны появиться два запроса.  В первом запрашиваются ваши учетные данные, а во втором предоставляются разрешения для запроса `managedDevices`.  

Ниже приведен полный текст программы для справки:

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a>Проверка подлинности Azure AD (PowerShell)

В следующем скрипте PowerShell для проверки подлинности используется модуль AzureAD PowerShell.  Дополнительные сведения см. в статьях [Azure Active Directory PowerShell, версия 2](https://docs.microsoft.com/powershell/azure/install-adv2?view=azureadps-2.0) и [Образцы PowerShell для Intune](https://github.com/microsoftgraph/powershell-intune-samples).

В этом примере укажите соответствующий идентификатор приложения в значении параметра `$clientID`.

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a>Поддержка нескольких клиентов и партнеров

Если ваша организация поддерживает организации с собственными клиентами Azure AD, вы можете разрешить своим клиентам использовать приложения с соответствующими клиентами.

Для этого:

1.  Убедитесь, что в целевом клиенте Azure AD существует необходимая учетная запись клиента.

2.  Убедитесь, что в учетной записи клиента пользователям разрешено регистрировать приложения (см. раздел **Параметры пользователей**).

3.  Установите отношения между каждым клиентом.  

    Для этого выполните любое из следующих действий:

    a. С помощью [Центра партнеров Майкрософт](https://partnercenter.microsoft.com/) определите отношение между своим клиентом и соответствующим адресом электронной почты.

    b. Пригласите пользователя в качестве гостя клиента.

Чтобы пригласить пользователя в качестве гостя клиента, выполните следующие действия:

1.  Выберите **Добавить гостевого пользователя** на панели **Быстрые задачи**.

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  Введите адрес электронной почты клиента и при необходимости настраиваемый текст приглашения.

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  Выберите **Пригласить**.

Приглашение будет отправлено пользователю.

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   Чтобы принять ваше приглашение, пользователю необходимо щелкнуть ссылку **Начало работы**.

После того как отношение установлено (или ваше приглашение принято), добавьте учетную запись пользователя в **роль каталога**.

При необходимости добавьте пользователя в другие роли. Например, если пользователям требуются разрешения на управление параметрами Intune, им необходимо назначить роль **Глобальный администратор** или **Администратор службы Intune**.

Кроме того:

- С помощью портала https://admin.microsoft.com назначьте лицензию Intune учетной записи пользователя.

- Обновите код приложения таким образом, чтобы реализовать проверку подлинности в домене клиента Azure AD соответствующего клиента, а не в вашем собственном.

    Например, если ваш домен клиента выглядит как `contosopartner.onmicrosoft.com`, а домен клиента вашего клиента — как `northwind.onmicrosoft.com`, следует обновить код, чтобы реализовать проверку подлинности в домене клиента вашего клиента.

    Для этого в приложении C# из предыдущего образца следует изменить значение переменной `authority`:

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    значение

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
