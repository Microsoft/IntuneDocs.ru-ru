---
title: Краткое руководство. Настройка автоматической регистрации в Intune
description: Краткое руководство. Настройка автоматической регистрации устройств Windows 10 в Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 11/05/2018
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 810adbf06ddcd0aabb5c758f6a71c898116a9cee
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394315"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Краткое руководство. Настройка автоматической регистрации устройств с Windows 10

В этом кратком руководстве вы настроите Microsoft Intune для автоматической регистрации устройств при входе конкретных пользователей на устройства Windows 10.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](free-trial-sign-up.md).

## <a name="prerequisites"></a>Предварительные условия

- Подписка Microsoft Intune: [зарегистрируйтесь для получения бесплатной пробной учетной записи](free-trial-sign-up.md).
- Для работы с этим кратким руководством необходимо сначала [создать пользователя](quickstart-create-user.md) и [создать группу](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Вход в Intune

Войдите в [Intune](https://aka.ms/intuneportal) в качестве глобального администратора или администратора службы Intune.

## <a name="set-up-windows-10-automatic-enrollment"></a>Настройка автоматической регистрации Windows 10

В этом примере будет использоваться регистрация MDM, что позволит автоматически регистрировать корпоративные и личные устройства. Мы будем использовать бесплатную подписку Azure Active Directory Premium.

1. В Azure выберите **Azure Active Directory** > **Мобильность (MDM и MAM)**.
2. Выберите **Получить бесплатную пробную версию уровня "Премиум" для использования этой возможности**. Выбрав этот параметр, мы разрешим автоматическую регистрацию с помощью бесплатной пробной версии Azure Active Directory уровня "Премиум". 

    ![Выбор бесплатной пробной версии Azure Active Directory уровня "Премиум"](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

    Выберите бесплатную пробную версию **Enterprise Mobility + Security E5**. Кроме того, необходимо **активировать** бесплатную пробную версию.

    ![Выбор бесплатной пробной версии Enterprise Mobility + Security E5](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

3. Выберите **Microsoft Intune**. 

    ![Выбор Microsoft Intune в списке](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. В **области пользователей MDM** выберите **Некоторые**, чтобы использовать автоматическую регистрацию MDM для управления корпоративными данными на устройствах Windows сотрудников вашей компании. Автоматическая регистрация MDM будет настроена для сценариев с использованием собственных устройств и устройств, присоединенных к AAD.

    ![Выбор "Некоторые" в списке "Настройка"](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Выберите **Выберите группы** > **Тест-инженеры Contoso** > **Выбрать**, чтобы указать назначенную группу.

    ![Выбор группы для регистрации](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. Выберите **Некоторые** в **области пользователей MAM** для управления данными на устройствах сотрудников.
7. Выберите **Выберите группы** > **Тест-инженеры Contoso** > **Выбрать**, чтобы указать назначенную группу. 
8. Используйте значения по умолчанию для остальных параметров конфигурации.
9. Выберите **Сохранить**.

## <a name="clean-up-resources"></a>Очистка ресурсов

Сведения о перенастройке автоматической регистрации в Intune см. в статье [Настройка регистрации устройств Windows](windows-enroll.md).

## <a name="next-steps"></a>Дальнейшие шаги

В этом кратком руководстве вы узнали, как настроить автоматическую регистрацию устройств Windows 10. Дополнительные сведения о регистрации устройств см. в статье [Что такое регистрация устройств?](device-enrollment.md).

Чтобы выполнить эту серию кратких руководств по Intune, переходите к следующему руководству.

> [!div class="nextstepaction"]
> [Краткое руководство. Регистрация устройства с ОС Windows 10](quickstart-enroll-windows-device.md)
