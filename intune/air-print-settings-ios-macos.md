---
title: Параметры Intune AirPrint для устройств iOS и MacOS
titlesuffix: Microsoft Intune
description: Узнайте, как использовать Microsoft Intune для автоматического подключения устройств iOS и macOS к совместимым с AirPrint принтерам.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 850c61868cc5404d1645482a6998856e465b4070
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186296"
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>Параметры AirPrint для устройств iOS и MacOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

1. Из [Intune на портале Azure](https://portal.azure.com) перейдите на страницу [**Функции устройства** в области конфигурации устройства](device-features-configure.md). 
1. На панели **Функции устройства** выберите **AirPrint**.
2. Чтобы добавить целевой объект AirPrint, на панели **AirPrint** введите его **IP-адрес** и **путь к ресурсу**, а затем нажмите кнопку **Добавить**.
3. Вы можете добавить любое количество целевых объектов. После этого нажмите кнопку **ОК**.

Вы также можете импортировать список принтеров из файла с разделителями-запятыми (CSV-файл) или экспортировать список.


## <a name="next-steps"></a>Дальнейшие шаги

Теперь профиль устройства можно назначить определенным группам. Дополнительные сведения см. в статье [Назначение профилей устройств](device-profile-assign.md).