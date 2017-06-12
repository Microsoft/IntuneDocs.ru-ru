---
title: "Добавление приложений для компьютеров Windows, на которых выполняется программный клиент Intune | Документы Майкрософт"
description: "В этом разделе описывается, как добавить в Intune приложения для компьютеров с Windows перед их развертыванием."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 41823544901f0ae2c87cba4e8591446068b8d144
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Добавление приложений для компьютеров Windows, на которых выполняется программный клиент Intune

В этом разделе описывается, как добавить приложения в Intune перед их развертыванием.

> [!IMPORTANT]
> Сведения в этом разделе помогут вам добавить приложения для компьютеров Windows, которые управляются с помощью программного клиента Intune. Если нужно добавить приложения для зарегистрированных компьютеров с Windows и мобильных устройств, см. раздел [Добавление приложений для мобильных устройств в Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

Приложения, устанавливаемые на ПК, должны поддерживать автоматическую установку без участия пользователя. В противном случае произойдет сбой установки.


## <a name="add-the-app"></a>Добавление приложения
В этой процедуре используется издатель ПО Intune для настройки свойств приложения и его отправки в облачное хранилище.

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) последовательно выберите **Приложения** &gt; **Добавить приложения**, чтобы запустить издатель ПО Intune.

    > [!TIP]
    > Перед запуском издателя может потребоваться ввести имя пользователя и пароль Intune.

2.  На странице **Установка ПО** издателя в разделе **Выберите, каким образом будет предоставляться доступ к этой программе для устройств** выберите **Установщик программ** и укажите следующее:

    - **Выберите тип файла установщика программ**. Указывает тип программного обеспечения, которое необходимо развернуть. Для компьютера с Windows выберите **Установщик Windows**.
    - **Укажите расположение файлов установки ПО**. Введите расположение файлов установки или нажмите кнопку **Обзор**, чтобы выбрать расположение из списка.
    - **Добавлять дополнительные файлы и вложенные папки из одной и той же папки**. Для некоторых программ, использующих установщик Windows, требуются вспомогательные файлы. Они должны находиться в той же папке, что и файл установки. Выберите этот параметр, если помимо прочего требуется развернуть эти дополнительные файлы.

    Например, если вы хотите опубликовать в Intune приложение с именем Application.msi, страница будет выглядеть так: ![Страница установки программного обеспечения издателя](./media/publisher-for-pc.png)

   Этот тип установки использует определенное пространство в облачном хранилище.

3.  На странице **Описание ПО** настройте следующие параметры.

    > [!NOTE]
    > В зависимости от используемого файла установщика некоторые из этих значений могут быть введены автоматически или могут не отображаться.

    - **Издатель**. Введите имя издателя приложения.
    - **Имя**. Введите имя приложения так, как оно будет отображаться на корпоративном портале.<br />Убедитесь, что все имена приложений являются уникальными. Если имя приложения существует два раза, пользователи корпоративного портала увидят только одно из приложений.
    - **Описание**. Введите описание приложения. Оно будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес страницы сведений о ПО** (необязательно). Введите URL-адрес веб-сайта со сведениями об этом приложении. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес политики конфиденциальности** (необязательно). Введите URL-адрес веб-сайта со сведениями о политике конфиденциальности для этого приложения. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **Категория** (необязательно). Выберите одну из встроенных категорий приложений. Это облегчит поиск приложения при просмотре пользователями корпоративного портала.
    - **Значок** (необязательно). Загрузите значок, который будет связан с приложением. Это значок, который будет отображаться с приложением при просмотре пользователями корпоративного портала.

4.  На странице **Требования** укажите требования, которые должны быть выполнены перед установкой приложения. Выберите один из следующих типов.

    - **Архитектура**. Укажите ОС для установки: 32-разрядная, 64-разрядная версия или обе.
    - **Операционная система**. Выберите минимальную операционную систему, в которой можно установить это приложение.

5.  На странице **Правила обнаружения** можно настроить правила для определения того, установлено ли уже на компьютере настраиваемое вами приложение. Или использовать правила обнаружения по умолчанию для автоматической перезаписи всех ранее установленных версий приложения. Этот параметр предназначен для установщика Windows (только EXE-файлы).

    Ниже приведены правила, которые вы можете настроить.
    - **Файл существует**. Укажите путь к файлу, который нужно обнаружить. Вы можете выполнить поиск в разделе **%ProgramFiles%** (поиск выполняется в **Program Files**\&lt;путь&gt; и **Program Files (x86)**\&lt;путь&gt;) на ПК или в **%SystemDrive%** (поиск выполняется с корневого диска ПК, обычно с диска C).
    - **Код продукта MSI существует**. Нажмите кнопку **Обзор** для выбора файла установщика Windows (MSI), который необходимо обнаружить.
    - **Раздел реестра существует**. Укажите раздел реестра, который начинается с **HKEY_LOCAL_MACHINE\**. Поиск выполняется по обоим путям к реестру в 32- и 64-разрядной версиях. Если указанный раздел существует, правило обнаружения удовлетворяется.

    Если приложение соответствует любому из настроенных правил, оно не устанавливается.

6.  Только для типа файла **установщика Windows** (MSI и EXE): на странице **Аргументы командной строки** выберите, нужно ли указывать для установщика необязательные аргументы командной строки.
    Следующие параметры Intune добавляет автоматически.
    - Для EXE-файлов добавляется **/install**.
    - Для MSI-файлов добавляется **/quiet**.
    Обратите внимание, что эти параметры можно использовать, только если создатель пакета приложения предоставил эту возможность.

7.  Только для типа файла **установщика Windows** (только EXE): на странице **Коды возврата** вы можете добавить новые коды ошибок, которые интерпретируются Intune при установке приложения на управляемый компьютер с Windows.

    По умолчанию Intune использует стандартные коды возврата для оповещения об успешной или неправильной установке пакета приложения: **0** — успешно, **3010** — успех при перезапуске. Кроме того, в этот список вы можете добавить собственные коды возврата. Если указан список кодов возврата и при установке приложения возвращается код, который отсутствует в списке, он интерпретируется как ошибка.

8.  На странице **Сводка** проверьте указанные сведения. Когда будете готовы, нажмите кнопку **Отправить**.

9. Чтобы завершить работу мастера, нажмите кнопку **Закрыть**.

Приложение отображается в узле **Приложения** в рабочей области **Приложения**.

## <a name="next-steps"></a>Дальнейшие действия

После создания приложения его необходимо развернуть. Дополнительные сведения см. в статье [Развертывание приложений с помощью Microsoft Intune](deploy-apps.md).

Советы и рекомендации по развертыванию программного обеспечения на ПК с Windows см. в записи блога [Советы службы поддержки: рекомендации по распространению программного обеспечения Intune на ПК](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/).
