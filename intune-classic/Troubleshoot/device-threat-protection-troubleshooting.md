---
title: Устранение неполадок интеграции Lookout
description: В этом разделе описывается устранение неполадок, которые часто возникают при интеграции с Lookout.
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: dougeby
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6262fee0051827794c49ebe10361b1a3b280b140
ms.sourcegitcommit: f21287c66dd5559688f08bd98b6c976a0dea055d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2018
ms.locfileid: "34470803"
---
# <a name="troubleshoot-lookout-integration-with-intune"></a>Устранение неполадок интеграции Lookout с Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

В этом разделе описаны некоторые распространенные проблемы, которые могут возникать в ходе установки службы Lookout MTP.

**Ошибки входа**

## <a name="403-errors"></a>Ошибкa 403
При входе в [консоль Lookout MTP](https://aad.lookout.com) отображается ошибка 403: **вы не авторизованы для доступа к службе**. Это может произойти, если вы указали имя пользователя, который не является членом группы Azure Active Directory (AD), настроенной для доступа к Lookout MTP.

Lookout MTP предоставляет доступ к службе только пользователям из настроенных групп Azure AD. Чтобы определить, для какой группы настроен доступ к Lookout MTP, обратитесь в службу поддержки Lookout:

* Адрес электронной почты: enterprisesupport@lookout.com
* Войдите в [консоль MTP](http://aad.lookout.com) и перейдите к модулю **Поддержка**.
* Перейдите по адресу <https://enterprise.support.lookout.com/hc/requests> и создайте запрос на поддержку.

## <a name="unable-to-sign-in"></a>Не удается выполнить вход
Если пользователь с правами глобального администратора Azure AD не принял условия первоначальной установки Lookout, отображается следующая ошибка.

![снимок экрана входа Lookout с ошибкой входа](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Чтобы устранить эту проблему, глобальный администратор должен выполнить вход на странице https://aad.lookout.com/les?action=consent и принять условия для запуска установки. Более подробные сведения можно найти в разделе [Настройка службы Lookout MTP в подписке](../deploy-use/setup-your-lookout-mtd-subscription.md).

**Проблемы с состоянием устройства**

## <a name="device-missing-from-lookout-device-list"></a>Устройство отсутствует в списке устройств Lookout

Это может происходить в следующих случаях.
* Пользователь устройства не находится в **группе регистрации**, указанной в **консоли Lookout MTP**.  В [консоли Lookout](http://aad.lookout.com) выберите **Система** > **Соединитель Intune** > **Управление регистрацией**.  Проверьте группы Azure AD, настроенные для регистрации, и убедитесь, что пользователь устройства входит в одну из них.  При добавлении пользователя в группу регистрации его устройство может отобразиться в модуле **Устройства** консоли Lookout MTP по прошествии настроенного интервала опроса (по умолчанию — 5 минут).
* Устройство не поддерживается Lookout MTP.  Неподдерживаемые устройства будут отображаться в разделе **Управляемые устройства** параметров соединителя в консоли Lookout MTP.

### <a name="device-reported-as-pending"></a>Устройство отображается в состоянии **ожидания**.

Если для устройства отображается состояние **Ожидание**, значит конечный пользователь еще не открыл приложение Lookout for Work и не нажал кнопку **Активировать**. Дополнительные сведения об активации устройства с помощью приложения Lookout for Work см. в разделе [Вам предложено установить Lookout for Work на устройстве с Android](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) или [Вам предложено установить Lookout for Work на устройстве с iOS](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios).

## <a name="device-whos-active-but-has-no-device-id"></a>Активное устройство без идентификатора устройства
Если у активного устройства в консоли Lookout MTP отсутствует идентификатор, значит его пользователь не входит в группу регистрации. Устройство может перейти в это состояние, если его пользователь был удален из группы регистрации или была удалена сама эта группа регистрации.

В [консоли Lookout](http://aad.lookout.com) выберите **Система** > **Соединитель Intune** > **Регистрация** и просмотрите параметры.  Проверьте группы Azure AD и убедитесь, что пользователь устройства входит в одну из них.

Если устройство находится в этом состоянии, Lookout будет по-прежнему уведомлять пользователя об обнаруженных угрозах, но не будет передавать сведения об угрозах Intune.

## <a name="device-reported-as-disconnected"></a>Устройство отображается в **отключенном** состоянии.

**Отключенное** состояние означает, что устройство еще не синхронизировано с Lookout MTP в течение заданного периода (по умолчанию 30 дней, но не менее 7 дней). На устройстве отсутствует приложение корпоративного портала или приложение Lookout for Work. Переустановка приложения должна решить эту проблему. Когда пользователь открывает Lookout for Work и активирует приложение, выполняется повторная синхронизация устройства с Lookout MTP и Intune.

### <a name="forcing-a-device-sync"></a>Принудительная синхронизация устройства
В модуле **Устройства** консоли Lookout MTP администратор может выбрать устройство и удалить его.   Когда владелец устройства в следующий раз откроет Lookout for Work и нажмет кнопку **Активировать**, будет выполнена полная повторная синхронизация.

## <a name="device-has-a-new-user"></a>Новый пользователь устройства
Следует очистить устройство и попросить нового пользователя пройти регистрацию.  В [консоли администрирования Intune](https://manage.microsoft.com) выберите устройство, щелкните его правой кнопкой мыши и выберите пункт **Снять с учета/очистить**, чтобы удалить устройство из области управления. После снятия устройства с учета его можно удалить.

![снимок экрана модуля "Устройства" в консоли администрирования Intune с параметром "Снять с учета/очистить"](../media/mtp/mtp-retire-device-intune-console.png)

Можно также перейти в модуль **Устройства** [консоли Lookout](http://aad.lookout.com) и выбрать **Удалить**.

Если новый пользователь входит в группу регистрации Lookout MTP, устройство отображается в списке после его связывания с новым пользователем в Azure AD.

## <a name="compliance-remediation-workflows"></a>Рабочие процессы устранения проблем совместимости
- [Вам предложено установить Lookout for Work на устройстве с Android](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android).
- [Вам требуется устранить угрозу, обнаруженную Lookout for Work на устройстве Android](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Вам требуется устранить угрозу, обнаруженную Lookout for Work на устройстве iOS](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>См. также:
[Настройка службы Lookout MTP в подписке](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)
