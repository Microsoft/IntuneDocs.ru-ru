---
title: Выборочная очистка данных с помощью действий доступа политики защиты приложений
titleSuffix: Microsoft Intune
description: Узнайте, как выборочно очищать данные с помощью действий доступа политики защиты приложений в Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f422b5619115b44b8d39c2d735f2163c22167f
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138702"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Выборочная очистка данных с помощью действий доступа политики защиты приложений в Intune

С помощью политик защиты приложений в Intune можно настроить параметры, чтобы заблокировать конечным пользователям доступ к корпоративному приложению или учетной записи. Эти параметры связаны с требованиями к доступу и перемещению данных, установленными вашей организацией, например для разблокированных устройств или минимальной версии ОС.
 
Вы можете явным образом выбрать очистку корпоративных данных компании с устройства конечного пользователя в случае несоблюдения этих требований, выбрав соответствующие параметры. Для некоторых параметров можно настроить несколько действий, например, блокировать доступ и очистить данные, в зависимости от значения параметра.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Создание политики защиты приложений с помощью действий доступа

1. Войдите на [портал Azure](https://portal.azure.com).
2. Выберите **Все службы** > **Intune**.  
    Intune находится в разделе **Мониторинг и управление**.
3. На панели **Intune** выберите **Мобильные приложения** > **Политики защиты приложений**.
4. Нажмите **Добавить политику** (можно также изменить существующую политику). 
5. Нажмите **Настроить обязательные параметры**, чтобы открыть список параметров, которые можно настроить для этой политики. 
6. Прокрутите вниз панель "Параметры" до раздела **Действия доступа** с доступной для редактирования таблицей.

    ![Снимок экрана с действиями доступа для защиты приложений Intune](./media/apps-selective-wipe-access-actions01.png)

7. Выберите **Параметр** и введите **Значение**, которому пользователи должны соответствовать для входа в приложение компании. 
8. Выберите **Действие**, которое нужно предпринять, если пользователи не соответствуют вашим требованиям. В некоторых случаях для одного параметра можно настроить несколько действий. Дополнительные сведения см. в статье [Как создать и назначить политики защиты приложений](app-protection-policies.md).

>[!NOTE]
> Чтобы использовать параметр **Модели устройств**, введите список идентификаторов моделей, разделенных точкой с запятой. 

## <a name="policy-settings"></a>Параметры политики 

В таблице параметров политики защиты приложений есть столбцы **Параметр**, **Значение** и **Действие**.

### <a name="ios-policy-settings"></a>Параметры политики iOS
В iOS можно настроить действия для следующих параметров из раскрывающегося списка **Параметр**:
-  Макс. попыток ввода ПИН-кода
-  Период отсрочки в автономном режиме
-  Устройства со снятой защитой или административным доступом
-  Мин. версия ОС
-  Мин. версия приложения
-  Мин. версия пакета SDK
-  Модель устройства

Чтобы использовать параметр **Модели устройств**, введите список идентификаторов моделей iOS через точку с запятой. Идентификатор модели iOS можно найти в столбце "Тип устройства" в [сопроводительной документации HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types).<br>
Пример: *iPhone5,2; iPhone5,3*

На пользовательских устройствах клиент Intune будет выполнять действия на основе простого сопоставления для строк моделей устройств, указанных в Intune для политик защиты приложения. Сопоставление полностью зависит от значения, предоставленного устройством. Вам (или ИТ-администратору) следует удостовериться в желаемом поведении. Для этого проверьте параметр для разных производителей и моделей устройств, применив его к небольшой группе пользователей. Значение по умолчанию: **не настроено**.<br>
Задайте одно из следующих действий. 
- Разрешить указанные (заблокировать неуказанные)
- Разрешить указанные (удалить неуказанные)

**Что произойдет, если ИТ-администратор укажет разные идентификаторы моделей iOS в политиках, назначенных одинаковым приложениям пользователя Intune?**<br>
При возникновении конфликта между настроенными значениями в двух политиках защиты приложений Intune обычно выбирает наиболее строгий подход. Таким образом, итоговая политика, отправляемая в целевое приложение, которое открывает пользователь Intune, будет пересечением указанных идентификаторов моделей iOS в *политике A* и *политике B*, назначенных одному и тому же сочетанию приложения и пользователя. Например, в *политике A* указано "iPhone5,2; iPhone5,3", а в *политике B* — "iPhone5,3". Итоговая политика, назначенная пользователю Intune, указанному в *политике A* и *политике B*, — "iPhone5,3". 

### <a name="android-policy-settings"></a>Параметры политики Android

Для Android можно настроить действия для следующих параметров из раскрывающегося списка **Параметр**:
-  Макс. попыток ввода ПИН-кода
-  Период отсрочки в автономном режиме
-  Устройства со снятой защитой или административным доступом
-  Мин. версия ОС
-  Мин. версия приложения
-  Минимальная версия исправления
-  Производитель устройства

Чтобы использовать параметр **Производители устройств**, введите список производителей Android через точку с запятой. Производитель устройства Android указан в его параметрах.<br>
Пример: *производитель A; производитель B; Google* 

На пользовательских устройствах клиент Intune будет выполнять действия на основе простого сопоставления для строк моделей устройств, указанных в Intune для политик защиты приложения. Сопоставление полностью зависит от значения, предоставленного устройством. Вам (или ИТ-администратору) следует удостовериться в желаемом поведении. Для этого проверьте параметр для разных производителей и моделей устройств, применив его к небольшой группе пользователей. Значение по умолчанию: **не настроено**.<br>
Задайте одно из следующих действий. 
- Разрешить указанные (заблокировать неуказанные)
- Разрешить указанные (удалить неуказанные)

**Что произойдет, если ИТ-администратор укажет разных производителей Android в политиках, назначенных одинаковым приложениям пользователя Intune?**<br>
При возникновении конфликта между настроенными значениями в двух политиках защиты приложений Intune обычно выбирает наиболее строгий подход. Таким образом, итоговая политика, отправляемая в целевое приложение, которое открывает пользователь Intune, будет пересечением указанных производителей Android в *политике A* и *политике B*, назначенных одному и тому же сочетанию приложения и пользователя. Например, в *политике A* указано "Google, Samsung", а в *политике B* — "Google". Итоговая политика, назначенная пользователю Intune, указанному в *политике A* и *политике B*, — "Google". 

### <a name="additional-settings-and-actions"></a>Дополнительные параметры и действия 

По умолчанию в таблице будут заполненные строки для параметров **Автономный льготный период** и **Макс. попыток ввода ПИН-кода**, если для параметра **Требовать ПИН-код для доступа** установлено значение **Да**.
 
Чтобы настроить параметр, выберите его из раскрывающегося списка в столбце **Параметр**. После выбора параметра появится активное текстовое поле в столбце **Значение** в той же строке, если требуется задать значение. Также появится раскрывающийся список в столбце **Действие** с действиями условного запуска для этого параметра. 

Ниже приведены эти действия:
-  **Блокировать доступ** — блокировать пользователю доступ к корпоративному приложению.
-  **Очистить данные** — очистить корпоративные данные с устройства конечного пользователя.
-  **Предупредить** — отобразить диалоговое окно с предупреждающим сообщением.

В некоторых случаях, например для параметра **Мин. версия ОС**, вы можете указать все действия в зависимости от номера версии. 

![Снимок экрана с действиями доступа для защиты приложений Intune — минимальная версия ОС](./media/apps-selective-wipe-access-actions05.png)

Когда вы настроите параметр, строка будет отображаться в режиме только для чтения и будет доступна для изменения в любое время. Кроме того, появится строка с раскрывающимся списком в столбце **Параметр**. Параметры, которые уже были настроены и не допускают несколько действий, не будут доступны для выбора в раскрывающемся списке.

## <a name="next-steps"></a>Дальнейшие шаги

Узнайте больше о политиках защиты приложений в Intune:
- [Как создать и назначить политики защиты приложений](app-protection-policies.md)
- [Параметры политики защиты приложений в iOS](app-protection-policy-settings-ios.md)
- [Параметры политики защиты приложений Android в Microsoft Intune](app-protection-policy-settings-android.md) 

