---
title: Краткое руководство. Настройка автоматической регистрации в Intune
description: Краткое руководство. Настройка автоматической регистрации устройств Windows 10 в Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581779"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Краткое руководство. Настройка автоматической регистрации устройств Windows 10

В этом кратком руководстве вы настроите Microsoft Intune для автоматической регистрации устройств при входе конкретных пользователей на устройства Windows 10.

Если у вас нет подписки Intune, [зарегистрируйтесь для получения бесплатной пробной учетной записи](free-trial-sign-up.md).

## <a name="prerequisites"></a>Предварительные условия

- Для работы с этим кратким руководством необходимо сначала [создать пользователя](quickstart-create-user.md) и [создать группу](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Вход в Intune

Войдите в [Intune](https://aka.ms/intuneportal) в качестве глобального администратора или администратора службы Intune.

## <a name="set-up-windows-10-automatic-enrollment"></a>Настройка автоматической регистрации Windows 10

В этом примере будет использоваться регистрация MDM, что позволит автоматически регистрировать корпоративные и личные устройства.

1. В Azure выберите **Azure Active Directory**  >  **Мобильность (MDM и MAM)**  >  **Microsoft Intune**  >   **Некоторые**.
![Браузер](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. Выберите **Выберите группы**  >  **Тест-инженеры Contoso**  >  **Выбрать**.
3. Используйте значения по умолчанию для следующих URL-адресов:
    - URL-адрес условий использования MDM;
    - URL-адрес обнаружения MDM;
    - URL-адрес соответствия MDM.
4. Выберите **Сохранить**.
5. Выполните вход как пользователь в группе на устройстве Windows 10 и следуйте инструкциям на экране.

## <a name="clean-up-resources"></a>Очистка ресурсов

Сведения о перенастройке автоматической регистрации в Intune см. в статье [Настройка регистрации устройств Windows](windows-enroll.md).

## <a name="next-steps"></a>Дальнейшие шаги

В этом кратком руководстве вы узнали, как настроить автоматическую регистрацию устройств Windows 10. Вы также можете изучить другие способы регистрации устройств на всех платформах.

> [!div class="nextstepaction"]
> [Статья "Что такое регистрация устройств?"](device-enrollment.md)