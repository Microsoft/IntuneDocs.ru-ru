---
title: "Разрешенные и заблокированные приложения для KNOX | Документы Майкрософт"
description: "Настраиваемый профиль для создания списка разрешенных и заблокированных приложений для KNOX."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 933a47163ccc66a1bab636982ca422c4a704656d
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Использование настраиваемых политик для разрешения и блокировки приложений для устройств Samsung KNOX Standard

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В этом разделе приведены процедуры для создания настраиваемой политики Microsoft Intune, которая создает один из следующих элементов:

- Список приложений, запуск которых заблокирован на конкретном устройстве. Выполнение приложений в этом списке блокируется, даже если они были установлены после применения политики.
- Список приложений, которые пользователи устройства могут установить из магазина Google Play. Устанавливать можно будет только приложения из списка. Другие приложения невозможно установить из магазина.

Эти настройки могут использовать только устройства под управлением Samsung KNOX Standard.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>Создание списка разрешенных или заблокированных приложений

1. В [консоли администрирования Microsoft Intune](https://manage.microsoft.com/) последовательно выберите **Политика** &gt; **Политики конфигурации** &gt; **Добавить**.
2. В диалоговом окне **Создать новую политику** разверните узел **Android**, выберите **Настраиваемая конфигурация** и нажмите кнопку **Создать политику**.
3. Укажите имя и необязательное описание для политики, а затем в разделе **Параметры OMA-URI** выберите **Добавить**.
4. В диалоговом окне **Добавление или изменение параметра OMA-URI** укажите следующие значения. Для списка приложений, запуск которых будет блокироваться на устройстве:
    
    - **Имя параметра.** Введите **PreventStartPackages**.
    - **Описание параметра.** Введите необязательное описание, например "Список приложений, запуск которых запрещен".
    -     **Тип данных.** В раскрывающемся списке выберите **Строка**.
    -     **OMA-URI.** Введите **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -     **Значение.** Введите список имен пакетов приложений, которые требуется заблокировать. В качестве разделителей можно использовать **; : ,** или **|**. (Пример: package1;package2;)

    Для списка приложений, которые пользователи могут устанавливать из магазина Google Play (все прочие приложения исключаются):

    - **Имя параметра.** Введите **AllowInstallPackages**.
    - **Описание параметра.** Введите необязательное описание, например "Список приложений, которые пользователи могут устанавливать из Google Play".
    - **Тип данных.** В раскрывающемся списке выберите **Строка**.
    - **OMA-URI.** Введите **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Значение.** Введите список имен пакетов приложений, которые требуется разрешить. В качестве разделителей можно использовать **; : ,** или **|**. (Пример: package1;package2;)

4. Нажмите кнопку **ОК**, а затем щелкните **Сохранить политику**. 

>[!TIP]
> Чтобы найти идентификатор пакета приложения, перейдите к приложению в магазине Google Play. Идентификатор пакета содержится в URL-адресе страницы приложения. Например, идентификатор пакета приложения Microsoft Word — **com.microsoft.office.word**.

При каждой проверке целевым устройством будут применяться эти параметры приложения.


## <a name="deploy-the-policy"></a>Развертывание политики

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.

2.  В диалоговом окне **Управление развертыванием** выберите одну или несколько групп, для которых будет развернута политика, а затем нажмите кнопки **Добавить** &gt; **ОК**.

 
При выборе развернутой политики можно просмотреть дополнительные сведения о развертывании в нижней части списка политик.

### <a name="see-also"></a>См. также
[Параметры политики Android и Samsung KNOX в Microsoft Intune](android-policy-settings-in-microsoft-intune.md)
