---
# required metadata

title: Развертывание и мониторинг политики соответствия в Microsoft Intune | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Развертывание и мониторинг политики соответствия устройств в Microsoft Intune
## Развертывание политики соответствия
Разверните [созданную](create-a-device-compliance-policy-in-microsoft-intune.md) политику соответствия в одной или нескольких группах пользователей или устройств в организации.

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.
![Снимок экрана: страница политики соответствия с пунктом меню "Управление развертыванием" в верхней части](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  В диалоговом окне **Управление развертыванием** выберите одну или несколько групп, для которых будет развернута политика, а затем нажмите кнопки **Добавить > ОК**.
![Снимок экрана с диалоговым окном "Управление развертыванием" Политику соответствия можно развернуть для пользователей или устройств. Используйте группы Active Directory, которые уже созданы и синхронизированы с Intune, или создайте такие группы вручную в консоли Intune.

Дополнительные сведения о развертывании политик см. в разделе [Развертывание политики конфигурации](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Используйте сводку состояния и оповещения на странице **Обзор** рабочей области **Политика** для выявления проблем с политикой, требующих вашего внимания.

> [!IMPORTANT]Кроме того, сводка состояний отображается в рабочей области **Панель мониторинга** .

## Если политика соответствия не была развернута и включена политика условного доступа Exchange, доступ будет разрешен всем целевым устройствам.
Разрешение конфликтов политик Intune Конфликты могут возникать из-за применения нескольких политик Intune к устройству.

-   Если параметры политик пересекаются, Intune разрешает конфликты согласно приведенным ниже правилам.

-   Если конфликтуют параметры политики конфигурации Intune и политики соответствия, параметры политики соответствия имеют приоритет над параметрами политики конфигурации, даже если параметры политики конфигурации являются более безопасными.

## При развертывании нескольких политик соответствия будет использоваться наиболее безопасная из них.

#### Мониторинг политики соответствия

1.  Просмотр устройств, которые не соответствуют политике соответствия

2.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Группы > Все устройства**.

3.  Дважды щелкните имя устройства в списке.

4.  Откройте вкладку **Политика**, чтобы просмотреть список политик для устройства.
![В раскрывающемся списке **Фильтры** выберите **Не согласуется с политикой соответствия**.](./media/intune-sa-3e-view-device-noncompliance.png)

#### Снимок экрана со списком фильтров

1.  Просмотр отчетов об аттестации работоспособности

2.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите элемент **Отчеты**. На странице **Health Attestation Report — Create a new report** (Отчет об аттестации работоспособности — создание отчета) можно просмотреть отчет со всеми данными об аттестации работоспособности Windows 10, собранными с помощью Intune. Кроме того, вы можете создать отчет с подмножеством данных, используя фильтры.


## Они могут основываться на типе устройства, операционной системе или определенном подмножестве точек данных.
Дальнейшие действия

[Теперь можно использовать политику соответствия с политиками условного доступа для управления доступом к службам в вашей организации.](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### Ограничение доступа к электронной почте и службам Office 365
[См. также](introduction-to-device-compliance-policies-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->

