---
title: "Новые возможности | Документация Майкрософт"
description: "Новые возможности в выпусках Microsoft Intune этого месяца и за прошлые периоды"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 053cf0a1b5d06496397b36cbd1a7ebdce420fed3
ms.openlocfilehash: 5158d58c32066ea720335a878fef87451542c195


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Новые возможности в Microsoft Intune — январь 2017 г.
Узнайте о новых возможностях этого выпуска Microsoft Intune. Кроме того, здесь можно узнать о предстоящих изменениях, к которым следует подготовиться, а также сведения о прошлых выпусках.

> [!Note]
> В будущем все эти функции будут также поддерживаться в гибридных развертываниях (Configuration Manager с Intune). Дополнительные сведения о новых гибридных функциях см. на [странице новых гибридных функций](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Новые возможности

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Отчеты в консоли для MAM без регистрации <!--677961-->
Как для зарегистрированных, так и для незарегистрированных устройств были добавлены новые отчеты защиты приложений. Дополнительные сведения о том, как можно [отслеживать политики управления мобильными приложениями с помощью Intune](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Поддержка Android 7.1.1 <!--694397-->
Теперь служба Intune полностью поддерживает Android 7.1.1 и может управлять устройствами на базе этой ОС.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Устранена проблема, из-за которой устройства с ОС iOS были неактивны или консоль администрирования не могла связаться с ними. <!--unknown-->
Если устройства пользователей потеряют связь с Intune, можно предоставить пользователям новые шаги по устранению проблем, чтобы они могли получить доступ к ресурсам компании. См. статью [Устройства неактивны, или консоль администрирования не может связаться с ними](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Объявления

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Переход на управление настольными устройствами Windows с помощью параметров Windows <!--663050-->
Меняется стандартный процесс для регистрации настольных систем на базе Windows 10. Новые регистрации будут выполняться по стандартной процедуре с помощью агента MDM, а не через агент ПК.

Веб-сайт корпоративного портала предоставляет пользователям настольных систем Windows 10 инструкции по регистрации, помогающие добавить настольные компьютеры с Windows 10 в качестве мобильных устройств. Это не затронет уже зарегистрированные компьютеры, и [при желании](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) организация по-прежнему сможет управлять настольными системами Windows 10 с помощью агента ПК.

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Улучшение поддержки управления мобильными приложениями для выборочной очистки <!--581242-->
Конечным пользователям будут представлены дополнительные указания о том, как восстановить доступ к рабочим или учебным данным в случае их автоматического удаления политикой "Offline interval before app data is wiped" (Период автономной работы до очистки данных).<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Открытие ссылок корпоративного портала для iOS внутри приложения <!--665954-->
Ссылки внутри приложения корпоративного портала для iOS, включая указывающие на документацию и приложения, открываются непосредственно в приложении корпоративного портала, используя представление Safari в приложении. Это обновление будет поставляться отдельно от обновления за январь.

### <a name="modernizing-the-company-portal-website---753980--"></a>Модернизация сайта корпоративного портала <!--753980-->
В феврале сайт корпоративного портала предоставит поддержку приложений для пользователей, у которых нет управляемых устройств. Контрастная цветовая схема, динамические иллюстрации и значок меню сайта будут оформлены в стиле других продуктов и служб Майкрософт, а в ![меню корпоративного портала](./media/CP_hamburger_menu.png) можно будет найти контактные данные службы поддержки и информацию об управляемых устройствах. На целевой странице появятся карусели для рекомендуемых и недавно обновленных приложений, доступных пользователям, и им будет отведено видное место. Изображения с изменениями "до" и "после" см. в статье [Новые возможности пользовательского интерфейса для приложений в Intune](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017).

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Новая документация для политик защиты приложений <!--583398-->
Мы обновили документацию для администраторов и разработчиков, желающих включить политики защиты приложений (известные как политики MAM) в своих приложениях iOS и Android с помощью инструмента упаковки приложений Intune или пакета SDK для приложений Intune.

Были обновлены следующие статьи:

* [Выбор способа подготовки приложений для управления мобильными приложениями с помощью Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Подготовка приложений из iOS для управления мобильными приложениями с помощью инструмента упаковки для приложений Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Начало работы с SDK для приложений Microsoft Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Руководство разработчика iOS по SDK для приложений Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

В библиотеку документов были добавлены следующие статьи:

* [подключаемый модуль Cordova из пакета SDK для приложений Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova).
* [компонент Xamarin из пакета SDK для приложений Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin);

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Индикатор выполнения при запуске корпоративного портала на iOS <!--665978-->
На экране запуска корпоративного портала для iOS появился индикатор выполнения, предоставляющий пользователю сведения о процессе загрузки. Замена вертушки индикатором выполнения будет проводиться поэтапно. Это означает, что некоторые пользователи увидят новый индикатор, а другие продолжат видеть вертушку.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Новые возможности в общедоступной предварительной версии в интерфейсе администрирования Intune в Azure <!--736542-->

В начале 2017 года мы планируем перенести все административные функции в Azure. Это позволит обеспечить интегрированное и эффективное управление основными рабочими процессами EMS на современной платформе служб, расширяемой с помощью интерфейсов API Graph.

В новых пробных версиях клиентов на портале Azure общедоступная предварительная версия нового интерфейса администратора будет доступна в этом месяце. Пока интерфейс администратора будет находиться в предварительной версии, процесс обеспечения соответствия возможностям имеющейся консоли Intune будет выполняться несколько раз.

В интерфейсе администратора на портале Azure будут реализованы уже объявленные возможности группирования и определения целевых объектов. Если применить новые параметры группирования на имеющемся клиенте, на нем также будет реализован новый интерфейс администратора. В то же время, чтобы проверить или просмотреть любые новые возможности перед переносом своего клиента, зарегистрируйтесь для получения новой пробной учетной записи Intune или изучите [новую документацию](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Вопросы о сроках переноса вашего клиента отравляйте нашей команде по миграции по адресу [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Новые возможности в предварительной версии Intune в Azure см. [здесь](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>См. также
* [Блог Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Стратегии развития облачной платформы](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Новые возможности в предварительной версии Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Новые возможности пользовательского интерфейса корпоративного портала](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Новые возможности — архив](whats-new-archive.md)



<!--HONumber=Feb17_HO1-->


