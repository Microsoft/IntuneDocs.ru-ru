---
title: "Регистрация устройств Windows | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure: включение управления мобильными устройствами Intune (MDM) для устройств Windows."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: ec623e7d102e8a8ddf1cc86a750f592ca765cfce


---

# <a name="enroll-windows-devices"></a>Регистрация устройств Windows 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Чтобы настроить регистрацию устройств Windows, воспользуйтесь одним из описанных ниже методов.

- **[Автоматическая регистрация Windows 10 и Windows 10 Mobile с помощью Azure Active Directory Premium](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Этот метод подходит только для устройств Windows 10 и Windows 10 Mobile.
 -  Для использования этого метода необходима служба Azure Active Directory Premium. Если у вас ее нет, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.
 -  Если вы решили не включать автоматическую регистрацию, используйте метод регистрации для Windows 8.1 и Windows Phone 8.1.


- **[Регистрация Windows 8.1 и Windows Phone 8.1 путем настройки CNAME](#set-up-windows-8.1-and-windows-phone-8.1-enrollment-by-configuring-cname)** 
 - Этот метод следует использовать для регистрации устройств Windows 8.1 и Windows Phone 8.1.


## <a name="prerequisites"></a>Необходимые компоненты

Если некоторых из указанных ниже необходимых компонентов еще нет в предварительной версии Intune Azure, выполните эти действия в классической консоли администрирования Intune.

- [Настройка пользовательского доменного имени](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- Настройка **Microsoft Intune** в качестве [центра управления мобильными устройствами (MDM)](set-mdm-authority.md).
- [Настройка приложения корпоративного портала](/intune-azure/manage-apps/company-portal-app.md)
- Назначение лицензий пользователям

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Настройка регистрации Windows 8.1 и Windows Phone 8.1 путем настройки CNAME

Вы можете разрешить пользователям устанавливать и регистрировать свои устройства с помощью корпоративного портала Intune. Если вы создаете записи ресурсов DNS CNAME, пользователи подключаются к Intune и выполняют регистрацию без ввода имени сервера.

1. **Создание записей CNAME** (необязательно)<br>
 Создайте запись ресурсов **CNAME** DNS для домена вашей организации. Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com.

    Хотя создание записей DNS CNAME и не является обязательным, записи CNAME упрощают регистрацию для пользователей. При отсутствии регистрационной записи CNAME пользователям предлагается вручную ввести имя сервера MDM — enrollment.manage.microsoft.com.

    Если у вас уже есть запись CNAME в службе DNS, которая перенаправляет EnterpriseEnrollment.contoso.com на manage.microsoft.com, предполагается, следует заменить ее записью CNAME в службе DNS, которая перенаправляет EnterpriseEnrollment.contoso.com на enterpriseenrollment-s.manage.microsoft.com. Это рекомендуемое изменение, так как конечная точка manage.microsoft.com в будущем выпуске не будет использоваться для регистрации.

    Если имеется несколько проверенных доменов, создайте запись CNAME для каждого из них. Записи ресурсов CNAME должны содержать следующие сведения:

    Записи ресурсов CNAME должны содержать следующие сведения:

  |ТИП|Имя узла|Указывает на|СРОК ЖИЗНИ|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 час|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 час|

  `EnterpriseEnrollment-s.manage.microsoft.com` — поддерживает перенаправление в службу Intune с распознаванием домена по имени домена электронной почты.

  `EnterpriseRegistration.windows.net` — поддерживает устройства Windows 8.1 и Windows 10 Mobile, которые будут зарегистрированы в Azure Active Directory с помощью рабочей или учебной учетной записи.

  Если ваша организация использует несколько доменов для учетных данных пользователей, создайте записи CNAME для каждого домена.

  Например, если компания имеет веб-сайт contoso.com, необходимо создать запись CNAME в DNS, перенаправляющую EnterpriseEnrollment.contoso.com на EnterpriseEnrollment-s.manage.microsoft.com. Распространение изменений записей DNS может занимать до 72 часов. Вы не можете проверить смену DNS в Intune, пока запись DNS не будет распространена.

2.  **Проверка CNAME**<br>В [консоли администрирования Intune](http://manage.microsoft.com) щелкните **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Windows Phone**. Введите URL-адрес проверенного домена веб-сайта организации в поле **Укажите проверенное имя домена** и нажмите кнопку **Проверить автообнаружение**.

3.  **Дополнительные шаги**<br>Для Windows 10 шаг **Добавление ключей для загрузки неопубликованных приложений** не требуется. <br>Шаг **Отправка сертификата подписи кода** необходим, только если планируется распространять на устройства бизнес-приложения, недоступные в Магазине Windows.

4.  **Сообщите пользователям, как зарегистрировать устройства и что произойдет при управлении ими.**

    Инструкции по регистрации для пользователей см. в статье [Регистрация устройства Windows в Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). Вы также можете перенаправить пользователей к статье [Что может видеть ИТ-администратор при регистрации устройства в Intune?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)

    Дополнительные сведения о задачах пользователей см. в разделе [Ресурсы по пользовательскому интерфейсу Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Дополнительные действия требуются только в случае развертывания корпоративного портала на устройствах.  Шаги 2 и 3 в консоли администрирования можно спокойно пропустить.



<!--HONumber=Feb17_HO2-->


