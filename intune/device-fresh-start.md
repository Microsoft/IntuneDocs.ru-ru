---
title: Сброс настроек для устройств Windows 10 с помощью Microsoft Intune — Azure | Документация Майкрософт
description: Чтобы удалить приложения с компьютеров Windows 10 с помощью Microsoft Intune, используйте действие "Чистый запуск".
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 230c328c14f0da39db34c8b91ac30fe05f9b05ca
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57388194"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Сброс устройств с Windows 10 с помощью функции нового запуска в Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

При использовании на устройствах действия **Новый запуск** будут удалены все приложения, установленные на компьютерах с Windows 10 версии 1703 и более поздними версиями. Это действие помогает удалить предварительно установленные приложения (от изготовителя оборудования), обычно имеющиеся на новом компьютере.  

1. Войдите на [портал Azure](https://portal.azure.com) и перейдите в раздел **Microsoft Intune** > **Устройства** > **Все устройства**.
2. Выберите настольный компьютер с Windows 10 из списка управляемых устройств.
3. Щелкните **Новый запуск**. 
4. Выберите **Сохранить данные пользователя на устройстве**, чтобы:
   * Сохранить устройство присоединенным к Azure AD
    * Когда пользователь, зарегистрированный в Azure Active Directory, входит на устройство, оно снова регистрируется в системе управления мобильными устройствами.
    * Сохранить содержимое домашней папки пользователя на устройстве и удалить приложения и настройки  
  > [!IMPORTANT]
 > Если вы не сохраните пользовательские данные, устройство будет возвращено к тому состоянию, в котором оно находится в момент поставки. Регистрация устройства BYOD в Azure AD и системе управления мобильными устройствами будет отменена.
 > Когда пользователь, зарегистрированный в Azure Active Directory, входит на устройство, присоединенное к Azure AD, оно снова регистрируется в системе управления мобильными устройствами.
 
5. Нажмите кнопку **ОК**.   
6. Чтобы просмотреть состояние этого действия, выберите **Устройства** и щелкните **Действия устройства**.  
