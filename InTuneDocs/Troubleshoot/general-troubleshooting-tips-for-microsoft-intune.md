---
title: "Общие советы по устранению неполадок | Microsoft Intune"
description: "Общие ресурсы для решения проблем при работе с Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: d321930262a9bcf9542c757fdf0b945d0419930c


---

# Общие советы по устранению неполадок в Microsoft Intune
После развертывания Microsoft Intune могут возникать проблемы с конфигурацией или клиентами. Перечисленные ниже ресурсы помогут вам выявить причину проблемы, а затем устранить ее.

> [!NOTE]
> Чтобы создать запрос в службу поддержки или просмотреть существующий запрос, [перейдите в центр администрирования Office 365](https://portal.office.com/admin/default.aspx). Дополнительные сведения о вариантах поддержки см. в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
## Определение проблемы

-   Какое поведение имеет место?

-   Кто сталкивается с таким поведением, на каких платформах и устройствах?

-   Работало ли устройство правильно ранее?

-   Какие изменения были внесены в Intune или конфигурацию устройства?

-   Определите, были ли внесены в среду, где вы работаете, какие-либо другие изменения, кроме изменений конфигурации.

-   Как часто возникает эта проблема, носит ли она разовый или регулярный характер?

-   Испытывает ли пользователь проблемы с проверкой подлинности? Если это возможно, проверьте, может ли пользователь войти в другие службы, использующие Azure Active Directory. Кроме того, проверьте, может ли пользователь выполнить вход с другого устройства.

-   Проверили ли вы состояние службы? Вы сможете отслеживать работоспособность службы Intune на [портале управления Office 365](https://portal.office.com/Admin/Default.aspx). Выберите **Работоспособность службы** в области слева.

## Сбор доступных данных

-   Журналы устройств. Узнайте, как собрать журналы устройств:
  - [Отправка журналов диагностических данных Android ИТ-администратору по USB-кабелю](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Отправка ошибок регистрации Android ИТ-администратору](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Отправка ошибок регистрации iOS ИТ-администратору](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Данные из консоли администрирования. Например, для проблем с реализацией политик следует изучить применяемую политику и ее состояние, как описано в статье [Использование групп для управления пользователями и устройствами в Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## Поиск решения

-   Выполните поиск решения в Интернете. Например, если возникает ошибка 0x80073CF0, можно выполнить поиск строки **technet intune 0x80073cf0** в Интернете и найти статью [Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md) с рекомендациями по устранению этой проблемы.

-   Можно попытаться найти ответ на [форуме Intune TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Если проблема ранее не обсуждалась, вам следует опубликовать вопрос, чтобы члены сообщества смогли высказать свои предложения.

-   Вы можете открыть запрос на поддержку. Служба поддержки Intune сможет оказать вам более квалифицированную помощь, если вы определили проблему и собрали доступные данные.

    Чтобы создать запрос на поддержку, [перейдите в центр администрирования Office 365](https://portal.office.com/admin/default.aspx). Дополнительные сведения о вариантах поддержки см. в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## Ресурсы сообщества
Другие полезные сведения, которые можно найти в этих ресурсах сообщества:

-   Статья [Практические советы по Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) содержит ссылки на различные ресурсы, которые могут помочь при настройке, обслуживании и устранении неполадок Intune.

-   [Блог по Intune](http://blogs.technet.com/b/windowsintune/)

-   [Подпишитесь на Intune в Twitter](https://twitter.com/MSIntune)

-   [Форумы по Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Дальнейшие действия
Перечисленные ниже разделы могут помочь в устранении определенных неполадок. Если эта информация не помогла, обратитесь в службу поддержки Майкрософт, как описано в разделе [Как получить поддержку для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Устранение неполадок, связанных с доступом к ресурсам компании, с использованием Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Устранение проблем при регистрации устройств в Intune](troubleshoot-device-enrollment-in-intune.md)

[Устранение неполадок с политиками Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Устранение неполадок при настройке клиента в Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Устранение неполадок с обновлениями программного обеспечения в Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


