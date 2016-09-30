---
title: "Ограничение доступа с помощью функции защиты от угроз мобильных устройств | Microsoft Intune"
description: "Ограничение доступа к ресурсам организации на основании риска для устройства, сети и приложений."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c3cf5e6b32ad24d4972fd147331dda7d2d43e8c6
ms.openlocfilehash: d4eadb73aac14a375f41c434a4303a885bfbae64


---

# Ограничение доступа к ресурсам организации на основании риска для устройства, сети и приложений
Вы можете управлять доступом к корпоративным ресурсам с мобильных устройств на основании оценки рисков, проведенной Lookout, решением защиты от угроз на мобильных устройствах (MTP), интегрированным с Microsoft Intune. Данные оценки рисков основаны на данных телеметрии, которые служба Lookout MTP собирает с устройств для выявления уязвимостей операционных систем, установленных вредоносных приложений и сетевых профилей. На основании оценки рисков можно настроить политики условного доступа в Intune и разрешить или блокировать устройства, которые были определены как несоответствующие из-за угроз, обнаруженных на этих устройствах.  В настоящее время эта функция поддерживается только для устройств **Android** под управлением **версии 4.1 и выше**, зарегистрированных в Microsoft Intune.  
## Какие проблемы это решает?
Организациям необходимо защищать конфиденциальные данные от новых угроз, включающих физические, основанные на приложениях и сетевые угрозы, а также уязвимости операционной системы.

Исторически сложилось так, что организации ведут активную работу по защите компьютеров от вредоносных атак. Мобильные устройства — это новая составляющая инфраструктуры, которая часто остается незащищенной. Хотя мобильные платформы включают встроенную защиту операционной системы с помощью таких методов, как изоляция приложений и проверка приложений для пользователей в магазинах, эти платформы остаются уязвимыми для сложных атак. Учитывая тот факт, что мобильные устройства все чаще используются сотрудниками для работы и получения доступа к информации, которая может являться ценной и конфиденциальной, эти устройства должны быть защищены от различных сложных атак.

Intune дает вам возможность управлять доступом к ресурсам организации и данным на основании оценки рисков, проводимой решениями MTP, такими как Lookout.

## Как Intune и Lookout MTP помогают защитить ресурсы организации?
Приложение Lookout (Lookout for Work), работающее на мобильных устройствах, регистрирует сведения о файловой системе и сетевом стеке, а также данные телеметрии устройства и приложений (при наличии) и отправляет их в облачную службу Lookout MTP для вычисления совокупного риска в отношении угроз для мобильных устройств. Вы также можете изменить классификацию уровня риска угроз в консоли MTP, исходя из ваших потребностей.  
Политики соответствия в Intune теперь включают новое правило для защиты мобильных угроз Lookout, основанное на оценке рисков Lookout MTP. При включении этого правила Microsoft Intune оценивает соответствие устройства заданной политике.

Если устройство определяется как несоответствующее требованиям политики, можно заблокировать его доступ к ресурсам, например к Exchange Online и SharePoint Online, с помощью политик условного доступа. При блокировании доступа конечным пользователям предоставляется пошаговое руководство, которое помогает устранить проблему и возобновить доступ к ресурсам организации. Это пошаговое руководство запускается в приложении Lookout for Work.

## Примеры сценариев
Ниже приведены некоторые распространенные сценарии.
### Угроза со стороны вредоносных приложений
При обнаружении на устройстве вредоносных программ вы можете заблокировать для таких устройств:
* подключение к корпоративной электронной почте до устранения угроз;
* синхронизацию корпоративных файлов с помощью приложения OneDrive для работы;
* доступ к критически важным бизнес-приложениям.

**Блокирование доступа при обнаружении вредоносных приложений:**
![схема, демонстрирующая блокирование доступа политикой условного доступа при определении устройства как несоответствующего из-за наличия на нем вредоносных программ](../media/mtp/malicious-apps-blocked.png)

**Устройство разблокировано и может получать доступ к ресурсам организации после устранения угрозы:**

![схема, демонстрирующая предоставление доступа политикой условного доступа, когда устройство определяется как соответствующее после устранения угрозы](../media/mtp/malicious-apps-unblocked.png)
### Угроза безопасности сети
Обнаружение угроз для вашей сети, таких как атаки "злоумышленник в середине", и ограничение доступа к сети Wi-Fi на основании риска для устройства.

**Блокирование доступа к сети через Wi-Fi:**
![схема, демонстрирующая блокирование доступа Wi-Fi политикой условного доступа при обнаружении сетевых угроз](../media/mtp/network-wifi-blocked.png)

**Доступ предоставлен после устранения угрозы:**

![схема, демонстрирующая предоставление доступа политикой условного доступа после устранения угрозы](../media/mtp/network-wifi-unblocked.png)
### Угроза безопасности сети (блокирование доступа к SharePoint Online)

Обнаружение угроз для вашей сети, таких как атаки "злоумышленник в середине", и блокирование синхронизации корпоративных файлов на основании риска для устройства.

**Блокирование доступа к SharePoint Online из-за сетевой угрозы, обнаруженной на устройстве:**

![схема, демонстрирующая блокирование доступа устройства к SharePoint Online политикой условного доступа из-за обнаруженной угрозы](../media/mtp/network-spo-blocked.png)


**Доступ предоставлен после устранения угрозы:**

![схема, демонстрирующая предоставление доступа политикой условного доступа после устранения сетевой угрозы](../media/mtp/network-spo-unblocked.png)

## Дальнейшие шаги
Ниже приведены основные шаги, которые необходимо выполнить для реализации этого решения.
1.  [Настройка службы Lookout MTP в подписке](set-up-your-subscription-with-lookout-mtp.md)
2.  [Включение подключения Lookout MTP в Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Настройка и развертывание приложения Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Настройка политики соответствия требованиям](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Устранение неполадок интеграции Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Sep16_HO3-->

