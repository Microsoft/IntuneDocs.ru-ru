---
title: "Параметры политики MAM для iOS | Microsoft Intune"
description: "В этом разделе описываются параметры политики управления мобильными приложениями для устройств iOS."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 126974152c638fc4bc69ef92b5fa79beeb0eed0c


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Параметры политики управления мобильными приложениями iOS
Описываемые в этом разделе параметры политики можно [настроить](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) для политики управления мобильными приложениями (MAM) на портале Azure в колонке **Параметры**.

Существуют две категории параметров политики: параметры перемещения данных и доступа. В этом разделе термин *приложения, управляемые политикой* используется для обозначения приложений, которые настроены с помощью политик MAM.

##  <a name="data-relocation-settings"></a>Параметры перемещения данных

- **Запретить резервное копирование в iTunes и iCloud**: выберите **Да** для запрета или **Нет** для разрешения резервного копирования корпоративных данных из приложений, управляемых политикой.

  Значение по умолчанию — **Да**.

- **Разрешить приложению передавать данные в другие приложения**: выберите один из вариантов, чтобы указать приложения, которые могут получать данные из приложений, управляемых политикой.
  - **Приложения, управляемые политикой**: разрешить передачу только в приложения с политикой MAM.
  - **Все приложения**: разрешить передачу в любое приложение.
  - **Нет**: запретить передачу данных в любое приложение, включая другие приложения, управляемые политикой.

  Кроме того, если установить этот параметр в значения **Приложения, управляемые политикой** или **Нет**, будет заблокирована функция iOS 9, которая позволяет Spotlight Search искать данные в приложениях.

  >[!NOTE]
  >Этот параметр не управляет использованием функции "Открыть с помощью" на мобильных устройствах. Для управления функцией "Открыть с помощью" см. раздел [Управление передачей данных между приложениями iOS в Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Значение по умолчанию — **Приложения, управляемые политикой**.

- **Разрешить приложению принимать данные от других приложений**: укажите приложения, которые могут передавать данные в приложения, управляемые политикой.
  -  **Приложения, управляемые политикой**: разрешить передачу данных только из других приложений, управляемых политикой.
  -  **Все приложения**: разрешить передачу данных из любого приложения.
  -  **Нет**: запретить передачу данных из любого приложения.

  Значение по умолчанию — **Все приложения**.

- **Запретить операцию "Сохранить как"**: выберите **Да**, чтобы отключить возможность выбора команды "Сохранить как" во всех приложениях, использующих эту политику. Если вы хотите разрешить команду "Сохранить как", выберите **Нет**.

  Значение по умолчанию — **Да**.

- **Ограничить операции "вырезать", "копировать" и "вставить" с другими приложениями**: укажите, когда следует ограничивать операции вырезания, копирования и вставки. Выберите один из следующих типов.
  -   **Заблокировано**: запретить операции вырезания, копирования и вставки данных между приложениями, управляемыми политикой.
  -   **Приложения, управляемые политикой**: разрешить операции вырезания, копирования и вставки данных только между приложениями, управляемыми политикой.
  -   **Приложения, управляемые политикой, с добавлением из буфера**: разрешить операции вырезания и копирования данных между приложениями, управляемыми политикой. Разрешить вставку данных, вырезанных или скопированных в любом приложении, в это приложение.
  - **Любое приложение**: не ограничивать операции вырезания, копирования и вставки данных между приложениями.

  Значение по умолчанию — **Приложения, управляемые политикой, с добавлением из буфера**.

- **Ограничить веб-контент, отображаемый в Managed Browser**: если этот параметр включен, то любые ссылки в приложении будут открываться в Managed Browser.

  Для устройств, которые не зарегистрированы в Intune, можно разрешить открытие веб-ссылок из приложений, управляемых политикой, только в приложении Managed Browser.

  Если вы используете Intune для управления устройствами, см. статью [Управление доступом в Интернет с помощью политик управляемого браузера в Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Значение по умолчанию — **Да**.

- **Шифровать данные в приложении**: для приложений, связанных с политикой MAM, данные, находящиеся в неактивном состоянии, шифруются с использованием средств шифрования на уровне устройства, предоставленных ОС. Если требуется ввод ПИН-кода, данные шифруются в соответствии с параметрами политики MAM. Как указано в документации компании Apple, [модули, используемые iOS 7, имеют сертификат соответствия FIPS 140-2](http://support.apple.com/en-us/HT202739).

  В параметрах политики можно указать значения шифрования при использовании ПИН-кода. Эти значения определяют, когда данные шифруются. Доступны следующие параметры.
  -   **Когда устройство заблокировано**: все данные приложений, связанные с этой политикой, шифруются, пока устройство заблокировано.
  -   **Когда устройство заблокировано (кроме открытых файлов)**: все данные приложений, связанные с этой политикой, шифруются, пока устройство заблокировано, кроме данных из файлов, открытых сейчас в приложении.
  -   **После перезагрузки устройства**: все данные приложений, связанные с этой политикой, шифруются после перезагрузки устройства, пока устройство не будет разблокировано в первый раз.
  -   **Использовать параметры устройства**: данные приложений шифруются в соответствии с заданными на устройстве параметрами по умолчанию.
  Если этот параметр включен, для доступа к устройству пользователю требуется настроить и использовать ПИН-код.  Если ПИН-код для доступа к устройству отсутствует, приложения не открываются, а конечному пользователю предлагается задать ПИН-код путем отображения сообщения "Для доступа к приложению вам сначала нужно включить ввод ПИН-кода устройства".

  Значение по умолчанию — "Параметр шифрования не выбран".
- **Отключить синхронизацию контактов**: выберите **Да** для предотвращения синхронизации контактных данных со встроенным приложением адресной книги на устройстве. При выборе варианта **Нет** приложение сохранит контактные данные во встроенном приложении адресной книги на устройстве.

  При выборочной очистке в целях удаления корпоративных данных контакты, синхронизированные напрямую из приложения со встроенной адресной книгой, удаляются. Все контакты, синхронизированные из собственной адресной книги в другой внешний источник, нельзя очистить. В настоящее время это распространяется только на приложение Microsoft Outlook.

  Значение по умолчанию — **Да**.

- **Отключить печать**: выберите **Да**, чтобы запретить печать корпоративных данных из приложений, связанных с политикой MAM.

    Значение по умолчанию — **Да**.

##  <a name="access-settings"></a>Параметры доступа

- **Требовать ПИН-код для доступа**: выберите **Да**, чтобы затребовать ПИН-код для использования приложений, управляемых политикой. Пользователю предлагается настроить эту функцию при первом запуске приложения в рабочем контексте.

  Значение по умолчанию — **Да**.
    -  **Разрешить простой ПИН-код**: укажите, могут ли пользователи применять простые ПИН-коды, например 1234 или 1111. Значение по умолчанию — **Да**.
    - **Длина ПИН-кода**: укажите минимальное число цифр или символов в ПИН-коде. Значение по умолчанию — **4**.
    - **Число попыток до сброса ПИН-кода**: укажите число попыток ввода ПИН-кода, по достижении которого пользователь будет должен сбросить ПИН-код. Этот параметр не имеет значения по умолчанию.

- **Требовать отпечатки пальцев вместо ПИН-кода (iOS 8.0+)**: выберите **Да**, чтобы запрашивать отпечатки пальцев вместо ПИН-кода для доступа к приложению.
На устройствах iOS можно разрешить пользователю идентифицировать себя, используя отпечатки пальцев вместо ПИН-кода. Когда пользователь пытается получить доступ к этому приложению с помощью своей рабочей учетной записи, ему будет предложено вместо ПИН-кода предоставить удостоверение на основе отпечатков пальцев.

  Значение по умолчанию — **Да**.
- **Требовать для доступа учетные данные организации**: выберите **Да**, чтобы запрашивать корпоративные учетные данные вместо ПИН-кода для доступа к приложению. При выборе значения **Да** для этого параметра переопределяются требования для ПИН-кода или Touch ID. Пользователю будет предложено ввести свои корпоративные учетные данные.

  Значение по умолчанию — **Нет**.
- **Блокировать запуск управляемых приложений на устройствах со снятой защитой или с административным доступом**: выберите **Да**, чтобы блокировать запуск приложений на устройствах со снятой защитой или с административным доступом. Пользователь по-прежнему сможет использовать приложения в личных целях, однако для работы ему придется использовать другое устройство.

  Значение по умолчанию — **Да**.
- **Повторная проверка соблюдения требований к доступу через (в минутах)**
  -   **Время ожидания**: укажите время (в минутах), по истечении которого выполняется повторная проверка требований доступа для приложения.
  -   **Льготный период автономности**: если устройство находится в автономном режиме, укажите период времени (в минутах), по истечении которого выполняется повторная проверка требований доступа для приложения.

  Значения по умолчанию — **30** минут для времени ожидания и **720** минут для льготного периода автономности.
- **Интервал в автономном режиме до очистки данных приложения (дн.)**: вы можете настроить очистку данных компании для устройств, которые находятся в автономном режиме в течение определенного времени. В колонке параметров политики можно указать число дней, в течение которых устройство может находиться в автономном режиме, прежде чем с этого устройства будут удалены данные компании.

  >[!TIP]
  >Если ввести значение **0**, этот параметр будет отключен.

  Значение по умолчанию — **90** дней.



<!--HONumber=Dec16_HO2-->

