---
title: "Регистрация устройств Windows"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: включение управления мобильными устройствами Intune (MDM) для устройств Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/21/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 609656c2831c09c67e911c8150d31f38faad020b
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-windows-devices"></a>Регистрация устройств Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Чтобы настроить регистрацию устройств Windows, воспользуйтесь одним из описанных ниже методов.

- [**Автоматическая регистрация Windows 10 и Windows 10 Mobile с помощью Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium).
 -  Этот метод подходит только для устройств Windows 10 и Windows 10 Mobile.
 -  Для использования этого метода необходима служба Azure Active Directory Premium. Если у вас ее нет, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.
 -  Если вы решили не включать автоматическую регистрацию, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.

- [**Регистрации без автоматической регистрации в Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - Этот метод следует использовать для регистрации устройств Windows 8.1 и Windows Phone 8.1.
 - Этот метод можно использовать для Windows 8.1 и более поздних устройств, если вы не хотите использовать Azure Active Directory (AD) Premium.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Включение регистрации Windows без Azure AD Premium

Вы можете разрешить пользователям устанавливать и регистрировать свои устройства без автоматической регистрации в Azure AD Premium. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера.

1. **Создание записей CNAME** (необязательно)<br>
 Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

    Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии регистрационной записи CNAME пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

    Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

    Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

2.  **Проверка CNAME**<br>На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**. В колонке Intune выберите пункты **Регистрация устройств** > **Регистрация Windows**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

3.  **Сообщите пользователям, как зарегистрировать устройства и что произойдет при управлении ими.**

    Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Вы также можете перенаправить пользователей к статье [Что может видеть ИТ-администратор при регистрации устройства в Intune?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)

    Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

Дополнительные действия требуются только в случае развертывания корпоративного портала на устройствах.  Шаги 2 и 3 в консоли администрирования можно спокойно пропустить.

