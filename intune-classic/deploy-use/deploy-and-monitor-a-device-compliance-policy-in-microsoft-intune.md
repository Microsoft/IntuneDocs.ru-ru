---
title: "Развертывание и мониторинг политики соответствия требованиям | Документы Майкрософт"
description: "Воспользуйтесь пошаговыми инструкциями из этого раздела, чтобы развернуть политику соответствия требованиям и следить за ней."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 40826175eb7c71220a521ac45bb8b9b9e84dec4a
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Развертывание и мониторинг политики соответствия устройств в Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Развертывание политики соответствия
Разверните [созданную](create-a-device-compliance-policy-in-microsoft-intune.md) политику соответствия в одной или нескольких группах пользователей в организации. При развертывании политики соответствия для пользователя его устройства проверяются на соответствие.

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.
![Снимок экрана: страница политики соответствия с пунктом меню "Управление развертыванием" в верхней части](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  В диалоговом окне **Управление развертыванием** выберите одну группу (или несколько), в которой нужно развернуть политику, а затем последовательно выберите **Добавить** > **ОК**.
![Снимок экрана с диалоговым окном "Управление развертыванием"](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Используйте группы Active Directory, которые уже созданы и синхронизированы с Intune, или создайте такие группы вручную в консоли Intune. Дополнительные сведения о развертывании политик см. в статье [Развертывание политики конфигурации](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Используйте сводку состояния и оповещения на странице **Обзор** рабочей области **Политика** для выявления проблем с политикой, требующих вашего внимания. Кроме того, сводка состояний отображается в рабочей области **Панель мониторинга** .

> [!IMPORTANT]
> Если политика соответствия не была развернута, а включена политика условного доступа Exchange, доступ будет предоставлен всем целевым устройствам.

## <a name="monitor-the-compliance-policy"></a>Мониторинг политики соответствия

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Просмотр устройств, которые не соответствуют политике соответствия

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Группы** > **Все устройства**.

2.  Дважды щелкните имя устройства в списке.

3.  Откройте вкладку **Политика**, чтобы просмотреть список политик для устройства.

4.  В раскрывающемся списке **Фильтры** выберите **Не согласуется с политикой соответствия**.
![Снимок экрана со списком фильтров](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Просмотр отчетов об аттестации работоспособности

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Отчеты**.

2.  На странице **Health Attestation Report — Create a new report** (Отчет об аттестации работоспособности — создание отчета) можно просмотреть отчет со всеми данными об аттестации работоспособности Windows 10, собранными Intune. Кроме того, вы можете создать отчет с подмножеством данных, используя фильтры. Они могут основываться на типе устройства, операционной системе или определенном подмножестве точек данных.

## <a name="how-intune-resolves-policy-conflicts"></a>Разрешение конфликтов политик в Intune
Конфликты могут возникать из-за применения нескольких политик Intune к устройству. Если параметры политик пересекаются, Intune разрешает конфликты согласно приведенным ниже правилам.

-   Если конфликтуют параметры политики конфигурации Intune и политики соответствия, параметры политики соответствия имеют приоритет над параметрами политики конфигурации. Это происходит, даже если параметры политики конфигурации являются более безопасными.

-   При развертывании нескольких политик соответствия Intune будет использовать наиболее безопасную из них.

## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения об использовании политики соответствия с политиками условного доступа для управления доступом к службам в организации см. в статье [Ограничение доступа к электронной почте и службам Office 365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).


### <a name="see-also"></a>См. также
[Общие сведения о политиках соответствия устройств в Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)
