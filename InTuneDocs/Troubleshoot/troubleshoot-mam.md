---
title:
- "Устранение неполадок управления мобильными приложениями | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Устранение неполадок управления мобильными приложениями

Если у вас возникают проблемы, связанные с управлением мобильными приложениями, начните с этой статьи. В этой статье описывается ряд распространенных проблем, которые могут возникнуть, а также их решения.


**Проблема.** MAM без политики регистрации из консоли Azure не применяется к приложению Skype для бизнеса на устройствах iOS и Android.

Решение. В Skype для бизнеса необходимо настроить современную проверку подлинности.  Следуйте инструкциям, приведенным в статье, посвященной [включению современной проверки подлинности для клиента](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx), чтобы настроить современную проверку подлинности для Skype.

**Проблема.** MAM без политик регистрации не применяется к любому (поддерживаемому приложению Office) [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] для любого пользователя.
 
Решение. Убедитесь, что у пользователя есть лицензия для Intune.  

**Проблема.** ИТ-администратору не удается настроить политики MAM на портале Azure.

Решение. Следующие роли имеют доступ к порталу Azure:

- глобальный администратор, учетную запись которого можно настроить на [портале Office](http://portal.office.com/);
- владелец, учетную запись которого можно настроить на [портале Azure](https://portal.azure.com/);
- участник, учетную запись которого можно настроить на [портале Azure](https://portal.azure.com/).

Дополнительные сведения о настройке этих ролей см. в статье [Подготовка к настройке политик управления мобильными приложениями в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). 

**Проблема.** В отчете о приложении не отображаются пользователи, недавно добавленные в политику MAM.

Решение. Если пользователь недавно добавлен в политику MAM, отображение этого пользователя в отчетах как целевого может занять до 24 часов. 

**Проблема.** Применение изменений и обновлений политики может занять до 8 часов.  

Решение. Конечный пользователь может выйти из приложения и повторить вход для принудительной синхронизации со службой.  

**Проблема.** Политика MAM не применяется к устройствам Apple DEP.

Решение. Убедитесь, что вы используете сопоставление пользователей в рамках программы регистрации устройств Apple (DEP). Сопоставление пользователей необходимо для всех приложений, требующих проверку подлинности пользователей в рамках DEP.
Дополнительные сведения о регистрации устройств iOS в программе DEP см. в статье [Регистрация корпоративных устройств с помощью программы регистрации устройства iOS](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### См. также
- [Проверка настройки управления мобильными приложениями](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Подготовка к настройке политик управления мобильными приложениями в Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


