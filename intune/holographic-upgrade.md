---
title: Обновление Windows Holographic до Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Сведения о том, как обновить устройства с Windows Holographic и перевести их на Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e6a71d48e81914808b9af037692a44e4f651bf55
ms.sourcegitcommit: 2198a39ae48beca5fc74316976bc3fc9db363659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38224776"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Обновление устройств с Windows Holographic до Windows Holographic for Business


Для работы с устройствами под управлением Windows Holographic в Microsoft Intune необходимо обновить устройства с Windows Holographic на Windows Holographic for Business. Можно создать профиль обновления выпуска для выполнения обновления. Для получения нужной лицензии на обновление Microsoft HoloLens вы можете приобрести пакет Commercial Suite. Дополнительные сведения: [Разблокировка функций Windows Holographic for Business](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Настройка для устройства профиля конфигурации обновления выпуска

1. Войдите на [портал Azure](https://portal.azure.com) с учетной записью администратора.


2.  Выберите **Конфигурация устройства**, **Профили** и щелкните **+ Создать профиль**.

    ![Создать профиль](media/Holographic-create-profile.png)

3.  На странице **Создать профиль** введите имя профиля, выберите платформу **Windows 10 и более поздние версии** и укажите тип платформы **Обновление выпуска**. Щелкните **Настроить параметры**.

5. На странице **Обновление выпуска** в поле **Выпуск, до которого необходимо обновить** выберите **Windows 10 Holographic for Business**. В поле **Файл лицензии** укажите расположение полученного вами XML-файла лицензии.

    ![Введите имя файла XML](media/Holographic-edition-upgrade.png)
 
5.  Нажмите кнопку **ОК**, а затем щелкните **Создать** для создания профиля.


## <a name="deploy-the-edition-upgrade-policy"></a>Развертывание политики обновления выпусков

Теперь необходимо назначить профиль обновления выпуска выбранным группам или устройствам.

1. В созданном ранее профиле щелкните **Назначения**.

2. На странице **Назначения** выберите группы пользователей и устройства, которые вы хотите включить или исключить для политики.

![Включение и исключение групп](media/Holographic-groups.PNG)

При регистрации этих пользователей или устройств в Intune будет применен профиль обновления выпуска. 

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения о группах: [Начало работы с группами](get-started-groups.md).


