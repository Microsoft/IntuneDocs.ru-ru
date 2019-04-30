---
title: Удаленное администрирование устройств в Microsoft Intune —Azure | Документы Майкрософт
description: Просмотрите необходимые роли для использования TeamViewer, рекомендации по установке соединителя TeamViewer и пошаговые инструкции для удаленного администрирования устройств с помощью Microsoft Intune на портале Azure
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/05/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd2d9f0a0caf87eb75ba3a9cdc123e69425ceb8b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61509745"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Используйте TeamViewer для удаленного администрирования устройств Intune

Устройства, управляемые Intune, можно администрировать удаленно с помощью [TeamViewer](https://www.teamviewer.com). TeamViewer — это программа стороннего производителя, которая приобретается отдельно. В этом разделе описано, как настроить TeamViewer в Intune и удаленно управлять устройством. 

## <a name="prerequisites"></a>Предварительные условия

- Необходимо поддерживаемое устройство. Устройства Android, Windows, iOS и macOS, управляемые с помощью Intune, поддерживают удаленное администрирование. TeamViewer может не поддерживать Windows Holographic (HoloLens), Windows Team (Surface Hub) или Windows 10 S. Актуальный список поддерживаемых устройств см. в разделе [TeamViewer](https://www.teamviewer.com).

- Администратор Intune на портале Azure должен иметь следующие [роли Intune](role-based-access-control.md):  

    - **Обновить удаленную помощь**: позволяет администраторам изменять параметры соединителя TeamViewer
    - **Запросить удаленную помощь**: позволяет администраторам начать новый сеанс удаленной помощи для любого пользователя. Пользователи с этой ролью не ограничиваются ролями Intune в пределах области. Кроме того, группы пользователей или устройств с ролью Intune в пределах области могут также запросить удаленную помощь. 

- Учетная запись [TeamViewer](https://www.teamviewer.com) с учетными данными для входа. Только некоторые лицензии TeamViewer поддерживают интеграцию с Intune. Конкретные потребности TeamViewer см. в разделе [Партнер по интеграции TeamViewer: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/).

Используя TeamViewer, вы можете использовать соединитель TeamViewer для Intune для создания сеансов TeamViewer, чтения данных Active Directory и сохранения токена доступа к учетной записи TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Настройка соединителя TeamViewer

Чтобы предоставить удаленную поддержку для устройств, настройте соединитель TeamViewer для Intune, выполнив следующие действия:

1. На [портале Azure](https://portal.azure.com) выберите **Все службы** и найдите **Microsoft Intune**.
2. В **Microsoft Intune** нажмите **Устройства**, а затем **Соединитель TeamViewer**.
3. Нажмите **Подключить** и примите условия лицензионного соглашения.
4. Нажмите **Войти в TeamViewer для авторизации**.
5. Откроется веб-страница сайта TeamViewer. Введите учетные данные лицензии TeamViewer и нажмите кнопку **Войти**.

## <a name="remotely-administer-a-device"></a>Удаленное администрирование устройства

После настройки соединителя вы можете удаленно управлять устройством. Выполните следующие шаги. 

1. На [портале Azure](https://portal.azure.com) выберите **Все службы** и найдите **Microsoft Intune**.
2. В **Microsoft Intune** нажмите **Устройства**, а затем **Все устройства**.
3. В списке выберите устройство для удаленного администрирования. В свойствах устройства выберите **Новый сеанс удаленной помощи**.
4. После того как Intune подключится к службе TeamViewer, появятся определенные сведения об устройстве. Выберите **Подключить**, чтобы начать удаленный сеанс.

![Удаленное администрирование устройства Android с помощью TeamViewer — пример](./media/android-teamviewer.png)

Когда вы запускаете удаленный сеанс, пользователь видит флажок уведомления на значке приложения "Корпоративный портал" на своем устройстве. Также уведомление отображается при открытии приложения. При необходимости пользователь может принять запрос удаленной помощи.

> [!NOTE]
> Устройства с ОС Windows, которые регистрируются без участия пользователей, например с помощью DEM и WCD, не отображают уведомление TeamViewer в приложении "Корпоративный портал". В этих случаях рекомендуется создать сеанс на портале TeamViewer.

В TeamViewer можно выполнить ряд действий на устройстве, включая возможность управления устройством. Подробные сведения о доступных возможностях см. в [Руководстве по TeamViewer](https://www.teamviewer.com/support/documents/).

После завершения сеанса закройте окно TeamViewer.
