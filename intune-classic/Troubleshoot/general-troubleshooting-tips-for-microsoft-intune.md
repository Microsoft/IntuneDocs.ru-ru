---
title: Общие советы по устранению неполадок
description: Общие ресурсы для решения проблем при работе с Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/08/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d5d55f6c3efabdde51b5627d5ddd409c2b282f6c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Общие советы по устранению неполадок в Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

После развертывания Microsoft Intune могут возникать проблемы с конфигурацией или клиентскими устройствами. Используйте указанные ниже ресурсы, чтобы определить причину проблемы и способы ее решения.

> [!NOTE]
> Чтобы создать запрос в службу поддержки или просмотреть существующий запрос, [перейдите в центр администрирования Office 365](https://portal.office.com/admin/default.aspx). Дополнительные сведения о вариантах поддержки см. в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="define-the-problem"></a>Определение проблемы

-   Какое поведение имеет место?

-   Кто сталкивается с таким поведением, на каких платформах и устройствах?

-   Работало ли устройство правильно ранее?

-   Какие изменения были внесены в Intune или конфигурацию устройства?

-   Были ли внесены в среду, где вы работаете, какие-либо другие изменения, кроме изменений конфигурации?

-   Как часто возникает эта проблема, носит ли она разовый или регулярный характер?

-   Испытывает ли пользователь проблемы с проверкой подлинности? Если это возможно, проверьте, может ли пользователь войти в другие службы, использующие Azure Active Directory. Кроме того, проверьте, может ли пользователь выполнить вход с другого устройства.

-   Проверили ли вы состояние службы? Вы сможете отслеживать работоспособность службы Intune на [портале управления Office 365](https://portal.office.com/Admin/Default.aspx). Выберите **Работоспособность службы** в области слева.

## <a name="collect-available-data"></a>Сбор доступных данных

- Следующие ресурсы помогут вам узнать, как собирать сведения о журналах устройств:
  - [Отправка журналов диагностических данных Android ИТ-администратору по USB-кабелю](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Отправка ошибок регистрации Android ИТ-администратору](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [Отправка ошибок регистрации iOS ИТ-администратору](/intune-user-help/send-errors-to-your-it-admin-ios)

- Используя данные из консоли администрирования (например, при проблемах с реализацией политик), изучите применяемую политику и ее состояние, как описано в статье [Использование групп для управления пользователями и устройствами в Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="research-the-solution"></a>Поиск решения

-   Выполните поиск решения в Интернете. Например, если возникает ошибка 0x80073CF0, выполните поиск строки **technet intune 0x80073cf0** в Интернете, чтобы найти статью [Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md). Данная статья содержит рекомендации по устранению этой ошибки.

-   Попытайтесь найти ответ на [форуме Intune TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Если проблема ранее не обсуждалась, опубликуйте вопрос, чтобы члены сообщества смогли высказать свои предложения.

-   Откройте запрос на техническую поддержку. Служба поддержки Intune сможет оказать вам более квалифицированную помощь, если вы определили проблему и собрали доступные данные.

    Чтобы создать запрос на поддержку, [перейдите в Центр администрирования Office 365](https://portal.office.com/admin/default.aspx). Дополнительные сведения о вариантах поддержки см. в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="find-community-resources"></a>Поиск ресурсов сообщества
Другие полезные сведения, которые можно найти в этих ресурсах сообщества:

-   Статья [Практические советы по Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) содержит ссылки на различные ресурсы, которые могут помочь при настройке, обслуживании и устранении неполадок Intune.

-   [Блог по Intune](http://blogs.technet.com/b/windowsintune/)

-   [Подпишитесь на Intune в Twitter](https://twitter.com/MSIntune)

-   [Форумы по Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Дальнейшие шаги
Перечисленные ниже разделы могут помочь в устранении определенных неполадок. Если эта информация не помогла, обратитесь в службу поддержки Майкрософт, как описано в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Устранение неполадок с Endpoint Protection в Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Устранение неполадок, связанных с доступом к ресурсам организации, с использованием Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Устранение проблем при регистрации устройств в Intune](troubleshoot-device-enrollment-in-intune.md)

[Устранение неполадок с политиками в Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Устранение неполадок при настройке клиента в Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Устранение неполадок с обновлениями программного обеспечения в Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)
