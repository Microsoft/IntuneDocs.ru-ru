---
title: Использование базовых показателей безопасности в Microsoft Intune в Azure | Документация Майкрософт
description: Чтобы управлять мобильными устройствами, добавьте или настройте рекомендуемые параметры безопасности группы для защиты пользователей и данных на устройствах с помощью Microsoft Intune. Включите BitLocker, настройте Расширенную защиту от угроз в Защитнике Windows, управляйте Internet Explorer, используйте Smart Screen, устанавливайте локальные политики безопасности, запрашивайте пароль, блокируйте загрузки через Интернет и многое другое.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d78adf8e7d6d2ce05951171e6248dcc8c389945d
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55070298"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Создание базовых показателей безопасности Windows 10 в Intune

Базовые показатели безопасности — это функция предварительной версии, доступная для устройств под управлением Windows 10 и более поздних версий. Эта функция включает в себя множество настроек Intune, которые помогают защитить ваших пользователей и устройства. Она также автоматически устанавливает значения для этих параметров, рекомендуемые командами безопасности. Например, базовый показатель автоматически включает BitLocker, запрашивает пароль для разблокировки устройства, отключает базовую проверку и многое другое.

Данная функция применяется к:

- Windows 10 версии 1809 и более поздние версии​

> [!NOTE]
> Пока базовые показатели безопасности находятся в предварительной версии, корпорация Майкрософт не рекомендует использовать профили в рабочей среде, поскольку базовые показатели могут изменяться в течение предварительной версии.

Целью использования базовых показателей безопасности является обеспечение сквозного безопасного рабочего процесса при работе с Microsoft 365. Ниже перечислены некоторые преимущества.

- Базовые показатели безопасности включают лучшие практики и рекомендации по настройкам, влияющим на безопасность. Intune сотрудничает с той же группой безопасности Windows, которая создает базовые показатели безопасности групповой политики. Эти рекомендации основаны на руководстве и обширном опыте.
- Если вы новичок в Intune и не знаете, с чего начать, базовые показатели безопасности дадут вам преимущество. Вы можете быстро создавать и развертывать профиль безопасности, зная, что ресурсы и данные вашей организации защищены.
- Если вы сейчас используете групповую политику, с этими базовыми показателями перейти на Intune для управления будет намного проще. Базовые показатели изначально встроены в Intune, а также включают современные принципы управления.

Базовые показатели безопасности создают "профиль конфигурации" в Intune. Этот профиль включает все параметры в базовых показателях. Затем примените или назначьте этот профиль для пользователей, групп и устройств.

После того как профиль назначен, вы можете его отслеживать, а также контролировать базовые показатели. Например, вы можете видеть, какие устройства соответствуют базовым показателям, а какие — нет.

В этой статье показано, как использовать базовые показатели безопасности для создания, назначения и мониторинга профиля.

Статья [Базовые параметры безопасности Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) является превосходным ресурсом для получения дополнительных сведений об этой функции. [Управление мобильными устройствами](https://docs.microsoft.com/windows/client-management/mdm/) — отличный ресурс со сведениями о MDM и о том, что вы можете делать на устройствах Windows.

## <a name="co-managed-devices"></a>Совместно управляемые устройства

Базовые показатели безопасности на устройствах, управляемых Intune, аналогичны совместно управляемым устройствам с Configuration Manager. Совместно управляемые устройства используют System Center Configuration Manager и Microsoft Intune для одновременного управления устройствами Windows 10. Это позволяет вам присоединить ваши существующие инвестиции в Configuration Manager к преимуществам Intune. Статья [Что такое совместное управление?](https://docs.microsoft.com/sccm/comanage/overview) является превосходным ресурсом в том случае, если вы используете Configuration Manager, а также хотите воспользоваться преимуществами облака.

При использовании совместно управляемых устройств необходимо переключить рабочую нагрузку **конфигурации устройства** (его параметры) на Intune. Дополнительные сведения предоставлены в разделе [Конфигурация устройства](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration).

## <a name="create-the-profile"></a>Создание профиля

1. На [портале Azure](https://portal.azure.com/) выберите **Все службы** > отфильтруйте список по **Intune** > выберите **Intune**.
2. Выберите **Базовые требования безопасности (предварительная версия)**. Список доступных базовых показателей. Поскольку добавлены дополнительные базовые показатели, вы увидите их ниже.

    ![См. список доступных сейчас базовых показателей безопасности в Intune.](./media/security-baselines/available-baselines.png)

3. Выберите базовые показатели, которые необходимо использовать, затем — **Создать профиль**.
4. В разделе **Основные** укажите следующие свойства.

    - **Имя**. Введите имя для профиля базовых показателей безопасности. Например, введите `pilot Windows 10 MDM baseline - Oct 2018`.
    - **Описание** Введите текст, описывающий назначение этих базовых показателей. Описание предназначено для того, чтобы вы вводили любой текст. Это необязательно, но определенно рекомендуется.

5. Разверните **Параметры**. В списке вы видите все параметры в этих базовых показателях безопасности и то, для чего этот параметр устанавливается автоматически. Рекомендуется использовать параметры и их значения, а также вы можете их изменить.

    ![Разверните параметры, чтобы увидеть все параметры в этих базовых показателях безопасности в Intune.](./media/security-baselines/sample-list-of-settings.png)

    Разверните некоторые параметры, чтобы проверить их значения. Например, разверните **Защитник Windows**. Обратите внимание на некоторые параметры и их настройки.

    ![Посмотрите автоматическое установление некоторых параметров Защитника Windows в Intune](./media/security-baselines/expand-windows-defender.png)

6. **Создайте** профиль. 
7. Выберите **Профили**. Созданный вами профиль отобразится в списке. Но он пока не активен. Далее вам нужно назначить профиль.

## <a name="assign-the-profile"></a>Назначение профиля

Созданный профиль готов к назначению пользователям, устройствам и группам. После назначения профиль и его настройки применяются к выбранным вами пользователям, устройствам и группам.

1. В Intune выберите **Security Baselines** (Базовые показатели безопасности), затем выберите базовые показатели, а затем — **Профили**.
2. Выберите свой профиль, а затем — **Назначения**.

    ![Выберите профиль базовой конфигурации в Intune и щелкните назначения для развертывания профиля.](./media/security-baselines/assignments.png)

3. На вкладке **Включить** добавьте группы, пользователей или устройства, к которым необходимо применить эту политику.

    > [!TIP]
    > Обратите внимание, что вы также можете **Исключить** группы. Если применять политику ко **всем пользователям**, рекомендуется исключить группы администраторов. Если что-то случится, вы и ваши администраторы не захотите, чтобы вас заблокировали.

4. **Сохраните** внесенные изменения.

После сохранения профиль отправляют на устройства, когда они возвращаются с Intune. Таким образом это может произойти сразу.

## <a name="q--a"></a>Вопросы и ответы

#### <a name="why-these-settings"></a>Почему именно эти параметры?

Группа безопасности Майкрософт имеет многолетний опыт работы с разработчиками Windows и сообществом по безопасности для создания этих рекомендаций. Параметры этих базовых показателей считаются наиболее важными параметрами конфигурации, связанными с безопасностью. В каждой новой сборке Windows команда корректирует свои рекомендации на основе новых функций.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Есть ли разница в рекомендациях для базовых показателей системы безопасности Windows для групповой политики или Intune?

Та же группа безопасности Майкрософт выбрала и настроила параметры для каждого базового показателя. Intune включает все соответствующие параметры в базовых показателях системы безопасности Intune. В базовых показателях групповой политики есть некоторые параметры, характерные для локального контроллера домена. Эти параметры исключены из рекомендаций Intune. Все остальные параметры одинаковы.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Соответствуют ли базовые конфигурации безопасности Intune требованиям CIS или NSIT?

Строго говоря, нет. Чтобы составить свои рекомендации, группа безопасности Майкрософт консультируется с организациями, например с CIS. Но не существует однозначного сопоставления между базовыми показателями "CIS-совместимыми" и Майкрософт.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Какие сертификаты имеет базовые показатели безопасности Майкрософт? 

- Корпорация Майкрософт продолжает публиковать базовые показатели безопасности для объектов групповой политики и [средств соответствия безопасности](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10) на протяжении уже многих лет. Эти базовые показатели используются многими организациями. Рекомендации в этих базовых показателях основаны на взаимодействии группы безопасности Майкрософт с корпоративными клиентами и внешними агентствами, включая Министерство обороны (DoD), Национальный институт стандартов и технологий (NIST) и другие. Мы делимся нашими рекомендациями и базовыми показателями с этими организациями. Эти организации также имеют свои собственные рекомендации, которые очень похожи на рекомендации Майкрософт. Поскольку управление мобильными устройствами продолжает расти в облаке, корпорация Майкрософт разработала эквивалентные рекомендации MDM этих базовых показателей групповой политики. Эти дополнительные базовые показатели встроены в Microsoft Intune и включают отчеты о соответствии для пользователей, групп и устройств, которые соответствуют (или не соответствуют) базовым показателям.

- Многие клиенты используют рекомендации базовых показателей Intune в качестве отправной точки, а затем настраивают их в соответствии со своими требованиями к ИТ и безопасности. **Базовые показатели безопасности MDM** Microsoft Windows 10 RS5 являются первым выпуском. Эти базовые показатели созданы в качестве общей инфраструктуры, которая позволяет клиентам в конечном итоге импортировать другие базовые показатели безопасности на основе CIS, NIST и других стандартов. Сейчас она доступна для Windows и в конечном итоге и для iOS и Android.

- Переход от локальных групповых политик Active Directory к чисто облачному решению с использованием Azure Active Directory (AD) с Microsoft Intune является циклом. Существуют опубликованные сопутствующие объекты групповой политики для гибридных устройств AD и Azure AD, которые помогут в этом. Эти устройства могут получать параметры MDM из облака (Intune) и параметры групповой политики с локальных контроллеров домена по мере необходимости.

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения см. в статье [Monitor the security baseline and profile in Microsoft Intune](security-baselines-monitor.md) (Мониторинг базовых показателей системы безопасности и профиля в Microsoft Intune).