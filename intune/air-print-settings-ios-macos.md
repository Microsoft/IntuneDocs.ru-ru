---
title: "Параметры Intune AirPrint для устройств iOS и MacOS"
titlesuffix: Azure portal
description: "Узнайте, как использовать Intune для автоматического подключения устройств iOS и MacOS к совместимым с AirPrint принтерам.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8953997ce5437227463b8061b8059d58721dce7a
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2017
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>Параметры AirPrint для устройств iOS и MacOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Используйте эти параметры, чтобы настроить на устройствах iOS или MacOS автоматическое подключение к совместимым с AirPrint принтерам в сети. Чтобы продолжить, вам нужен IP-адрес и путь к ресурсу принтеров.

## <a name="find-airprint-printer-information"></a>Поиск сведений о принтере AirPrint

С помощью этой процедуры добавьте сведения об AirPrint в полезные данные AirPrint, чтобы пользователи устройств iOS могли печатать документы на принтерах AirPrint.

1. На устройстве Mac, подключенном к той же локальной сети (подсети), что и принтеры AirPrint, откройте терминал (меню **/Приложения/Служебные программы**).
2. В окне терминала введите команду **ippfind**, а затем нажмите клавишу ВВОД.
3. Запишите все сведения о принтере, которые вернула команда, например **ipp://myprinter.local.:631/ipp/port1**. Первая часть сведений — это имя принтера, а последняя часть — это путь к ресурсу.
4. В окне терминала введите команду **ping myprinter.local**, а затем нажмите клавишу ВВОД.
5. Запишите IP-адрес, который вернула команда, например **PING myprinter.local (10.50.25.21)**.
6. Теперь используйте IP адрес и путь ресурса в параметрах полезных данных AirPrint. Примером IP-адреса может быть **10.50.25.21**, а примером пути ресурса может быть **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Настройка профиля AirPrint

1. В колонке **Функции устройства** выберите **AirPrint**.
2. Чтобы добавить целевой объект AirPrint, в колонке **AirPrint** введите его **IP-адрес** и **путь к ресурсу**, а затем нажмите кнопку **Добавить**.
3. Вы можете добавить любое количество целевых объектов. После этого нажмите кнопку **ОК**.

Вы также можете импортировать список принтеров из файла с разделителями-запятыми (CSV-файл) или экспортировать список.


## <a name="next-steps"></a>Дальнейшие действия

Теперь профиль устройства можно назначить определенным группам. Дополнительные сведения см. в статье [Назначение профилей устройств](device-profile-assign.md).