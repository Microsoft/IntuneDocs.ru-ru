---
title: "Оценка управления мобильными устройствами в Microsoft Intune | Microsoft Docs"
description: "Оценка MDM в рамках бесплатной пробной версии Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Оценка управления мобильными устройствами в Microsoft Intune
В этом руководстве по оценке содержатся сведения о работе управления мобильными устройствами в Intune. Вы выполните следующие задачи:
- Регистрация устройства для управления Intune.
- Создание групп для организации пользователей и устройств.
- Создание и развертывание ряда политик управления устройствами для групп.
- Публикация приложения, чтобы пользователи могли установить его на своих зарегистрированных устройствах.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Допущения
В этом руководстве предполагается, что пробная версия используется только в ознакомительных целях и запускается в чистой среде при оформлении подписки.

Чтобы начало работы с пробной версией не вызывало трудностей, будет настроена очень простая среда, где используется только служба Intune; предполагается, что она будет центром управления мобильными устройствами. Однако если вы захотите глубже изучить этот вопрос, вы сможете воспользоваться приведенными в этом руководстве ссылками на более подробное техническое содержимое.

В пробной версии доступны те же действия, что и в версии подписки. Единственное отличие заключается в том, что в пробной версии существует ограничение в 100 учетных записей пользователей.

## <a name="whats-not-covered"></a>Неохваченные темы
|Интересующий вас вопрос |Статья |
|------------------------|----------|
|MDM в среде, не являющейся тестовой | [Приступая к работе](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|MDM с Intune and System Center Configuration Manager | [Гибридное управление мобильными устройствами](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Поскольку указанные выше руководства предназначены для настройки Intune в рабочих средах, они охватывают больше точек принятия решений, которые необходимо проработать, чем руководство по оценке.

Для быстрого ознакомления с Intune рекомендуется начать с руководства по оценке, а затем перейти к другим руководствам.

## <a name="prerequisites-for-this-evaluation"></a>Предварительные требования для данной оценки
- Internet Explorer 10 или более поздней версии
- Устройство, которое будет использоваться для тестирования способов регистрации устройств и управления ими с помощью корпоративного портала. В этом руководстве используется iPad и телефон с Android.
- Для управления iPad или другим устройством с системой iOS вам потребуется [сертификат службы push-уведомлений Apple](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- [Пробная подписка Intune](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Настройка центра MDM
Первым шагом в процессе управления мобильными устройствами с помощью Intune является установка **центра управления мобильными устройствами (MDM)**.

Если вы используете автономное развертывание Intune, как предполагается в этой пробной версии, или используете Intune в составе подписки Enterprise Mobility + Security (EMS), необходимо задать Intune в качестве центра управления мобильными устройствами. При этом Intune становится службой, применяемой для управления мобильными устройствами в вашей организации.

Клиентам, желающим использовать Intune с System Center Configuration Manager для управления мобильными устройствами, необходимо решить, что будет их центром управления мобильными устройствами — Intune или Configuration Manager. Это важное решение, принимаемое в рабочей среде, так как в настоящее время очень сложно изменить уже сделанный выбор. Кроме того, этот вопрос не рассматривается в настоящем руководстве по оценке. Дополнительные сведения о последствии настройки Intune или Configuration Manager в качестве центра MDM см. в статье [Choose between standalone Intune and hybrid mobile device management](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management) (Выбор между автономной версией Intune и гибридным управлением мобильными устройствами).

В пробной версии Intune будет установлена в качестве центра управления мобильными устройствами. Это не повлияет на рабочую среду, если только в ней не будет использоваться пробная версия.

1. В [консоли администрирования Intune](https://manage.microsoft.com/) последовательно выберите **Администрирование** &gt; **Управление мобильными устройствами**.
2. В списке **Задачи** выберите команду **Задать центр MDM**. Откроется диалоговое окно **Установка центра MDM**. <!---screen shot--->
3. Intune просит подтвердить, что Intune должен быть вашим центром MDM. Установите флажок и нажмите кнопку **Да**, чтобы использовать Intune для управления мобильными устройствами.

## <a name="enroll-your-test-devices-into-intune"></a>Регистрация тестовых устройств в Intune

В этом руководстве мы будем регистрировать телефон с Android и Apple iPad, но в конце раздела предоставим ссылки на [дополнительные сведения о регистрации устройств в Intune](#Learn-more-about-device-enrollment).
### <a name="android"></a>Android
Установите приложение **корпоративного портала Intune** от корпорации Майкрософт из [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) и выполните вход с помощью [учетных данных пользователя](sign-up-for-30-day-trial-microsoft-intune.md#add-users), созданных при регистрации для использования бесплатной пробной версии.

### <a name="ios"></a>iOS
Прежде чем пользователи смогут регистрировать свои устройства с iOS, необходимо настроить Intune для управления этими устройствами.

1. **Получение запроса подписи сертификата**<br/>
Войдите в Intune с правами администратора и последовательно выберите пункты **Администрирование** > **Управление мобильными устройствами** > **iOS и Mac OS X** > **Отправка сертификата APNs**, после чего выберите команду **Загрузить запрос сертификата APNs**. Сохраните файл запроса на подписывание сертификата (CSR-файл) локально. CSR-файл используется для запроса сертификата отношений доверия с портала сертификатов push-уведомлений Apple. <!--- screen shot--->
2.  **Получение сертификата службы push-уведомлений Apple (APNs)**<BR/>
Перейдите на [Портал сертификатов push-уведомлений Apple](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) и войдите с помощью идентификатора Apple ID вашей организации, чтобы создать сертификат APNs с помощью CSR-файла. Нажав кнопку **Отправить** на портале сертификатов push-уведомлений Apple, вы получаете JSON-файл, который нельзя использовать для APNs. Завершите скачивание, вернитесь на страницу "Сертификаты сторонних серверов" портала сертификатов push-уведомлений Apple и нажмите кнопку **Скачать**.

 Скачайте сертификат APNs (PEM-файл) и сохраните файл локально. Этот идентификатор Apple ID необходимо использовать в будущем для продления сертификата APNs.
3.  **Добавление сертификата APNs в Intune**<BR/>
В консоли администрирования Microsoft Intune последовательно выберите пункты **Администрирование** > **Управление мобильными устройствами** > **iOS и Mac OS X** > **Отправка сертификата APNs**, а затем выберите команду **Отправить сертификат APNs**. Перейдите к файлу сертификата (PEM) и нажмите кнопку **Открыть**, а затем введите ваш идентификатор Apple. С помощью сертификата APNs Служба Intune позволяет регистрировать устройства с iOS и управлять ими, принудительно применяя политику к зарегистрированным мобильным устройствам.
4.  **Сообщите пользователям, как регистрировать свои устройства, чтобы получить доступ к ресурсам компании.**<br/>
Дополнительные сведения о регистрации для пользователей см. в статьях [Регистрация устройства iOS в Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) и [Регистрация устройства Mac OS X в Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). При регистрации пользователи будут уведомлены о том, что они могут ожидать, а также об объеме сведений, отображаемых на устройствах для ИТ-администраторов.


### <a name="learn-more-about-device-enrollment"></a>Дополнительные сведения о регистрации устройств

Intune поддерживает следующие платформы устройств:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Требования к включению управления устройствами зависят от платформы, которой требуется управлять.
- Мобильные устройства с **Android** позволяют пользователям [регистрироваться с помощью приложения корпоративного портала](/intune/deploy-use/set-up-android-management-with-microsoft-intune), доступного в Google Play. Никаких дополнительных настроек в Intune не требуется.
- [Требования к настройке для **iOS и Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Требования к настройке для **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Дальнейшие шаги
[Создание групп для организации пользователей и устройств](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Jan17_HO1-->

