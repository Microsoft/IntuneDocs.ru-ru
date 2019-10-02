---
title: Сброс секретного кода на устройствах Windows с помощью Microsoft Intune — Azure | Документы Майкрософт
description: Чтобы сбросить секретный код на устройствах Windows, установите службу сброса ПИН-кода Майкрософт и клиент сброса ПИН-кода Майкрософт, создайте политику устройств с помощью идентификатора каталога Active Directory Azure, а затем сбросьте секретный код на портале Azure с помощью Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cb34490b6b88d6a62fa9fb29a64b7a391eed7c6b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728433"
---
# <a name="reset-the-passcode-on-windows-devices-using-intune"></a>Сброс секретного кода на устройствах Windows с помощью Intune

Вы можете сбросить секретный код для устройств Windows. Функция сброса секретного кода использует службу сброса ПИН-кода Майкрософт, чтобы создать новый секретный код для устройств под управлением Windows 10 Mobile. 

## <a name="supported-platforms"></a>Поддерживаемые платформы

- Windows 10 Mobile с Creators Update и более поздних версий (присоединение к Azure AD)

Следующие платформы **не** поддерживаются:
- Windows
- iOS
- macOS
- Android

## <a name="authorize-the-pin-reset-services"></a>Авторизация служб сброса ПИН-кода

Чтобы сбросить секретный код на устройствах Windows, подключите службу сброса ПИН-кода к вашему клиенту Intune.

1. Перейдите к [службе сброса ПИН-кода Майкрософт](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) и войдите через учетную запись администратора клиента.
2. Нажмите **Принять**, чтобы служба сброса ПИН-кода получила доступ к вашей учетной записи. ![Принятие запроса сервера на сброс ПИН-кода для разрешений](./media/device-windows-pin-reset/pin-reset-service-home-screen.png)
3. Перейдите к [клиенту сброса ПИН-кода Майкрософт](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) и войдите через учетную запись администратора клиента. Нажмите **Принять**, чтобы клиент сброса ПИН-кода получил доступ к вашей учетной записи.
4. На [портале Azure](https://portal.azure.com) убедитесь, что службы сброса ПИН-кода находятся в списке "Корпоративные приложения" (Все приложения). ![Страница разрешений для службы сброса ПИН-кода](./media/device-windows-pin-reset/pin-reset-service-application.png)

> [!NOTE]
> После принятия запросов на сброс ПИН-кода вы можете получить сообщение `Page not found` или не произойдет ничего. Это нормально. Обязательно проверьте, что оба приложения для сброса ПИН-кода указаны для вашего клиента.

## <a name="configure-windows-devices-to-use-pin-reset"></a>Настройка устройств Windows для использования сброса ПИН-кода

Чтобы настроить сброс ПИН-кода на управляемых устройствах Windows, используйте [настраиваемую политику устройств Windows 10 в Intune](../configuration/custom-settings-windows-10.md). Настройте политику с помощью следующих поставщиков служб конфигурации (CSP) политики Windows:

**Используйте политику устройств** - `./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery`

Замените *идентификатор клиента* на идентификатор каталога Azure AD, который указан в **Свойствах** Azure Active Directory на [портале Azure](https://portal.azure.com).

Для этого поставщика CSP задайте значение **True**.

> [!TIP]
> После создания политики вы назначаете (или разворачиваете) ее в группе. Политику можно назначить группе пользователей или группе устройств. Если вы назначаете ее группе пользователей, группа может включать пользователей, имеющих другие устройства, например iOS. Технически политика не будет применяться к ним, но эти устройства будут включены в сведения о состоянии.

## <a name="reset-the-passcode"></a>Сброс секретного кода

1. Войдите на [портал Azure](https://portal.azure.com). 
2. Выберите **Все службы**, отфильтруйте список по **Intune** и выберите **Microsoft Intune**.
3. Нажмите **Устройства** и выберите **Все устройства**.
4. Выберите устройство, для которого необходимо сбросить секретный код. В свойствах устройства выберите **Новый секретный код**.
5. Нажмите кнопку **Да** для подтверждения. Формируется секретный код, который отображается на портале в течение следующих семи дней.

## <a name="next-step"></a>Дальнейшие действия

В случае сбоя при сбросе секретного кода предоставляется ссылка на портал с дополнительными сведениями.
