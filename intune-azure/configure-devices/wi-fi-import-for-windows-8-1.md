---
title: "Импорт параметров Wi-Fi для устройств с Windows 8.1 или более поздней версии"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Импорт параметров Wi-Fi из Windows в профиль Wi-Fi в Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 9f98a786e97afbb93628609808637def0a7e8fe8
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Импорт параметров Wi-Fi на устройства с ОС Windows 8.1 и более поздних версий в Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Для устройств под управлением Windows 8.1 или Windows 10 для настольных компьютеров или мобильных устройств можно импортировать профиль конфигурации Wi-Fi, который ранее был экспортирован в файл.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Экспорт параметров Wi-Fi с устройства Windows

В Windows используйте служебную программу **netsh wlan**, чтобы экспортировать существующий профиль Wi-Fi в XML-файл для чтения в Intune. На компьютере Windows, где уже установлен необходимый профиль Wi-Fi, выполните приведенную ниже процедуру.
1. Создайте локальную папку для экспортированных профилей Wi-Fi, например **С:\WiFi**.
1. Откройте командную строку с правами администратора.
1. Выполните команду **netsh wlan show profiles** и запишите имя профиля, который требуется экспортировать. В этом примере профиль имеет имя **WiFiName**.
1. Выполните команду **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Она создаст файл профиля Wi-Fi с именем **Wi-Fi-WiFiName.xml** в конечной папке.

## <a name="import-the-wi-fi-settings-into-intune"></a>Импорт параметров Wi-Fi в Intune

1. Зарегистрируйтесь на портале Azure.
2. Выберите **Больше служб** > **Другое** > **Intune**.
3. В колонке **Intune** выберите пункт **Конфигурация устройства**.
2. В колонке **Конфигурация устройства** выберите **Управление** > **Профили**.
3. В колонке профилей выберите **Создать профиль**.
4. В колонке **Создание профиля** введите **имя** и **описание** для профиля ограничения устройства.
5. Из раскрывающегося списка **Платформа** выберите **Windows 8.1 и более поздней версии**.
6. Из раскрывающегося списка **Профиль** выберите **Импорт Wi-Fi**.
7. В колонке **Базовый Wi-Fi** настройте следующие значения:
    - **Имя подключения.** Введите имя подключения Wi-Fi. Это имя будет отображаться для пользователей при просмотре доступных сетей Wi-Fi.
    - **XML-код профиля.** Нажмите кнопку "Обзор", чтобы выбрать XML-файл, содержащий параметры профиля Wi-Fi, которые необходимо импортировать в Intune.
    - **Содержимое файла.** Отображает XML-код для выбранного профиля конфигурации.
8. По завершении вернитесь в колонку **Создание профиля** и щелкните **Создать**.

Созданный профиль отобразится в колонке со списком профилей.

