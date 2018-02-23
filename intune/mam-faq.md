---
title: "Часто задаваемые вопросы об управлении мобильными приложениями (MAM) и защите приложений"
description: "Эта статья содержит ответы на некоторые часто задаваемые вопросы по управлению мобильными приложениями (MAM) и защите приложений в Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 02/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23ab21e21ff2ffd471523f8132acffd7545358f0
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Часто задаваемые вопросы об управлении мобильными приложениями (MAM) и защите приложений

Эта статья содержит ответы на некоторые часто задаваемые вопросы по управлению мобильными приложениями (MAM) и защите приложений в Intune.

## <a name="mam-basics"></a>Основы MAM


**Что такое MAM?** [Управление мобильными приложениями (MAM) в Intune](/intune/app-lifecycle) — это набор функций управления, позволяющих публиковать, отправлять, настраивать, защищать, отслеживать и обновлять мобильные приложения для пользователей.

**Каковы преимущества защиты приложений, обеспечиваемой MAM?** MAM защищает корпоративные данные в самом приложении. С помощью MAM без регистрации (MAM-WE) вы можете управлять рабочими или учебными приложениями, которые содержат конфиденциальные данные, практически с любого устройства, включая личные устройства в рамках сценария BYOD. Intune MAM позволяет управлять многими бизнес-приложениями, включая программы Microsoft Office. См. официальный список общедоступных [управляемых приложений Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

**Какие конфигурации устройств поддерживает MAM?** Intune MAM поддерживает две конфигурации.
- **Intune MDM и MAM**. ИТ-администраторы могут управлять приложениями только с помощью MAM и политик защиты приложений на устройствах, зарегистрированных с использованием управления мобильными устройствами Intune (MDM). Для управления приложениями с помощью MDM и MAM следует использовать консоль Intune, которая доступна на портале Azure по адресу https://portal.azure.com.

- **MAM без регистрации устройства**. MAM без регистрации устройства (MAM-WE) позволяет ИТ-администраторам управлять приложениями с помощью MAM и политик защиты приложений на устройствах, не зарегистрированных с использованием Intune MDM. Это означает, что приложениями можно управлять в Intune на устройствах, зарегистрированных с использованием сторонних поставщиков EMM. Для управления приложениями с помощью MAM-WE следует использовать консоль Intune, которую можно найти на портале Azure по адресу http://portal.azure.com. Кроме того, приложениями можно управлять в Intune на устройствах, зарегистрированных с использованием сторонних поставщиков EMM (Enterprise Mobility Management) или вовсе не зарегистрированных в MDM.


## <a name="app-protection-policies"></a>Политики защиты приложений

**Что такое политики защиты приложений?** Политики защиты приложений — это правила, которые обеспечивают защиту корпоративных данных (включая те, которые хранятся в управляемых приложениях). Политика может быть либо правилом, которое применяется, когда пользователь пытается получить доступ или переместить корпоративные данные, либо набором действий, которые запрещено выполнять или которые отслеживаются, когда пользователь работает с приложением.

**Каковы примеры политики защиты приложений?** Дополнительные сведения обо всех параметрах политики защиты приложений см. в статьях [Параметры политики управления мобильными приложениями в Microsoft Intune](app-protection-policy-settings-android.md) и [Параметры политики управления мобильными приложениями iOS](app-protection-policy-settings-ios.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Приложения, которыми можно управлять с помощью политик защиты приложений

**Какими приложениями можно управлять с помощью политик защиты приложений?** Любым приложением, которое интегрировано с [пакетом SDK для приложений Intune](/intune/app-sdk) или упаковано с помощью [инструмента упаковки для приложений Intune](/intune/apps-prepare-mobile-application-management), можно управлять с помощью политик защиты приложений Intune. См. официальный список общедоступных [управляемых приложений Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

**Каковы базовые требования к управляемым приложениям Intune для использования политик защиты приложений?**
- У пользователя должна быть учетная запись Azure Active Directory (AAD). Дополнительные сведения о создании пользователей Intune в Azure Active Directory см. в статье [Добавление пользователей и предоставление административного разрешения для Intune](/intune/users-permissions-add).

- У пользователя должна быть лицензию Microsoft Intune, назначенную его учетной записи Azure Active Directory. Дополнительные сведения о назначении лицензий Intune пользователям см. в статье [Назначение лицензий Intune учетным записям пользователей](/intune/licenses-assign).

- Пользователь должен быть включен в группу безопасности, на которую распространяется политика защиты приложений. Эта же политика защиты приложений должна распространяться и на определенное используемое приложение. Политики защиты приложений можно создавать и развертывать в консоли Intune на [портале Azure](http://portal.azure.com). Сейчас группы безопасности можно создавать на [портале Office](http://portal.office.com).

- Пользователь должен войти в приложение, используя свою учетную запись AAD.

**Каковы дополнительные требования к использованию [мобильного приложения Outlook](https://products.office.com/outlook)?**

- На устройстве пользователя должно быть установлено мобильное приложение Outlook.

- У пользователя должны быть почтовый ящик [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) и лицензия, связанная с учетной записью Azure Active Directory.

  >[!NOTE]
  > Мобильное приложение Outlook сейчас поддерживает только службу Microsoft Exchange Online, но не локальную службу Exchange или Exchange в Office 365 Dedicated.

**Каковы дополнительные требования к использованию приложений [Word, Excel и PowerPoint](https://products.office.com/business/office)?**

- У пользователя должна лицензия на пакет ["Office 365 бизнес" или "Office 365 корпоративный"](https://products.office.com/business/compare-more-office-365-for-business-plans), связанная с его учетной записью Azure Active Directory. Подписка должна включать приложения Office на мобильных устройствах и может включать облачную учетную запись хранения с поддержкой [OneDrive для бизнеса](https://onedrive.live.com/about/business/). Лицензии Office 365 можно назначить на [портале Office](http://portal.office.com), следуя этим [инструкциям](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- Пользователь должен настроить управляемое расположение с помощью функции настраиваемого сохранения в параметре политики защиты приложения "Запретить операцию "Сохранить как". Например, если управляемое расположение — OneDrive, приложение [OneDrive](https://onedrive.live.com/about/) должно быть настроено в приложении Word, Excel или PowerPoint пользователя.

- Если управляемое расположение — OneDrive, на приложение должна распространяться политика защиты, развернутая для пользователя.

  >[!NOTE]
  > Мобильные приложения Office сейчас поддерживают только SharePoint Online, но не локальное приложение SharePoint.

**Почему для Office требуется управляемое расположение (например, OneDrive)?** Intune помечает все данные в приложении как корпоративные или личные. Данные считаются корпоративными, если они созданы в корпоративном расположении. При работе с приложениями Office в Intune корпоративными считаются такие расположения: электронная почта (Exchange) или облачное хранилище (приложение OneDrive с учетной записью OneDrive для бизнеса).

**Каковы дополнительные требования к использованию Skype для бизнеса?** См. требования к лицензии [Skype для бизнеса](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > Мобильное приложение Skype для бизнеса сейчас поддерживает только службу Skype для бизнеса Online.

## <a name="app-protection-features"></a>Параметры защиты приложений

**Что такое поддержка множественной идентификации?** Поддержка множественной идентификации позволяет пакету SDK для приложений Intune применять политики защиты приложений только к рабочей или учебной учетной записи, используемой для входа в приложение. Если вход в приложение выполнен с помощью личной учетной записи, данные останутся без изменений.

**Для чего нужна поддержка множественной идентификации?** Поддержка множественной идентификации обеспечивает общедоступный выпуск приложений для корпоративного и личного пользования (включая приложения Office) с функциями защиты приложений Intune для корпоративных учетных записей.

**Поддерживает ли Outlook множественную идентификацию?** Так как в Outlook реализовано объединенное представление сообщений электронной почты (личных и корпоративных), приложение Outlook при запуске запрашивает ПИН-код Intune.

**Что такое ПИН-код для приложения Intune?** Персональный идентификационный номер (ПИН-код) — это секретный код, который используется для проверки прав пользователя на доступ к корпоративным данным в приложении.

- **Когда пользователь должен вводить ПИН-код?** Intune запрашивает ПИН-код для приложения, когда пользователь пытается получить доступ к корпоративным данным. В приложениях с поддержкой множественной идентификации (включая Word, Excel и PowerPoint) пользователь должен вводить ПИН-код при попытке открыть корпоративный документ или файл. В приложениях, использующих единую идентификацию (включая бизнес-приложения, управляемые с помощью инструмента упаковки для приложений Intune), ПИН-код нужно вводить при запуске, так как пакет SDK для приложений Intune всегда обрабатывает все данные в приложении как корпоративные.

- **Как часто пользователю предлагается ввести ПИН-код Intune?**
  ИТ-администратор может определить параметр "Проверять требования доступа повторно через (мин)" в настройках политики защиты приложения Intune с помощью консоли администрирования Intune. Этот параметр определяет период времени, через который выполняется проверка требования к доступу на устройстве, после чего снова появляется экран приложения с ПИН-кодом. Ниже приведены важные сведения о ПИН-коде, которые влияют на то, как часто пользователь будет получать запрос на ввод ПИН-кода: 

    - **Для удобства ПИН-код является общим для приложений одного издателя.** В iOS один ПИН-код используется во всех приложениях **одного издателя**. В Android один ПИН-код используется во всех приложениях.
    - **Последовательный характер таймера, связанного с ПИН-кодом.** После ввода ПИН-кода для доступа к приложению (приложение A) и перехода приложения в активный режим (основной фокус ввода) на устройстве, таймер ПИН-кода сбрасывается. Любое другое приложение (приложение B), использующее этот ПИН-код, не будет отправлять пользователю запрос на ввод ПИН-кода, так как таймер сброшен. Запрос появится снова, когда будет достигнуто значение параметра "Проверять требования доступа повторно через (мин)". 

      >[!NOTE] 
      > Чтобы проверять требования к пользовательскому доступу чаще (отображать запрос на ввод ПИН-кода), особенно для часто используемых приложений, рекомендуется уменьшить значение параметра "Проверять требования доступа повторно через (мин)". 

- **Безопасно ли использовать ПИН-код?** ПИН-код предоставляет доступ к корпоративным данным только пользователям с соответствующими полномочиями. Следовательно, чтобы настроить или сбросить ПИН-код для приложения Intune, пользователь должен войти с использованием своей рабочей или учебной учетной записи. Эта проверка подлинности обрабатывается Azure Active Directory с помощью безопасного обмена маркерами и не является прозрачной для пакета SDK для приложений Intune. Из соображений безопасности рекомендуется шифровать корпоративные или учебные данные. Шифрование не связано с ПИН-кодом для приложения; это отдельная политика защиты приложений.

- **Как Intune защищает ПИН-код от атак методом подбора?** В рамках политики использования ПИН-кода для приложения ИТ-администратор может настроить максимальное число попыток пользователя выполнить проверку подлинности с использованием ПИН-кода, прежде чем приложение будет заблокировано. При достижении этого числа попыток пакет SDK для приложений Intune может очистить корпоративные данные в приложении.
  
- **Почему нужно дважды задавать PIN-код для приложений одного издателя?**
  Сейчас MAM (в iOS) позволяет применять PIN-код уровня приложения, который содержит буквы, цифры и специальные символы (так называемый секретный код). Если используется этот секретный код, для интеграции пакета SDK для приложения Intune для iOS требуются приложения (например, WXP, Outlook, Managed Browser, Yammer). Без этих приложений параметры секретного кода неправильно применяются к целевым приложениям. Этот компонент был выпущен в пакете SDK Intune для iOS версии 7.1.12. <br><br> Для поддержки этого компонента и обеспечения обратной совместимости с предыдущими версиями пакета SDK Intune для iOS все PIN-коды (и числовые, и секретные коды) в версиях позднее 7.1.12 обрабатываются отдельно от числового PIN-кода в предыдущих версиях пакета SDK. Поэтому если на устройстве есть приложения с пакетом SDK Intune для версий iOS, выпущенных до и после версии 7.1.12, потребуется настроить два PIN-кода. <br><br> Эти два PIN-кода (по одному для каждого приложения) никак между собой не связаны, т. е. они должны соответствовать политике защиты приложения, которая применяется к приложению. Например, пользователь может задать один и тот же PIN-код дважды, *только* если для приложений A и B настроены одинаковые политики (касающиеся PIN-кода). <br><br> Это поведение относится только к PIN-кодам в приложениях iOS с поддержкой управления мобильными приложениями Intune. Со временем, по мере внедрения в приложения более поздних версий пакета SDK Intune для iOS, двукратная установка PIN-кодов станет менее проблематичной. Ниже приведен пример.

  >[!NOTE]
  > Например, один и тот же издатель создал приложение A до выпуска версии 7.1.12, а приложение B — с помощью версии 7.1.12. Пользователю потребуется задать отдельно PIN-коды для приложений A и B, если оба приложения установлены на устройстве iOS. <br><br> Если приложение C создано с помощью SDK версии 7.1.9 и установлено на том же устройстве, для него будет использоваться тот же PIN-код, что и для приложения A. <br><br> Приложение D, созданное с помощью версии 7.1.14, будут использовать тот же PIN-код, что и приложение B. <br><br> Если приложения A и C установлены на одном устройстве, необходимо задать только один PIN-код. То же касается приложений B и D, установленных на одном устройстве.

**Как используется шифрование?** ИТ-администраторы могут развернуть политику защиты приложений, в соответствии с которой данные приложения должны шифроваться. В рамках политики ИТ-администратор также может определить, когда содержимое должно быть зашифровано.

- **Как выполняется шифрование данных в Intune?** Дополнительные сведения о параметрах шифрования в политике защиты приложений см. в статьях [Android app protection policy settings](app-protection-policy-settings-android.md) (Параметры политики защиты мобильных приложений для Android) и [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Параметры политики защиты мобильных приложений для iOS).

- **Какие данные шифруются?** В соответствии с политикой защиты приложений, определенной ИТ-администратором, шифруются только те данные, которые отмечены как корпоративные. Данные считаются корпоративными, если они созданы в корпоративном расположении. При работе с приложениями Office в Intune корпоративными считаются такие расположения: электронная почта (Exchange) или облачное хранилище (приложение OneDrive с учетной записью OneDrive для бизнеса). В бизнес-приложениях, управляемых с помощью инструмента упаковки для приложений Intune, все данные считаются корпоративными.

**Как в Intune выполняется удаленная очистка данных?** Intune может очищать данные приложений тремя способами: полная очистка устройства, выборочная очистка для управления мобильными устройствами и выборочная очистка для управления мобильными приложениями. Дополнительные сведения об удаленной очистке для MDM см. в статье [Очистка устройств с помощью сброса параметров до заводских настроек или удаления данных организации](devices-wipe.md#factory-reset). Дополнительные сведения о выборочной очистке с использованием MAM см. в разделе [Удаление данных организации](devices-wipe.md#remove-company-data) и статье [Очистка только корпоративных данных в приложениях, управляемых с помощью Intune](apps-selective-wipe.md).

- **Что такое сброс до заводских настроек?** При [сбросе до заводских настроек](devices-wipe.md) с **устройства** удаляются все данные и параметры пользователя и восстанавливаются заводские настройки. Устройство удаляется из Intune.
  >[!NOTE]
  > Сбросить параметры до заводских настроек можно только на устройствах, зарегистрированных с помощью управления мобильными устройствами Intune.

- **Что такое выборочная очистка для управления мобильными устройствами?** Сведения об удалении данных организации см. в статье [Очистка устройств с помощью сброса параметров до заводских настроек или удаления данных организации](devices-wipe.md#remove-company-data).

- **Что такое выборочная очистка для управления мобильными приложениями?** При выборочной очистке для управления мобильными приложениями данные приложений компании просто удаляются из приложений. Запрос отправляется с портала Intune Azure. Сведения об инициации запроса на очистку см. в статье [Очистка только корпоративных данных в приложениях, управляемых с помощью Intune](apps-selective-wipe.md).

- **Как быстро выполняется выборочная очистка для управления мобильными приложениями?** Если пользователь использует приложение при запуске выборочной очистки, пакет SDK для приложений Intune каждые 30 минут будет проверять наличие запроса на выборочную очистку от службы Intune MAM. Проверка запросов на выборочную очистку также выполняется, когда пользователь впервые запускает приложение и входит с помощью своей рабочей или учебной учетной записи.

**Почему локальные службы не поддерживают приложения, защищенные с помощью Intune?** Защита приложений в Intune зависит от соответствия удостоверения пользователя в приложении и пакете SDK для приложений Intune. Единственный способ обеспечить это — использовать современные средства проверки подлинности. Есть сценарии, в которых приложения могут работать с локальной конфигурацией, но в таких случаях согласованность не гарантируется.

**Существует ли безопасный способ открывать веб-ссылки из управляемых приложений?** Да! ИТ-администратор может развернуть и настроить политику защиты приложений для [приложения Intune Managed Browser](app-configuration-managed-browser.md) (браузера от Microsoft Intune, которым можно управлять с помощью Intune). ИТ-администратор может настроить открытие всех веб-ссылок в управляемых приложениях Intune с помощью приложения Managed Browser.


## <a name="app-experience-on-android"></a>Работа приложений на устройствах Android

**Почему для защиты приложений Intune на устройствах Android требуется приложение корпоративного портала?** Большинство функций защиты приложений встроены в приложение корпоративного портала. И хотя приложение корпоративного портала требуется всегда, регистрация устройств _не обязательна_. Для использования MAM-WE на пользовательском устройстве должно быть установлено приложение корпоративного портала.

## <a name="app-experience-on-ios"></a>Работа приложений на устройствах iOS

**Я могу использовать расширение для общего доступа iOS, чтобы открывать рабочие или учебные данные в неуправляемых приложениях, даже если политика передачи данных распространяется только на управляемые приложения или вообще не включена. Не приведет ли это к утечке данных?** С помощью политики защиты приложений Intune нельзя управлять расширением для общего доступа iOS, не управляя самим устройством. Следовательно, Intune _**зашифровывает корпоративные данные, прежде чем они будут использоваться за пределами приложения**_. Это можно проверить, попытавшись открыть корпоративный файл за пределами управляемого приложения. Такой файл должен быть зашифрован, и его не удастся открыть за пределами управляемого приложения.

## <a name="see-also"></a>См. также:
- [План внедрения Intune](planning-guide-onboarding.md)
- [Тестирование и проверка Intune](planning-guide-test-validation.md)
- [Параметры политики управления мобильными приложениями Android в Microsoft Intune](app-protection-policy-settings-android.md)
- [Параметры политики управления мобильными приложениями iOS](app-protection-policy-settings-ios.md)
- [Проверка настройки политики защиты приложений](app-protection-policies-validate.md)
- [Добавление политик конфигурации приложений для управляемых приложений без регистрации устройств](app-configuration-policies-managed-app.md)
- [Получение поддержки для Microsoft Intune](get-support.md)