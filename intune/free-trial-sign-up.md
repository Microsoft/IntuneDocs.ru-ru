---
title: "Зарегистрируйтесь для получения 30-дневной бесплатной пробной версии."
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure. Регистрация для использования Intune в Azure."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3be43e12abc1cf90da3584450ddd56ab63bdfac1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Регистрация для использования бесплатной пробной версии Microsoft Intune для работы с предварительной версией портала Azure

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

В этой статье рассматривается регистрация для использования пробной версии Intune для работы с предварительной версией портала Azure. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. На странице [регистрации в Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) заполните форму регистрации для работы с пробной подпиской.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Изображение страницы регистрации](./media/1-clicking-try.png)

 > [!TIP]
> Если большая часть ваших ИТ-операций и пользователей поддерживают региональные параметры, отличные от ваших, эти параметры можно задать в раскрывающемся списке **Where's your company located?** (Где расположена ваша компания?).

2. По завершении регистрации вы получите сообщение со сведениями о новой учетной записи. <br/> ![Изображение со сведениями об учетной записи](./media/2-end-of-sign-up-process.png) <br/>Если на этом этапе щелкнуть **You're ready to go** (Можно приступать...), вы перейдете в центр администрирования Office 365, где можно добавить пользователей в свою среду тестирования. <br/><br/>Однако, если вы хотите перейти непосредственно в предварительную версию портала Intune Azure, откройте новое окно браузера и введите в адресную строку **https://portal.azure.com**. Вы перейдете на страницу входа Azure, где нужно использовать предоставленные вам учетные данные для входа. Используйте этот адрес для входа в пробную версию Intune. <br/> ![Изображение страницы входа на портал Azure](./media/azure-portal-signin.png)

При выполнении первого входа в предварительную версию Intune Azure, Intune может не отображаться на панели мониторинга Azure. Чтобы добавить службу Intune на панель мониторинга Azure, сделайте следующее:
1. В списке служб Azure слева от панели мониторинга выберите **Больше служб** и в поле поиска введите **Intune**.
2. Выберите **Intune** в списке и звездочку, чтобы добавить службу в список служб.<br/> ![Изображение с выбором Intune из списка служб](./media/azure-add-intune1.png)
3. Затем выберите **Intune** в списке служб, чтобы открыть панель мониторинга Intune.

При регистрации для использования пробной версии на электронный адрес, указанный в процессе регистрации, отправляется сообщение с информацией об учетной записи. Оно является подтверждением активации пробной версии.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Удобство работы администратора
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Для работы с предварительной версией Intune Azure используются три портала:
- Панель мониторинга Intune в Azure ([portal.azure.com](https://portal.azure.com)), где можно просматривать [возможности Intune на портале Azure](what-is-intune.md).
- Центр администрирования Office 365 ([portal.office.com](https://portal.office.com)), где можно добавлять пользователей и управлять ими, если для этого не используется Azure Active Directory. Здесь также можно управлять и другими функциями учетной записи, включая выставление счетов и предоставление поддержки.
- Классическая консоль администрирования Intune ([manage.microsoft.com](https://manage.microsoft.com)), где можно просматривать функции, которые еще не были добавлены в Azure.

Как правило, все действия выполняются в панели мониторинга Intune, приведенной ниже. Это сайт, где осуществляется настройка групп, политик, устройств и приложений и управление ими.

Вы можете перейти в консоль администрирования классической службы Intune из панели мониторинга, выбрав плитку **Открытие классического портала Intune**.

Чтобы вернуться в предварительную версию Intune Azure, введите https://portal.azure.com в адресной строке браузера и снова выберите **Intune** в списке служб.

 ![Изображение панели мониторинга Intune](./media/intune-azure-dashboard.png)


Однако для добавления пользователей и управления ими и другими аспектами вашей учетной записи, включая выставление счетов и поддержку, будет использоваться Центр администрирования Office 365, показанный ниже.

![Изображение Центра администрирования Office 365](./media/office-admin-center.png)

Чтобы перейти из центра администрирования Office 365 к панели мониторинга Intune, введите https://portal.azure.com в адресной строке браузера. Выберите **Intune** в списке служб.

Чтобы вернуться из Intune в центр администрирования Office 365, введите https://portal.office.com. Если вы уже выполнили вход в Intune, вы перенаправляетесь непосредственно в центр администрирования Office 365.

## <a name="next-steps"></a>Дальнейшие действия

### <a name="intune-azure-preview"></a>Предварительная версия Intune Azure
Дополнительные сведения об [Intune в предварительной версии портала Azure](what-is-intune.md)
### <a name="classic-intune"></a>Классическая служба Intune
Сценарий оценки. [Оценка управления мобильными устройствами в Microsoft Intune](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Интеграция с другими продуктами
Дополнительные сведения об использовании учетных записей пользователей Azure Active Directory в Intune:
- [Требования к удостоверениям](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Требования к синхронизации каталогов](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Требования к многофакторной идентификации](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Дополнительные сведения об использовании [Intune с System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)

