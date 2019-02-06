---
title: Проверка успешных операций и ошибок базовых показателей безопасности в Microsoft Intune в Azure | Документация Майкрософт
description: Проверьте состояние ошибок, конфликтов и успешности при развертывании базовых показателей безопасности для пользователей и устройств в Microsoft Intune MDM. Дополнительные сведения о том, как устранить неполадки с помощью клиентских журналов и функций отчетов в Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28a98a20e5f0b5181628da46ccd662f1f8f503dd
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55070310"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>Мониторинг базовых показателей безопасности и профиля в Microsoft Intune

Существуют различные параметры мониторинга при использовании базовых показателей системы безопасности. Вы можете отслеживать профиль базовых показателей безопасности, который применяется для пользователей и устройств. Вы также можете отслеживать фактические базовые показатели и любые устройства, которые соответствуют (или не соответствуют) рекомендуемым значениям.

В этой статье рассматриваются оба параметра мониторинга.

Статья [Создание базовых показателей безопасности Windows 10 в Intune](security-baselines.md) предоставляет дополнительные сведения о функции базовых конфигураций системы безопасности в Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Мониторинг базовых показателей и устройств

Контролируя базовые показатели, вы получаете представление о состоянии безопасности ваших устройств на основе рекомендаций Майкрософт.

> [!NOTE]
> После первого назначения базовых показателей обновление отчетов занимает до 24 часов. После этого для обновления необходимо до 6 часов.

1. На [портале Azure](https://portal.azure.com/) выберите **Все службы** > отфильтруйте список по **Intune** > выберите **Intune**.
2. Выберите **Базовые требования безопасности (предварительная версия)**, затем выберите базовые показатели.
3. В разделе **Обзор** график показывает, сколько устройств зависит от выбранных вами базовых показателей, а также различные статусы.

    ![Проверка состояния устройств](./media/security-baselines-monitor/overview.png)

    Доступны следующие состояния:

    - **Matches baseline** (Соответствует базовым показателям). Все параметры в базовых показателях соответствуют рекомендуемым параметрам.
    - **Does not match baseline** (Не соответствует базовым показателям). По крайне мере один параметр в базовых показателях не соответствует рекомендуемым параметрам.
    - **Неправильная конфигурация**. По крайней мере один параметр не настроен должным образом. Этот статус означает, что параметр находится в состоянии конфликта, ошибки или ожидания.
    - **Неприменимо**. По крайней мере один параметр не применяется.

4. Выберите одно из состояний устройств. Например, выберите состояние **Неправильная конфигурация**.

5. Отобразится список всех устройств с таким состоянием. Выберите конкретное устройство для получения дополнительных сведений. 

    В следующем примере выберите **Конфигурация устройства**, а затем выберите профиль с ошибкой.

    ![Проверка состояния устройств](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Выберите профиль "Ошибка". Отобразится список всех параметров в профиле и их состояние. Теперь вы можете прокрутить, чтобы найти параметр, вызывающий ошибку.

    ![Просмотр параметров, вызывающих ошибку](./media/security-baselines-monitor/profile-with-error-status.png)

Используйте этот отчет, чтобы увидеть все параметры в профиле, которые вызывают проблему. Также получите дополнительные сведения о политиках и профилях, развернутых на устройствах.

> [!NOTE]
> Если для свойства задано значение **Не настроено** в базовых показателях, этот параметр игнорируется и никакие ограничения не применяются. Свойство не отображается ни в каких отчетах.

## <a name="monitor-the-profile"></a>Мониторинг профиля

Мониторинг профиля дает вам полезные сведения о состоянии развертывания ваших устройств, но не о состоянии безопасности на основе рекомендаций базовых показателей.

1. В Intune выберите **Security Baselines** (Базовые показатели безопасности), выберите базовые показатели, а затем — **Profiles created** (Созданные профили).

2. Выберите профиль. В разделе **Обзор** на рисунку изображено, сколько устройств и пользователей назначил этот профиль.

    ![Просмотр количества устройств и пользователей, назначенных профилю базовых показателей безопасности.](./media/security-baselines-monitor/existing-profile-overview.png)

3. В разделе **Управление** > **Свойства** отображается список всех настроек в базовых показателях. Вы можете также изменить любой из этих параметров.

    ![Просмотр и изменения параметров профиля базовых показателей безопасности](./media/security-baselines-monitor/manage-settings.png)

4. В разделе **Монитор** вы можете просмотреть состояние развертывания профиля на отдельных устройствах, каждого пользователя и каждого параметра в базовых показателях.

    ![Просмотр различных параметров мониторинга для профиля базовых показателей безопасности](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Устранение неполадок с помощью состояния для отдельных параметров

Вы развернули базовые показатели безопасности, но состояние развертывания отображает ошибку. Следующие шаги дают вам некоторые рекомендации по устранению ошибки.

1. В Intune выберите **Security Baselines** (Базовые показатели безопасности), выберите базовые показатели, а затем — **Profiles created** (Созданные профили).
2. Выберите профиль, затем в разделе **Мониторинг** > **Состояние для отдельных параметров**.
3. В таблице показаны все параметры и их состояние. Выберите столбец **Ошибка** или столбец **Конфликт**, чтобы увидеть параметр, вызвавший ошибку.

### <a name="mdm-diagnostic-information"></a>Диагностическая информация MDM

Теперь вы определили проблемный параметр. Далее необходимо выяснить, почему этот параметр вызывает ошибку или конфликт. 

На устройствах Windows 10 имеется встроенный отчет с диагностической информацией MDM. Этот отчет включает значения по умолчанию, текущие значения, список политик, показывает, развернута ли она на устройстве или у пользователя, и многое другое. Используйте этот отчет, чтобы определить, почему этот параметр является причиной конфликта или ошибки.

1. На устройстве откройте **Настройка** > **Учетные записи** > **Доступ к учетной записи места работы или учебного заведения**.
2. Выберите учетную запись, а затем — **Информация** > **Advanced Diagnostic Report** (Расширенный отчет диагностики)  > **Создать отчет**.
3. Выберите **Экспорт** и откройте созданный файл.
4. В отчете найдите параметр ошибки или конфликта в разных разделах отчета.

  Например, посмотрите раздел **Enrolled configuration sources and target resources** (Зарегистрированные источники конфигурации и целевые ресурсы) или раздел **Unmanaged policies** (Неуправляемые политики). Вы можете понять, почему это вызывает ошибку или конфликт.

Статья [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (Диагностика сбоев MDM в Windows 10) предоставляет дополнительные сведения об этом встроенном отчете.

> [!TIP]
> - Некоторые параметры также перечислены в GUID. Вы можете искать этот GUID в локальном реестре (regedit) для любых установленных значений.
> - Журналы просмотра событий могут также содержать некоторую информацию об ошибках в проблемной настройке (**Просмотр событий** > **Журналы приложений и служб** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **Администратор**).

## <a name="next-steps"></a>Дальнейшие шаги

[Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md) и [Распространенные проблемы с профилями устройств в Microsoft Intune и возможные решения](device-profile-troubleshoot.md).