---
# required metadata

title: Подготовка к регистрации устройств в Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Подготовка к регистрации устройств в Microsoft Intune
Чтобы позволить сотрудникам регистрировать мобильные устройства (в том числе устройства Android, iOS и Windows Phone, а также компьютеры с Windows) в Intune, необходимо включить регистрацию устройств. Чтобы разрешить регистрацию, необходимо задать центр управления мобильными устройствами, настроить корпоративный портал Intune, назначить лицензии и включить регистрацию для платформы устройств.

## <a name="BKMK_Set_MDM_Authority"></a>Указание центра управления мобильными устройствами
Центр управления мобильными устройствами MDM определяет службу управления с разрешением на управление набором устройств. Возможные варианты центра управления мобильными устройствами — отдельная служба Intune или Configuration Manager с Intune. Если Configuration Manager задан в качестве центра управления, использовать другие службы для управления мобильными устройствами нельзя.

>[!IMPORTANT]
> Необходимо тщательно продумать вариант управления мобильными устройствами: с помощью только Intune (веб-служба) или System Center Configuration Manager с Intune (локальное программное решение в сочетании с веб-службой). Заданный центр управления мобильными устройствами изменить нельзя.



1.  В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) щелкните **Администрирование** &gt; **Управление мобильными устройствами**.

2.  В списке **Задачи** выберите **Задать центр управления мобильными устройствами**. Откроется диалоговое окно **Установка центра MDM** .

    ![Диалоговое окно "Задать центр MDM"](../media/intune-mdm-authority.png)

3.  Intune просит подтвердить, что Intune должен быть вашим центром MDM. Установите флажок и нажмите кнопку **Да** , чтобы использовать Microsoft Intune для управления мобильными устройствами.

## Настройка корпоративного портала Intune и назначение лицензий
Корпоративный портал Intune позволяет пользователям получать доступ к ресурсам организации, например приложениям, находить информацию по поддержке и регистрировать устройства или отменять их регистрацию. Перед регистрацией устройств следует [настроить корпоративный портал](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Чтобы разрешить доступ к Intune, необходимо также [назначить пользователям лицензии](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4).

## Настройка управления устройствами
После задания центра управления мобильными устройствами нужно настроить управление устройствами для операционных систем, которые должны поддерживаться в вашей организации. Действия по настройке управления устройствами зависят от операционной системы. Например, для ОС Android в консоли администрирования Intune не нужно выполнять никаких действий. Однако для управления Windows и iOS требуется установить отношение доверия между устройствами и Intune.

> [!div class="op_single_selector"]
- [Настройка управления Android с помощью Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Настройка управления Windows Phone с помощью Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Настройка управления устройствами Windows с помощью Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Кроме того, вы можете выполнить следующие действия.
 - Регистрация нескольких устройств с помощью [учетной записи диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - [Указание принадлежащих организации устройств с помощью номеров IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) для регистрации устройств и применения политики


<!--HONumber=May16_HO2-->


