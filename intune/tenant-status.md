---
title: Страница "Состояние клиента" Microsoft Intune
titleSuffix: Microsoft Intune
description: Страница состояния клиента Intune позволяет просмотреть важные сведения о клиенте без необходимости покидать портал Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98b3180bc90c7b54213781ddf8b6668918b22dd3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2019
ms.locfileid: "54205029"
---
# <a name="intune-tenant-status-page"></a>Страница "Состояние клиента" Intune
Страница состояния клиента служит в качестве централизованного концентратора, выводя важные сведения о клиенте, доступности лицензии и ее использовании, состоянии соединителя и важные сообщения о службе Intune.  

Для просмотра панели мониторинга на портале Azure выберите пункты **Intune > Состояние клиента**.  Состояние клиента отображается в разделе **Справка и поддержка**.  

Страница разделена на четыре части:

## <a name="tenant-details"></a>Сведения о клиенте.
Сведения о клиенте предоставляют краткие сведения о клиенте. Просмотрите здесь сведения, такие как имя вашего клиента, расположение центра управления мобильными устройствами и номер выпуска службы. Номер выпуска службы — это ссылка, позволяющая открыть статью *Новые возможности Intune* на сайте документации Майкрософт, где можно прочитать о последних функциях и обновлениях в службе Intune.  

Этот раздел также содержит основные сведения о наличии лицензий и количестве лицензий, назначенных пользователям. Лицензии для устройств не отображаются.

## <a name="connector-status"></a>Состояние соединителя
Состояние соединителя — здесь можно централизованно просмотреть состояние всех доступных соединителей для Intune.  

Соединители:
- **Подключения, настроенные для внешних служб**. Например, для служб *Apple Volume Purchase Program* или *Windows Autopilot*.  Состояние этого типа соединителя основано на времени последней успешной синхронизации.
- **Сертификаты и учетные данные, необходимые для подключения к внешней неуправляемой службе**, например сертификатов *служб push-уведомлений Apple* (APNS). Состояние для этого типа соединителя основано на отметке времени окончания срока действия сертификата или учетных данных.  

По умолчанию отображается только пять соединителей. Можно выбрать пункт **Показать все соединители**, чтобы расширить этот список для просмотра всех доступных соединителей, включая соединители, еще не настроенные для использования.  

При наличии нескольких соединителей одного типа состояние — это сводка для таких соединителей. Состояние наименьшей работоспособности среди всех соединителей группы указывается в качестве работоспособности всей группы.  

Неработоспособные соединители всегда будут отображаться в верхней части списка. Далее идут соединители с предупреждениями, а затем список работоспособных соединителей. Соединители, которые вы еще не настроили, отображаются последними.

**Состояние соединителя**.
- **Неработоспособный**.
    - Истек срок действия сертификата или учетных данных.
    - Последняя синхронизация была не меньше трех дней назад.
- **Внимание!**
    - Срок действия сертификата или учетных данных истекает в течение семи дней.
    - Последняя синхронизация была более одного дня назад.
- **Работоспособный**.
    - Срок действия сертификата или учетных данных не истекает в течение следующих семи дней.
    - Последняя синхронизация была более одного дня назад.  

При выборе соединителя в списке появится страница портала, относящаяся к созданию или настройке этого соединителя.  Например, при выборе соединителя **Дата окончания срока действия VPP** откроется страница **Токены iOS Volume-Purchased Program**, где можно просмотреть дополнительные сведения о соединителе. Затем можно создать новую конфигурацию или изменить готовую и устранить в ней проблемы.  

## <a name="intune-service-health"></a>Работоспособность службы Intune.  
Без необходимости перехода к панели мониторинга работоспособности службы Microsoft 365 или центру сообщений можно просмотреть подробные сведения об активных инцидентах и рекомендации, расположенные в центре администрирования Microsoft 365 в https://portal.office.com. Отображаются только инциденты, которые ранее затрагивали ваш клиент.  

При выборе инцидента непосредственно на странице состояния клиента будут представлены сведения об инциденте. Чтобы просмотреть прошлые рекомендации и инциденты, выберите команду **Показать прошлые инциденты и рекомендации**. Откроется центр администрирования Microsoft 365, где можно просмотреть рекомендации и инциденты за последние 30 дней для вашего клиента.  

Для просмотра сведений о *работоспособности службы Intune* учетная запись должна иметь роль **глобального администратора** или **администратора службы** в Azure Active Directory или на портале администрирования Office. Чтобы назначить эти разрешения, перейдите в [Центр администрирования Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) с разрешениями глобального администратора. Выберите пункты **Пользователи > Активные пользователи**, а затем выберите учетную запись, которой требуется доступ. Выберите **Изменить** для ролей, роль *администратора службы* или *глобального администратора*, а затем нажмите **Сохранить** для назначения разрешения.  

Настроить параметры связи для службы работоспособности служб Intune можно только через Центр администрирования Microsoft 365.

## <a name="intune-news"></a>Новости Intune.  
Просмотр информационных сообщений от команды разработчиков службы Intune без необходимости переходить в центре сообщений Office. Они включают сообщения об изменениях, недавно произошедших в службе Intune или еще только предстоящих для вашего клиента.  

По умолчанию отображаются последние 10 активных сообщений. Чтобы просмотреть более старые сообщения, выберите **Показать прошлые сообщения**, чтобы открыть *центр сообщений* на портале центра администрирования Microsoft 365.  

Для просмотра сведений о новостях Intune учетная запись должна иметь роль **глобального администратора** или **администратора службы** в Azure Active Directory или на портале администрирования Office, либо же иметь роль **читателя центра сообщений** на портале администрирования Office.  Чтобы назначить эти разрешения, перейдите в [Центр администрирования Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) с разрешениями администратора. Выберите пункты **Пользователи > Активные пользователи**, а затем выберите учетную запись, которой требуется доступ. Выберите **Изменить** для *ролей*, роль *администратора сообщений группы*, а затем нажмите **Сохранить** для назначения разрешения.  

Настроить параметры связи для новостей Intune можно только через Центр администрирования Microsoft 365.