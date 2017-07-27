---
title: "Регистрация для использования 30-дневной бесплатной пробной версии Microsoft Intune"
titleSuffix: 
description: "Регистрация для использования 30-дневной бесплатной пробной версии Microsoft Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: 
ms.openlocfilehash: de86b6c9938d4be3f90d62e96080d8b967886792
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2017
---
# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Регистрация для использования бесплатной пробной версии Microsoft Intune


В этой статье рассматривается регистрация для использования пробной версии Intune для работы с порталом Azure.

1. На странице [регистрации в Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) заполните форму регистрации для работы с пробной подпиской.
* Если для пробной версии Intune вы хотите использовать имеющуюся рабочую или учебную учетную запись, следуйте [этим инструкциям по входу](/intune/account-sign-up).

* Если большая часть ваших ИТ-операций и пользователей поддерживают региональные параметры, отличные от ваших, эти параметры можно задать в раскрывающемся списке **Where's your company located?** (Где расположена ваша компания?).

2. По завершении регистрации вы получаете сообщение со сведениями о новой учетной записи. <br/> ![Изображение со сведениями об учетной записи](./media/2-end-of-sign-up-process.png) <br/>Если на этом этапе щелкнуть **Можно начинать**, вы перейдете в Центр администрирования Office 365, где можно добавить пользователей в свою тестовую среду. <br/><br/>Однако если вы хотите перейти непосредственно на портал Intune Azure, откройте новое окно браузера и введите в адресную строку **https://portal.azure.com**. Вы переходите на страницу входа Azure, где нужно использовать предоставленные учетные данные для входа. Используйте этот адрес для входа в пробную версию Intune. <br/> ![Изображение страницы входа на портал Azure](./media/azure-portal-signin.png)

При выполнении первого входа на портал Intune Azure Intune может не отображаться на панели мониторинга Azure. Чтобы добавить службу Intune на панель мониторинга Azure, сделайте следующее:
1. В списке служб Azure слева от панели мониторинга выберите **Больше служб** и в поле поиска введите **Intune**.
2. Выберите **Intune** в списке и звездочку, чтобы добавить службу в список служб.<br/> ![Изображение с выбором Intune из списка служб](./media/azure-add-intune1.png)
3. Затем выберите **Intune** в списке служб, чтобы открыть панель мониторинга Intune.

При регистрации для использования пробной версии на электронный адрес, указанный в процессе регистрации, отправляется сообщение с информацией об учетной записи. Оно является подтверждением активации пробной версии.



## <a name="keeping-the-admin-experiences-straight"></a>Удобство работы администратора


Для работы с порталом Intune Azure используются три портала.
- Панель мониторинга Intune в Azure ([portal.azure.com](https://portal.azure.com)), где можно просматривать [возможности Intune на портале Azure](what-is-intune.md).
- Центр администрирования Office 365 ([portal.office.com](https://portal.office.com)), где можно добавлять пользователей и управлять ими, если для этого не используется Azure Active Directory. Здесь также можно управлять и другими функциями учетной записи, включая выставление счетов и предоставление поддержки.
- Классическая консоль администрирования Intune ([manage.microsoft.com](https://manage.microsoft.com)), где можно просматривать функции, которые еще не были добавлены в Azure.

Как правило, все действия выполняются в панели мониторинга Intune, приведенной ниже. Это сайт, где осуществляется настройка групп, политик, устройств и приложений и управление ими.

Вы можете перейти в классическую консоль администрирования Intune из панели мониторинга, выбрав элемент **Классический портал** в верхней ее части.

Чтобы вернуться на портал Intune Azure, введите https://portal.azure.com в адресной строке браузера и снова выберите **Intune** в списке служб.

 ![Изображение панели мониторинга Intune](./media/intune-azure-dashboard.png)


Для добавления пользователей и управления ими и другими аспектами вашей учетной записи, включая выставление счетов и поддержку, используется показанный ниже Центр администрирования Office 365.

![Изображение Центра администрирования Office 365](./media/office-admin-center.png)

Чтобы перейти из центра администрирования Office 365 к панели мониторинга Intune, введите https://portal.azure.com в адресной строке браузера. Выберите **Intune** в списке служб.

Чтобы вернуться из Intune в центр администрирования Office 365, введите https://portal.office.com. Если вы уже выполнили вход в Intune, вы перенаправляетесь непосредственно в центр администрирования Office 365.

## <a name="next-steps"></a>Дальнейшие действия

### <a name="intune-on-azure"></a>Intune на портале Azure
Дополнительные сведения об [Intune на портале Azure](what-is-intune.md)

### <a name="integration-with-other-products"></a>Интеграция с другими продуктами
Дополнительные сведения об использовании учетных записей пользователей Azure Active Directory в Intune:
- [Требования к удостоверениям](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Требования к синхронизации каталогов](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Требования к многофакторной идентификации](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Дополнительные сведения об использовании [Intune с System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)
