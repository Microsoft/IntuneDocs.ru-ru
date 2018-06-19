---
title: Получение данных из API хранилища данных через клиент REST
titlesuffix: Microsoft Intune
description: Получение данных из хранилища данных Intune с помощью RESTful API
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0187555a087f6ca8ab391b839f2c905181c33cb6
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223685"
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Получение данных из API хранилища данных через клиент REST

Для доступа к модели данных для хранилища данных Intune можно использовать конечные точки RESTful. Для получения доступа к данным клиент должен авторизоваться в Microsoft Azure Active Directory (Azure AD) с помощью OAuth 2.0. Чтобы разрешить доступ, сначала следует настроить собственное приложение в Azure и предоставить разрешения API-интерфейсу Microsoft Intune. Локальный клиент проходит авторизацию, после чего он может взаимодействовать с конечными точками хранилища данных через собственное приложение.

Чтобы настроить клиент для получения данных API хранилища данных необходимо пройти следующие этапы:

1. создание клиентского приложения в качестве собственного приложения в Azure;
3. предоставление клиентскому приложению прав доступа к API Microsoft Intune;
3. создание локального клиента REST для получения данных.

Чтобы узнать, как выполнить авторизацию API и получить доступ к нему с помощью клиента REST, выполните указанные ниже действия. Для начала рассмотрим использование универсального клиента REST с помощью Postman. Почтальон — это часто используемое средство для устранения неполадок и разработки клиентов REST для работы с API-интерфейсами. Дополнительные сведения о Postman см. на веб-сайте [Postman](https://www.getpostman.com). После этого вы можете взглянуть на пример кода C#. Это пример для авторизации клиента и получение данных из API.

## <a name="create-a-client-app-as-a-native-app-in-azure"></a>создание клиентского приложения в качестве собственного приложения в Azure;

Создайте собственное приложение в Azure. Это собственное приложение является клиентским приложением. Клиент, запущенный на локальном компьютере, ссылается на API хранилища данных Intune, когда локальный клиент запрашивает учетные данные.

1. Войдите на портал Azure своего клиента. Выберите **Azure Active Directory** > **Регистрации приложений**, чтобы открыть панель **Регистрации приложений**.
2. Выберите элемент **Регистрация нового приложения**.
3. Введите сведения о приложении.
    1.  В поле **Имя**введите понятное имя, например "Intune Data Warehouse Client".
    2.  В поле **Тип приложения** выберите **Собственный**.
    3.  В поле **URL-адрес входа** введите URL-адрес. URL-адрес входа будет зависеть от конкретного сценария, но если вы планируете использовать Postman, введите `https://www.getpostman.com/oauth2/callback`. На этапе проверки подлинности в Azure AD вы будете использовать обратный вызов клиента.
4.  Выберите **Создать**.

     ![API хранилища данных Intune](./media/reports-get_rest_data_client_overview.png)

5. Запомните значение в поле **Идентификатор приложения**. Оно потребуется в следующем разделе.

## <a name="grant-the-client-app-access-to-the-microsoft-intune-api"></a>предоставление клиентскому приложению прав доступа к API Microsoft Intune;

Теперь у вас есть приложение, определенное в Azure. Предоставьте доступ из собственного приложения к API Microsoft Intune.

1.  Выберите собственное приложение. Вы назвали приложение **Intune Data Warehouse Client**.
2.  На панели **Параметры** выберите **Необходимые разрешения**
3.  Нажмите кнопку **Добавить** на панели **Необходимые разрешения**.
4.  Выберите элемент **Выбор API**.
5.  Найдите имя веб-приложения. Приложение называется **Microsoft Intune API**.
6.  Выберите приложение в списке.
7.  Нажмите кнопку **Выбрать**.
8.  Установите флажок **Делегированные разрешения**, чтобы добавить параметр **Получать сведения о хранилище данных из Microsoft Intune**.

    ![Включить доступ — API Microsot Intune](./media/reports-get_rest_data_client_access.png)

9.  Нажмите кнопку **Выбрать**.
10.  Нажмите кнопку **Готово**.
11.  При необходимости выберите элемент **Предоставить разрешения** на панели "Необходимые разрешения". Это позволит предоставить доступ ко всем учетным записям в текущем каталоге. Кроме того, диалоговое окно согласия не будет отображаться для каждого пользователя в клиенте. Дополнительные сведения см. в статье [Интеграция приложений с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
12.  Выберите **Да**.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Получение данных из API Microsoft Intune с помощью Postman

Для работы с API хранилища данных Intune можно использовать универсальный клиент REST, например Postman. Postman поможет глубже понять функции API, базовую модель данных OData, а также устранить неполадки подключения к ресурсам API. В этом разделе содержатся сведения о создании токена Auth2.0 для локального клиента. Токен будет нужен клиенту для прохождения проверки подлинности в Azure AD и получения доступ к ресурсам API.

### <a name="information-you-will-need-to-make-the-call"></a>Сведения, необходимые для вызова

Для выполнения вызова REST с помощью Postman вам потребуются приведенные ниже данные.

| Атрибут        | Описание                                                                                                                                                                          | Пример                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| URL-адрес обратного вызова     | Задайте его как URL-адрес обратного вызова на странице параметров приложения.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Имя токена       | Строка, используемая для передачи учетных данных в приложение Azure. В ходе процесса создается токен, чтобы можно было сделать вызов API хранилища данных.                          | Bearer                                                                                        |
| URL-адрес проверки подлинности         | Это URL-адрес, используемый для проверки подлинности. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/ |
| URL-адрес токена доступа | Это URL-адрес, используемый для предоставления токена.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| Идентификатор клиента        | Идентификатор, созданный и взятый на заметку при создании собственного приложения в Azure.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Область действия (необязательно) | Пустое                                                                                                                                                                               | Можно оставить поле пустым.                                                                     |
| Тип предоставления       | Токен является кодом авторизации.                                                                                                                                                  | Код авторизации                                                                            |

### <a name="odata-endpoint"></a>Конечная точка OData

Вам также нужна конечная точка. Чтобы получить конечную точку хранилища данных, вам потребуется пользовательский URL-адрес канала. Конечную точку OData можно получить на панели хранилища данных.

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**. Intune находится в разделе **Мониторинг и управление**.
3. Выберите элемент **Настройка хранилища данных Intune** в области **Другие задачи**.
4. Скопируйте пользовательский URL-адрес канала из области **Использовать сторонние службы отчетов**. Он должен выглядеть примерно так: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`.

Конечная точка имеет следующий формат: `https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`.

Например, сущность **dates** выглядит следующим образом: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.

Дополнительные сведения см. в разделе [Конечная точка API для хранилища данных Intune](reports-api-url.md).

### <a name="make-the-rest-call"></a>Осуществление вызова REST

Для получения нового токена доступа для Postman необходимо добавить URL-адрес авторизации в Azure AD, добавить идентификатор клиента и секрет клиента. Postman загрузит страницу авторизации, где нужно будет ввести учетные данные.

#### <a name="add-the-information-used-to-request-the-token"></a>Добавление сведений для запроса токена

1.  Скачайте Postman, если это средство еще не установлено. Скачать Postman можно на веб-сайте [www.getpostman](https://www.getpostman.com).
2.  Откройте Postman. Выберите операцию HTTP **GET**.
3.  Вставьте URL-адрес конечной точки в адрес. Он должен выглядеть примерно так:  

    `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Откройте вкладку **Авторизация** и в списке **Тип** выберите **OAuth 2.0**.
5.  Выберите элемент **Get New Access Token** (Получить новый маркер доступа).
6.  Убедитесь, что вы уже добавили URL-адрес обратного вызова в приложение в Azure. URL-адрес обратного вызова — `https://www.getpostman.com/oauth2/callback`.
7.  В поле **Имя токена** введите "Bearer".
8.  Добавьте **URL-адрес проверки подлинности**. Он должен выглядеть примерно так:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/`
9.  Добавьте **URL-адрес токена доступа**. Он должен выглядеть примерно так:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Добавьте **идентификатор клиента** из собственного приложения, созданного в Azure и носящего имя `Intune Data Warehouse Client`. Он должен выглядеть примерно так:  

     `88C8527B-59CB-4679-A9C8-324941748BB4`

11. Выберите **Код авторизации** и "Запросить токен доступа локально".

12. Выберите **Request Token** (Запросить токен).

    ![Сведения для токена](./media/reports-postman_getnewtoken.png)

13. Введите свои учетные данные на странице авторизации Active AD. Теперь список токенов в Postman содержит токен с именем `Bearer`.
14. Выберите элемент **Use Token** (Использовать токен). Список заголовков содержит новое значение ключа авторизации и значение `Bearer <your-authorization-token>`.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Отправка вызова на конечную с помощью Postman

1.  Выберите **Отправить**.
2.  Возвращаемые данные отобразятся в тексте ответа Postman.

    ![Postman 200 OK](./media/reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Создание клиента REST (C#) для получение данных из хранилища данных Intune

В следующем примере показан простой клиент REST. Код использует класс **httpClient** из библиотеки .Net. После получения учетных данных в Azure AD клиент создает вызов REST GET для получения сущности dates из API хранилища данных.

> [!Note]  
> Следующий пример кода можно найти на сайте [GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). Проверьте репозиторий GitHub на наличие последних изменений и обновлений для примера.

1. Откройте **Microsoft Visual Studio**.
2. Выберите **Файл** > **Создать проект**. Разверните **Visual C#** и выберите **Консольное приложение (.Net Framework)**.
3. Назовите проект ` IntuneDataWarehouseSamples`, перейдите к папке, где вы хотите сохранить проект, и нажмите кнопку **ОК**.
4. Щелкните правой кнопкой мыши имя решения в обозревателе решений, а затем выберите **Управление пакетами NuGet для решения**. Нажмите кнопку **Обзор**, а затем введите `Microsoft.IdentityModel.Clients.ActiveDirectory` в поле поиска.
5. Выберите пакет, в разделе "Управление пакетами для решения" выберите проект **IntuneDataWarehouseSamples**, а затем нажмите кнопку **Установить**.
6. Нажмите кнопку **Принимаю**, чтобы принять условия лицензии для пакета NuGet.
7. Откройте `Program.cs` в обозревателе решений.

    ![Проект в Visual Studio](./media/reports-get_rest_data_in.png)

8. Замените код в Program.cs на следующий код:  
   ```csharp
   namespace IntuneDataWarehouseSamples
   {
   using System;
   using System.Net.Http;
   using System.Net.Http.Headers;
   using Microsoft.IdentityModel.Clients.ActiveDirectory;

   class Program
   {
    static void Main(string[] args)
   {
   /**
   * TODO: Replace the below values with your own.
   * emailAddress - The email address of the user that you will authenticate as.
   *
   * password  - The password for the above email address.
   *    This is inline only for simplicity in this sample. We do not
   *    recommend storing passwords in plaintext.
   *
   * applicationId - The application ID of the native app that was created in AAD.
   *
   * warehouseUrl   - The data warehouse URL for your tenant. This can be found in
   *      the Azure portal.
   *
   * collectionName - The name of the warehouse entity collection you would like to
   *      access.
   */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
   resource: "https://api.manage.microsoft.com/",
   clientId: applicationId,
   userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
   }
   }
   ```

9. Обновите `TODO` в примере кода.
10. Нажмите сочетание клавиш **CTRL+F5** для сборки и выполнения клиента Intune.DataWarehouseAPIClient в режиме отладки.

    ![Сущность date, извлеченная в формате JSON.](./media/reports-get_rest_data_output.png)

11. Просмотрите выходные данные консоли. Выходные данные содержат данные в формате JSON, полученные из сущности **dates** в клиенте Intune.

## <a name="next-steps"></a>Дальнейшие шаги

Сведения об авторизации, структуре URL-адреса API и конечных точках OData см. в статье [Конечная точка API для хранилища данных Intune](reports-api-url.md).

Для поиска сущностей данных, содержащихся в интерфейсе API, можно также сослаться на модель данных для хранилища данных Intune. Дополнительные сведения см. в разделе [Модель данных для API хранилища данных Intune](reports-ref-data-model.md).
