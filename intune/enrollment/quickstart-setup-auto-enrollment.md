---
title: Краткое руководство. Настройка автоматической регистрации в Intune
description: Краткое руководство. Настройка автоматической регистрации устройств Windows 10 в Intune.
services: microsoft-intune
author: ErikjeMS
manager: dougeby
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e5cc7cf3661caa2b2640d9370d26402b7702d36b
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "76541080"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Краткое руководство. Настройка автоматической регистрации устройств с Windows 10

В этом кратком руководстве вы настроите Microsoft Intune для автоматической регистрации устройств при входе конкретных пользователей на устройства Windows 10.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Предварительные условия

- Подписка Microsoft Intune: [зарегистрируйтесь для получения бесплатной пробной учетной записи](../fundamentals/free-trial-sign-up.md).
- Для работы с этим кратким руководством необходимо сначала [создать пользователя](../fundamentals/quickstart-create-user.md) и [создать группу](../fundamentals/quickstart-create-group.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Вход в Intune с помощью диспетчера конечных точек (Майкрософт)

Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) в качестве глобального администратора или администратора службы Intune. Если вы создали подписку на пробную версию Intune, учетная запись, с помощью которой вы создали подписку, является глобальным администратором.

## <a name="set-up-windows-10-automatic-enrollment"></a>Настройка автоматической регистрации Windows 10

В этом примере будет использоваться регистрация MDM, что позволит автоматически регистрировать корпоративные и личные устройства. Мы будем использовать бесплатную подписку Azure Active Directory Premium.

1. В [центре администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431) выберите **Все службы** > **M365 Azure Active Directory** > **Azure Active Directory** > **Мобильность (MDM и MAM)** .
2. Выберите **Получить бесплатную пробную версию уровня "Премиум" для использования этой возможности**. Выбрав этот параметр, мы разрешим автоматическую регистрацию с помощью бесплатной пробной версии Azure Active Directory уровня "Премиум". 

    ![Выбор бесплатной пробной версии Azure Active Directory уровня "Премиум"](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

3. Выберите бесплатную пробную версию **Enterprise Mobility + Security E5**. 
4. Щелкните **Бесплатная пробная версия** > **Активировать** бесплатную пробную версию.

    ![Выбор бесплатной пробной версии Enterprise Mobility + Security E5](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

    > [!NOTE]
    > Активация может занять около минуты. 

3. Выберите **Microsoft Intune**, чтобы настроить Intune. 

    ![Выбор Microsoft Intune в списке](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. В **области пользователей MDM** выберите **Некоторые**, чтобы использовать автоматическую регистрацию MDM для управления корпоративными данными на устройствах Windows сотрудников вашей компании. Автоматическая регистрация MDM будет настроена для сценариев с использованием собственных устройств и устройств, присоединенных к AAD.

    ![Выбор "Некоторые" в списке "Настройка"](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Щелкните **Выбрать группы** > **Тест-инженеры Contoso** > **Выбрать**, чтобы указать назначенную группу.

    ![Выбор группы для регистрации](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. Выберите **Некоторые** в **области пользователей MAM** для управления данными на устройствах сотрудников.

    ![Выбор группы для регистрации](./media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-06.png)

7. Выберите **Выберите группы** > **Тест-инженеры Contoso** > **Выбрать**, чтобы указать назначенную группу. 
8. Используйте значения по умолчанию для остальных параметров конфигурации.
9. Выберите **Сохранить**.

## <a name="clean-up-resources"></a>Очистка ресурсов

Сведения о перенастройке автоматической регистрации в Intune см. в статье [Настройка регистрации устройств Windows](windows-enroll.md).

## <a name="next-steps"></a>Дальнейшие шаги

В этом кратком руководстве вы узнали, как настроить автоматическую регистрацию устройств Windows 10. Дополнительные сведения о регистрации устройств см. в статье [Что такое регистрация устройств?](device-enrollment.md).

Чтобы выполнить эту серию кратких руководств по Intune, переходите к следующему руководству.

> [!div class="nextstepaction"]
> [Краткое руководство. Регистрация устройства с ОС Windows 10](../quickstart-enroll-windows-device.md)
