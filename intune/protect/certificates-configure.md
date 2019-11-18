---
title: Создание профилей сертификатов в Microsoft Intune — Azure | Документы Майкрософт
description: Дополнительные сведения об использовании сертификатов и профилей сертификатов SCEP и PKCS с Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ea2d51b82f0f47ee4bfabc94c2e971e4cb666d4
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801747"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Использование сертификатов для проверки подлинности в Microsoft Intune

Используйте сертификаты с Intune для проверки подлинности пользователей в приложениях и корпоративных ресурсах через профили VPN, Wi-Fi или электронной почты. Если для проверки подлинности подключений используются сертификаты, конечным пользователям не нужно вводить имена пользователей и пароли, что позволяет сделать доступ прозрачным. Сертификаты также используются для подписывания и шифрования электронной почты с помощью S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Поддерживаемые сертификаты и использование Intune

| Type              | Проверка подлинности | Подписывание S/MIME | Шифрование S/MIME  |
|--|--|--|--|
| Импортированный сертификат PKCS |  | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png)|
| PKCS #12 (или PFX)    | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) |  |
| Протокол SCEP  | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | |

Чтобы развернуть эти сертификаты, создайте и назначьте профили сертификатов для устройств.  

Каждый отдельный профиль сертификата, созданный вами, поддерживает одну платформу. Например, если вы используете сертификаты PKCS, вы создадите профиль сертификата PKCS для Android и отдельный профиль сертификата PKCS для iOS. Если вы также используете сертификаты SCEP для этих двух платформ, вы создадите профиль сертификата SCEP для Android, а другой — для iOS.

**Общие вопросы**.
- Если у вас нет центра сертификации (ЦС) предприятия, его необходимо создать или использовать аналог [одного из наших поддерживаемых партнеров](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners).
- При использовании профилей сертификатов SCEP с помощью служб сертификатов Microsoft Active Directory вы настроите сервер службы регистрации сертификатов для сетевых устройств (NDES).
- Если вы используете SCEP одного из наших партнеров по ЦС, вам потребуется [интегрировать его с Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Для профилей сертификатов SCEP и PKCS требуется скачать, установить и настроить соединитель Microsoft Intune Certificate Connector.
- Для использования импортированных сертификатов PKCS требуется скачать, установить и настроить соединитель сертификатов PFX для Microsoft Intune.
- Для импортированных сертификатов PKCS необходимо экспортировать сертификаты из центра сертификации и импортировать их в Microsoft Intune. См. [проект PFXImport PowerShell](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).
- Чтобы устройство использовало SCEP, PKCS или импортированные профили сертификатов PKCS, оно должно доверять корневому центру сертификации. Используйте *профиль доверенного сертификата* для развертывания доверенного корневого сертификата ЦС на устройства.

## <a name="supported-platforms-and-certificate-profiles"></a>Поддерживаемые платформы и профили сертификатов

| Платформа              | Профиль доверенного сертификата | Профиль сертификата PKCS | Профиль сертификата SCEP | Профиль импортированного сертификата PKCS  |
|--|--|--|--|---|
| Администратор устройства с Android | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png)|  ![Поддерживается](./media/certificates-configure/green-check.png) |
| Android для бизнеса <br> Полностью управляемые устройства (владелец устройства)   | ![Поддерживается](./media/certificates-configure/green-check.png) |   | ![Поддерживается](./media/certificates-configure/green-check.png) |   |
| Android для бизнеса <br> Выделенное устройство (владелец устройства)   |  |   |  |   |
| Android для бизнеса <br> — Рабочий профиль    | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) |
| iOS                   | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) |
| macOS                 | ![Поддерживается](./media/certificates-configure/green-check.png) |  ![Поддерживается](./media/certificates-configure/green-check.png) |![Поддерживается](./media/certificates-configure/green-check.png)|![Поддерживается](./media/certificates-configure/green-check.png)|
| Windows Phone 8.1     |![Поддерживается](./media/certificates-configure/green-check.png)  |  | ![Поддерживается](./media/certificates-configure/green-check.png)| ![Поддерживается](./media/certificates-configure/green-check.png) |
| Windows 8.1 и более поздние версии |![Поддерживается](./media/certificates-configure/green-check.png)  |  |![Поддерживается](./media/certificates-configure/green-check.png) |   |
| Windows 10 и более поздней версии  | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) | ![Поддерживается](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Экспорт доверенного корневого сертификата ЦС

Чтобы использовать импортированные сертификаты PKCS, SCEP и PKCS, устройства должны доверять корневому центру сертификации. Чтобы установить доверие, экспортируйте доверенный корневой сертификат центра сертификации (ЦС), а также все промежуточные или выдаваемые сертификаты центра сертификации в качестве общедоступного сертификата (CER-файла). Эти сертификаты можно получить из выдающего ЦС или с любого устройства, которое доверяет выдающему ЦС.

Чтобы экспортировать сертификат, обратитесь к документации по своему центру сертификации. Вам потребуется экспортировать сертификат в виде CER-файла.  Не экспортируйте закрытый ключ (PFX).

Этот CER-файл будет использоваться при [создании профилей доверенных сертификатов](#create-trusted-certificate-profiles) для развертывания этого сертификата на устройствах.

## <a name="create-trusted-certificate-profiles"></a>Создание профилей доверенных сертификатов

Перед созданием профиля сертификата SCEP, PKCS или импортированного сертификата PKCS необходимо создать профиль доверенного сертификата. Развертывание профиля доверенного сертификата гарантирует, что каждое устройство распознает законность вашего ЦС. Профили сертификатов SCEP непосредственно ссылаются на профиль доверенного сертификата. Профили сертификатов PKCS не ссылаются напрямую на профиль доверенного сертификата, но напрямую ссылаются на сервер, на котором размещен ваш ЦС. Профили импортированных сертификатов PKCS не ссылаются напрямую на профиль доверенного сертификата, но могут использовать его на устройстве. Развертывание профиля доверенного сертификата на устройствах гарантирует, что доверие будет установлено. Если устройство не доверяет корневому ЦС, политика профиля сертификата SCEP или PKCS сообщит об ошибке.  

Создайте отдельный профиль доверенного сертификата для каждой платформы устройства, которую вы хотите поддерживать, точно так же, как это делается для профилей сертификатов SCEP, PKCS или импортированного сертификата PKCS.  


### <a name="to-create-a-trusted-certificate-profile"></a>Создание профиля доверенного сертификата  

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Выберите **Устройства** > **Профили конфигурации** > **Создать профиль**.

   ![Перейдите к Intune и создайте профиль для доверенного сертификата](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Укажите следующие свойства.

   - **Имя** для профиля.
   - При необходимости задайте **описание**.
   - **Платформа**, на которой нужно развернуть профиль.
   - Задайте **доверенный сертификат** в качестве **типа профиля**.

4. Выберите **Параметры** и перейдите к CER-файлу доверенного корневого сертификата ЦС, экспортированному для использования с этим профилем сертификата, и нажмите кнопку **ОК**.

5. Только для устройств Windows 8.1 и Windows 10 выберите **Конечное хранилище** для доверенного сертификата из следующих расположений:  
   - **хранилище сертификатов на компьютере — корневое**;
   - **хранилище сертификатов на компьютере — промежуточное**;
   - **хранилище сертификатов пользователей — промежуточное**.

6. По завершении нажмите кнопку **ОК**, вернитесь к панели **Создать профиль** и выберите **Создать**.

Профиль появится в списке профилей в окне *Устройства — профили конфигурации* с типом профиля **Доверенный сертификат**.  Не забудьте назначить этот профиль устройствам, которые будут использовать сертификаты SCEP или PKCS. Сведения о том, как назначить этот профиль группам, см. в статье о [назначении профилей устройств](../configuration/device-profile-assign.md).

> [!NOTE]  
> На устройствах с Android выводится сообщение о том, что третья сторона установила доверенный сертификат.  

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Назначение профилей устройств](../configuration/device-profile-assign.md)  
- [Использование S/MIME для подписывания и шифрования сообщений электронной почты](certificates-s-mime-encryption-sign.md)  
- [Использование сторонних центров сертификации](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Дальнейшие шаги

Создайте профили сертификатов SCEP, PKCS или импортированных сертификатов PKCS для каждой платформы, которую хотите использовать. Дополнительные сведения см. в следующих статьях:  
- [Настройка инфраструктуры для поддержки сертификатов SCEP с помощью Intune](certificates-scep-configure.md)  
- [Настройка инфраструктуры сертификатов Microsoft Intune для PKCS](certficates-pfx-configure.md)  
- [Создание профиля импортированного сертификата PKCS](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  
