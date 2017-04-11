---
title: "Возможности программного клиента Intune для ПК | Документы Майкрософт"
description: "Сведения о возможностях управления компьютерами с Windows с помощью программного клиента Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Возможности управления компьютерами Windows при использовании программного клиента Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В большинстве случаев устройства регистрируются в Microsoft Intune, что дает более широкий набор возможностей. Но для управления компьютерами можно использовать программный клиент, предоставляющий следующие возможности:

-   **[Управление обновлениями программного обеспечения](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**. Вы можете обновлять компьютеры и управлять временем применения обновлений.

-   **[Политика брандмауэра Windows](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**. Гарантирует, что брандмауэр Windows будет включен и правильно настроен на всех компьютерах, используемых организацией.

-   **[Защита от вредоносных программ](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**. В Intune входит компонент Endpoint Protection, который помогает защитить компьютеры от вредоносных программ.

-   **[Удаленная помощь](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**. Intune позволяет пользователям связываться со специалистами службы ИТ-поддержки, используя функцию удаленного рабочего стола, включенную в Intune (для этого необходима программа TeamViewer).

-   **[Управление лицензиями на программное обеспечение](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**. Отслеживайте количество доступных лицензий на программное обеспечение и количество используемых доступных лицензий.
-   **[Развертывание приложений](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**. Развертывайте программное обеспечение на компьютерах, которыми вы управляете. Некоторые функции управления приложениями недоступны при управлении компьютерами с помощью программного клиента.


Intune поддерживает установку программного клиента максимум на 7000 устройств Windows.

## <a name="operating-system-requirements"></a>Требования к операционной системе
Intune позволяет управлять компьютерами под управлением следующих версий Windows (32- и 64-разрядных):


-   **Windows Vista** Business, Enterprise и Ultimate;

-   **Windows 7** Профессиональная, Корпоративная и Максимальная (без пакета обновления или с пакетом обновления 1);

-   **Windows 8** Профессиональная и Корпоративная;

-   **Windows 8.1** Профессиональная и Корпоративная;

- **Windows 10** Pro, для образовательных учреждений и Корпоративная.


## <a name="minimum-hardware-requirements"></a>Минимальные требования к оборудованию
Для установки программного клиента Intune необходимо выполнить следующие минимальные требования к оборудованию:

|Требование|Подробные сведения|
|---------------|--------------------|
|Network (Сеть)|Для клиента требуется компьютер с подключением к Интернету.|
|Процессор и память|См. требования к процессору и ОЗУ для ОС компьютера.|
|Пространство на диске|200 МБ свободного места на диске до установки клиентского ПО.|

## <a name="further-requirements"></a>Дополнительные требования
Для установки программного клиента Intune необходимо выполнить следующие минимальные требования к программному обеспечению:

|Требование|Подробные сведения|
|---------------|--------------------|
|Разрешения администратора|Учетная запись, используемая для установки клиентского программного обеспечения, должна иметь разрешения локального администратора для этого компьютера.|
|Установщик Windows 3.1|Требуется как минимум установщик Windows 3.1.|
|Удаление несовместимого клиентского программного обеспечения|Перед установкой клиента Intune с компьютера необходимо удалить следующее клиентское программное обеспечение:<br /><br />- Любая версия Configuration Manager<br />- Любая версия Microsoft Systems Management Server (SMS)|

### <a name="see-also"></a>См. также
[Возможности управления зарегистрированными устройствами в Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


