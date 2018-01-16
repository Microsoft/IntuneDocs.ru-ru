---
title: "Сброс секретного кода на устройствах Windows с помощью Intune"
titlesuffix: Azure portal
description: "Вы можете узнать об использовании Intune для сброса секретного кода на устройствах Windows, интегрированных со службой сброса ПИН-кода Майкрософт."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 144313b63c1a6349a59220c901072dbf9d4c6f43
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Сброс секретного кода на устройствах Windows, интегрированных со службой сброса ПИН-кода Майкрософт, с помощью Intune

Возможность сброса секретного кода для устройств Windows интегрирована со службой сброса ПИН-кода Майкрософт, что позволяет сформировать новый секретный код для устройств под управлением Windows 10 Mobile. На устройствах должна использоваться Windows 10 Creators Update и более поздней версии.

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows — поддерживается в Windows 10 Creators Update и более поздних версиях (присоединение к Azure AD)
- Windows Phone — не поддерживается
- iOS — не поддерживается
- macOS — не поддерживается
- Android — не поддерживается


## <a name="before-you-start"></a>Перед началом работы

Прежде чем вы сможете удаленно сбросить секретный код на управляемых устройствах Windows, нужно подключить службу сброса ПИН-кода к вашему клиенту Intune и настроить управляемые устройства. Для этого выполните следующие инструкции.

### <a name="connect-intune-with-the-pin-reset-service"></a>Подключения Intune к службе сброса ПИН-кода

1. Посетите [веб-сайт интеграции со службой сброса ПИН-кода Майкрософт](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) и войдите в систему с помощью учетной записи администратора клиента, которую используете для управления клиентом Intune.
2. После входа щелкните **Принять**, чтобы предоставить службе сброса ПИН-кода доступ к вашей учетной записи.<br>
![Страница разрешений для службы сброса ПИН-кода](./media/pin-reset-service-application.png)
3. На портале Azure вы можете проверить интеграцию Intune и службы сброса ПИН-кода в колонке "Корпоративные приложения" — "Все приложения", как показано на следующем снимке экрана.<br>
![Приложение службы сброса ПИН-кода в Azure](./media/pin-reset-service-home-screen.png)
4. Войдите на [этот веб-сайт](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) с помощью учетных данных администратора клиента Intune и опять выберите **Принять**, чтобы предоставить службе доступ к вашей учетной записи.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Настройка устройств Windows для использования сброса ПИН-кода

Чтобы настроить сброс ПИН-кода на управляемых устройствах Windows, используйте [настраиваемую политику устройств Windows 10 в Intune](custom-settings-windows-10.md) для включения этой функции. Настройте политику с помощью следующих поставщиков служб конфигурации (CSP) политики Windows:


- **Для устройств** - **./Device/Vendor/MSFT/PassportForWork/*идентификатор_клиента*/Policies/EnablePinRecovery**

*идентификатор клиента* ссылается на ID Azure Active Directory, который можно получить на странице **Свойства** Azure Active Directory.

Для этого поставщика CSP задайте значение **True**.

## <a name="steps-to-reset-the-passcode"></a>Процедура сброса секретного кода

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Мониторинг и управление** > **Intune**.
3. В колонке **Intune** выберите **Устройства**.
4. В колонке **Устройства и группы** выберите **Управление** > **Все устройства**.
5. Выберите устройство, для которого нужно сбросить секретный код, а затем в колонке свойств устройства выберите **Новый секретный код**.
6. В появившемся подтверждении нажмите кнопку **Да**. Формируется секретный код, который отображается на портале в течение следующих семи дней.

## <a name="next-steps"></a>Дальнейшие шаги

В случае сбоя при сбросе секретного кода предоставляется ссылка на портал, позволяющая получить дополнительные сведения.


