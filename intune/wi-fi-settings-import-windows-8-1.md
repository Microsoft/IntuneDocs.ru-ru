---
title: Импорт параметров Wi-Fi для устройств Windows в Microsoft Intune в Azure | Документы Майкрософт
description: Экспортируйте параметры Wi-Fi с устройства Windows в формате XML с помощью netsh wlan. Затем импортируйте этот файл в Intune, чтобы создать профиль Wi-Fi для устройств под управлением Windows 8.1, Windows 10 и Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 841be002cf9ed99142ce95a1f9cafda761d1b856
ms.sourcegitcommit: cb4e71cd48311ea693001979ee59f621237a6e6f
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67558481"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Импорт параметров Wi-Fi для устройств Windows в Intune

Для устройств под управлением Windows можно импортировать профиль конфигурации Wi-Fi, который ранее был экспортирован в файл. **Для Windows 10 и более поздних версий [создать профиль Wi-Fi](wi-fi-settings-windows.md) можно также непосредственно в Intune**.

Область применения:  
- Windows 8.1 и более поздние версии
- Windows 10 и более поздней версии
- Windows 10 Desktop и Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Экспорт параметров Wi-Fi с устройства Windows

В Windows команда `netsh wlan` позволяет экспортировать существующий профиль Wi-Fi в XML-файл, который доступен Intune для чтения. Для использования профиля ключ необходимо экспортировать в виде обычного текста.

На компьютере Windows, где уже установлен необходимый профиль Wi-Fi, выполните приведенные ниже действия.

1. Создайте локальную папку для экспортированных профилей Wi-Fi, например **С:\WiFi**.
2. Откройте командную строку с правами администратора.
3. Выполните команду `netsh wlan show profiles` и запомните имя профиля, который требуется экспортировать. В этом примере профиль имеет имя **WiFiName**.
4. Выполните команду `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Эта команда создает в целевой папке файл профиля Wi-Fi с именем **Wi-Fi-WiFiName.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>Импорт параметров Wi-Fi в Intune

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Выберите **Конфигурация устройства** > **Профили** > **Создать профиль**.
3. Введите значения в поля **Имя** и **Описание** для профиля ограничения устройства.

    > [!IMPORTANT]
    > - Имя **должно** соответствовать значению атрибута name в XML-файле профиля Wi-Fi. В противном случае произойдет сбой.
    > - При экспорте профиля Wi-Fi, который содержит общий ключ, в команду **необходимо** добавить `key=clear`. Например, введите: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`.
    > - Использование общего ключа в Windows 10 приводит к появлению ошибки исправления в Intune. В этом случае профиль Wi-Fi правильно назначается устройству и работает должным образом.
    > - При экспорте профиля Wi-Fi, который содержит общий ключ, убедитесь, что файл защищен. Ключ указан в виде обычного текста, поэтому вы должны защитить его.

4. В поле **Платформа** выберите **Windows 8.1 и более поздние версии**.
5. В поле **Тип профиля** выберите **Импорт Wi-Fi**.
6. Настройте следующие параметры.
    - **Имя подключения**. Введите имя Wi-Fi-подключения. Это имя будет отображаться для пользователей при просмотре доступных сетей Wi-Fi.
    - **XML-код профиля**. Нажмите кнопку "Обзор", чтобы выбрать XML-файл, содержащий параметры профиля Wi-Fi, которые необходимо импортировать.
    - **Содержимое файла**. Отображает XML-код для выбранного профиля конфигурации.
7. По завершении нажмите **ОК** > **Создать**, чтобы сохранить изменения. Созданный профиль отобразится в списке профилей.

## <a name="next-steps"></a>Дальнейшие шаги

Мы создали профиль, но он пока ничего не делает. Теперь нам нужно [назначить этот профиль](device-profile-assign.md).

## <a name="more-resources"></a>Дополнительные ресурсы

[Общие сведения о параметрах Wi-Fi](wi-fi-settings-configure.md), в том числе для других доступных платформ.
