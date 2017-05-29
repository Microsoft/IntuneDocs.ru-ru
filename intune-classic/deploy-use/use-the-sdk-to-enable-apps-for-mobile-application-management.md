---
title: "Подготовка приложений для управления мобильными приложениями с помощью пакета SDK | Документы Майкрософт"
description: "В этом разделе содержатся общие сведения о том, почему следует использовать пакет SDK для приложений Intune."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 26b00081-7c05-4969-ace1-0585e44d5cd2
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ec4e2f966fa8c24505ce1fa74a59c95908273bd1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="use-the-sdk-to-enable-apps-for-mobile-application-management"></a>Подготовка приложений для управления мобильными приложениями с помощью пакета SDK

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Используйте пакет SDK для приложений Microsoft Intune, чтобы позволить Intune управлять определенными функциями приложений iOS или Android. После включения приложения для него можно развернуть политики. Они используют указанные возможностей для защиты корпоративных данных. Ниже приведены примеры типов защиты, которые можно реализовать с помощью пакета SDK:

-   Запрет пользователям на копирование корпоративных документов в облако.

-   Принудительное шифрование данных, сохраняемых на устройстве приложением.

-   Принудительное использование управляемого браузера.

-   Удаленная очистка корпоративных данных из приложения.

Для использования пакета SDK нужен доступ к исходному коду приложения, однако большинство возможностей пакета можно включить без изменения поведения приложения.

Обзор пакета SDK см. в разделе [Обзор](/intune-classic/develop/intune-app-sdk-get-started).

### <a name="see-also"></a>См. также
[Выбор подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

