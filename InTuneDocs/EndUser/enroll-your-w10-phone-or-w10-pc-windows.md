---
title: "Регистрация устройства с Windows 10 в Intune | Microsoft Intune"
description: "Описывается, как зарегистрировать мобильное или настольное устройство с Windows 10 в Intune."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 06/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02287eb01598c28906045fd8def9e8b4660e3da5
ms.openlocfilehash: 8806231f8d02885a192053a35559694a8984d2f5


---


# Регистрация устройства с ОС Windows 10 Mobile или Windows 10 Desktop в Intune

Если в вашей компании или учебном заведении используется Microsoft Intune, вы можете зарегистрировать свои устройства, чтобы получить доступ к электронной почте, файлам и другим ресурсам организации. Регистрация устройств позволяет организации обеспечить безопасность корпоративных данных. Дополнительные сведения о регистрации см. в статьях [What happens if you install the Company Portal app and enroll your device in Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) (Что произойдет, если установить приложение "Корпоративный портал" и зарегистрировать устройство в Intune?) и [What your IT administrator can and can't see on your device](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) (Что ИТ-администратор может и не может видеть на вашем устройстве).


Чтобы зарегистрировать устройство с ОС Windows 10 Mobile или Windows 10 Desktop, выполните указанные ниже действия.

1.  Перейдите в раздел **Параметры** Windows и нажмите **Учетные записи**.

    ![settings-accounts](./media/w10-enroll-rs1-settings-accounts.png)

2.  Посмотрите на следующие два снимка экрана и выберите тот, который похож на экран вашего устройства. Выполните действия, показанные на выбранном экране.

    Если вы видите этот экран, следуйте инструкциям из раздела [Действия при появлении элемента "Доступ к учетной записи места работы или учебного заведения"](#steps-to-follow-if-you-see-access-work-or-school).

    ![connect-to-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Если вы видите этот экран, следуйте инструкциям из раздела [Действия при появлении элемента "Ваша учетная запись"](#steps-to-follow-if-you-see-your-account).

    ![your-account](./media/w10-enroll-2-accounts-your-account.png)

## Действия при появлении элемента "Доступ к учетной записи места работы или учебного заведения"

1.  Выберите **Доступ к учетной записи места работы или учебного заведения**.

    ![tap-access-work-school-account](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Введите рабочий или учебный адрес электронной почты и выберите **Далее**.

    ![enter-your-work-or-school-account](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Выполните вход в Intune через рабочую или учебную учетную запись.

    ![add-work-school-account](./media/w10-enroll-rs1-enter-your-credentials.png)

    Появится сообщение о том, что устройство регистрируется в вашей компании или учебном заведении.

4. При появлении страницы **Всё готово!** нажмите кнопку **Закрыть**. Все готово.

  ![tap-close-on-you-are-all-set-screen](./media/w10-enroll-rs1-youre-all-set.png)

5. Если вы хотите еще раз убедиться, что подключение установлено правильно, вернитесь в раздел **Параметры**. Ваша рабочая или учебная учетная запись должна появиться в списке.

    ![validate-that-connection-was-set-up-correctly](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Если вы выполнили описанные выше действия, но по-прежнему не можете получить доступ к рабочей или учебной электронной почте и файлам, выполните инструкции из раздела [Устранение неполадок при появлении элемента "Доступ к учетной записи места работы или учебного заведения"](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).


## Действия при появлении элемента "Ваша учетная запись"

1.  Перейдите в раздел **Параметры** Windows и нажмите **Учетные записи**.

    ![go-to-settings-accounts](./media/W10-enroll-1-settings-accounts.png)

2.  Коснитесь **Ваша учетная запись**.

    ![tap-your-account](./media/W10-enroll-2-accounts-your-account.png)

3.  Нажмите **Добавить рабочую или учебную учетную запись**.

    ![add-work-or-school-account](./media/w10-enroll-3-add-work-school-acct.png)

4.  Войдите, используя рабочую или учебную учетную запись.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Если вы выполнили описанные выше действия, но по-прежнему не можете получить доступ к рабочей или учебной электронной почте, файлам и другим данным, выполните инструкции из раздела [Устранение неполадок при появлении элемента "Ваша учетная запись"](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).

Также рекомендуется установить приложение корпоративного портала, которое позволит легко определять и скачивать приложения организации, актуальные для вас и вашей роли. В зависимости от того, как ваша компания настроила Intune, приложение корпоративного портала могло быть установлено в рамках процесса регистрации. Чтобы проверить, есть ли у вас это приложение, найдите **Корпоративный портал** в списке приложений. Если вы не видите корпоративный портал в списке приложений, выполните следующие действия для его установки.

1.  Выберите **Пуск** &gt; **Магазин**.

2.  Нажмите **Поиск** и введите **корпоративный портал**.

3.  В списке результатов нажмите **Корпоративный портал** &gt; **Установить**.

4.  Нажмите **Установить** или **Бесплатно**. Отображаемый параметр зависит от того, как приложение настроено в компании.

По-прежнему нужна помощь? Обратитесь к ИТ-администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).

### См. также
[Использование устройства Windows в Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO3-->


