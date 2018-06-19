---
title: Защита Dynamics CRM Online
description: Защита и контроль доступа к Dynamics CRM Online с помощью условного доступа.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e2f720c8a6613884397111c2a421fa1cfdc0eb53
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31021801"
---
# <a name="protect-access-to-dynamics-crm-online-with-intune"></a>Защита доступа к Dynamics CRM Online при помощи Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Доступом к Microsoft Dynamics CRM Online можно управлять с устройств с iOS и Android с помощью условного доступа Microsoft Intune.  Условный доступ Intune включает два компонента:
* [Политика соответствия устройств](introduction-to-device-compliance-policies-in-microsoft-intune.md), которой устройства должны удовлетворять, чтобы считаться соответствующими.
* [Политика условного доступа](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), где указываются условия, которым должно удовлетворять устройство для доступа к службе.

Дополнительные сведения о принципах работы условного доступа см. в статье [Защита доступа к электронной почте, Office 365 и другим службам](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!IMPORTANT]
> Для развертывания условного доступа нужны подписки на Intune и Azure Active Directory Premium; при этом пользователям нужны лицензии на оба продукта. **Подписка Enterprise Mobility + Security (EMS)** включает подписки Intune и Azure Active Directory Premium. Дополнительные сведения см. на странице [Цены Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing). Если у вас нет подписки EMS, можно получить подписку для Azure Active Directory Premium. См. [Цены Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

Когда целевой пользователь пытается использовать приложение Dynamics CRM на своем устройстве, выполняется следующая оценка:

![На схеме показаны точки принятия решений, используемые для выбора между разрешением доступа устройства к службе и его блокировкой.](../media/mdm-ca-dynamics-crm-flow-diagram.png)

Устройство, которому требуется доступ к Dynamics CRM Online, должно соответствовать следующим условиям:
* устройство должно относиться к платформе **Android** или **iOS**;
* оно должно быть **зарегистрировано** в Intune;
* оно должно **удовлетворять** всем развернутым политикам соответствия Intune.

Состояние устройства хранится в службе Azure Active Directory, которая предоставляет или блокирует доступ на основе указанных условий.

Если условие не выполняется, при входе пользователь получает одно из следующих сообщений:
* Если устройство не зарегистрировано в Intune либо в Azure Active Directory, выводится сообщение с инструкциями о том, как установить приложение корпоративного портала и выполнить регистрацию.
* Если устройство не соответствует требованиям, отображается сообщение, направляющее пользователя на веб-сайт корпоративного портала Microsoft Intune или к приложению корпоративного портала Intune, где можно найти сведения о данной проблеме и способах ее устранения.

## <a name="configure-conditional-access-for-dynamics-crm-online"></a>Настройка условного доступа для Dynamics CRM Online  
### <a name="step-1-configure-active-directory-security-groups"></a>Шаг 1. Настройка групп безопасности Active Directory

Прежде чем начать, настройте политику условного доступа в группах безопасности Azure Active Directory. Эти группы можно настроить в **Центре администрирования Office 365**. Они используются для назначения пользователей политике или исключения их из нее. Если на пользователя распространяется действие политики, каждое используемое им устройство должно соответствовать этой политике, чтобы он мог получить доступ к ресурсам.

Для политики Dynamics CRM Online можно указать два типа групп:
* **Целевые группы**. Содержит группы пользователей, к которым применяется политика.
* **Исключенные группы**. Содержит группы пользователей, которые исключены из политики.

Если пользователь входит в обе группы, то он будет исключен из политики.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Шаг 2. Настройка и развертывание политики соответствия требованиям
[Создайте](create-a-device-compliance-policy-in-microsoft-intune.md) политику соответствия и [разверните](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) ее для всех устройств, которые она будет затрагивать. Это все устройства, которые используются пользователями в целевых группах.

> [!NOTE]
> Политики соответствия развертываются в группах Intune, тогда как политики условного доступа нацелены на группы безопасности Azure Active Directory.

> [!IMPORTANT]
> Если политика соответствия не развернута, устройства считаются соответствующими.

Когда будете готовы, перейдите к шагу 3.
### <a name="step-3-configure-the-dynamics-crm-policy"></a>Шаг 3. Настройка политики Dynamics CRM
Далее настройте в политике требование, разрешающее доступ к Dynamics CRM только для управляемых и соответствующих политикам устройств. Эта политика будет храниться в Azure Active Directory.

1. В консоли администрирования Intune последовательно выберите пункты **Политика > Условный доступ > Политика Dynamics CRM Online**.

   ![Снимок экрана со страницей политики условного доступа Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2. Выберите политику **Включить условный доступ**.
3. В разделе **Доступ приложения**  можно выбрать область применения политики условного доступа:
   * **iOS**
   * **Android**
4. В разделе **Целевые группы** нажмите кнопку **Изменить**, чтобы выбрать группы безопасности Azure Active Directory, к которым будет применена политика. В качестве целевой аудитории можно выбрать всех пользователей или отдельные группы пользователей.
5. Дополнительно в разделе **Исключенные группы** можно нажать кнопку **Изменить**, чтобы выбрать группы безопасности Azure Active Directory, которые будут исключены из этой политики.
6. По завершении нажмите кнопку **Сохранить**.

Настройка условного доступа для Dynamics CRM выполнена. Развертывать политику условного доступа не нужно; она вступает в силу немедленно.
##  <a name="monitor-the-compliance-and-conditional-access-policies"></a>Мониторинг соответствия и политик условного доступа

В рабочей области **Группы** вы можете просмотреть состояние условного доступа своих устройств.

Выберите любую группу мобильных устройств, а затем на вкладке **Устройства** выберите один из следующих **фильтров**.
* **Устройства, не зарегистрированные в AAD**. Эти устройства заблокированы в Dynamics CRM.
* **Устройства, не соответствующие условиям**. Эти устройства заблокированы в Dynamics CRM.
* **Устройства, соответствующие условиям и зарегистрированные в AAD**. Эти устройства могут получать доступ к Dynamics CRM.

##  <a name="next-steps"></a>Дальнейшие шаги
* [Защита доступа к Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [Защита доступа к локальной организации Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [Защита доступа к SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [Защита доступа к Skype для бизнеса Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
