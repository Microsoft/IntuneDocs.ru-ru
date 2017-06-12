---
title: "Приложения Android с политиками защиты приложений | Документация Майкрософт"
description: "В этой статье описывается, что происходит при управлении приложением с помощью политик защиты приложений."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 64a31832012aba65c4ad5b1c3dc67fa4aa748246
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Что происходит при управлении приложением Android с помощью политик защиты приложений

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

В этой статье описывается работа пользователей с приложениями, содержащими политики защиты приложений. Политики защиты приложений применяются, только если приложения используются в рабочем контексте, например, когда пользователь получает доступ к приложениям с помощью рабочей учетной записи или обращается к файлам, которые хранятся в корпоративном хранилище OneDrive.
##  <a name="access-apps"></a>Доступ к приложениям

Приложение корпоративного портала требуется для всех приложений, связанных с политиками защиты приложений на устройствах Android.

Если устройство не зарегистрировано в Intune, на нем должно быть установлено приложение корпоративного портала. Однако пользователям не нужно запускать приложение корпоративного портала или входить в него, чтобы использовать приложения под управлением политик защиты приложений.

Приложение корпоративного портала позволяет Intune организовать безопасный общий доступ к данным. Таким образом, приложение корпоративного портала необходимо для всех приложений, связанных с политиками защиты приложений, даже если устройство не зарегистрировано в Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Использование приложений с поддержкой множественной идентификации

Политики защиты приложений применяются только в рабочем контексте. Таким образом, приложение может работать по-разному в зависимости от того, является контекст рабочим или личным.

Например, пользователь получает запрос на ввод ПИН-кода при доступе к рабочим данным. При работе с **приложением Outlook** пользователь получает запрос на ввод ПИН-кода при запуске приложения. При работе с **приложением OneDrive** пользователь получает запрос на ввод ПИН-кода при вводе рабочей учетной записи. В случае с Microsoft **Word**, **PowerPoint** и **Excel** пользователь получает запрос на ввод ПИН-кода, когда получает доступ к документам в корпоративном хранилище OneDrive для бизнеса.

##  <a name="manage-user-accounts-on-the-device"></a>Управление учетными записями пользователей на устройстве

Intune поддерживает развертывание политик защиты приложений только для одной учетной записи на каждом устройстве.

* В зависимости от приложения второй пользователь может блокироваться на устройстве. Однако действие политик защиты приложений всегда распространяется только на первого пользователя, к которому они применяются.

  * В приложениях **Microsoft Word**, **Excel** и **PowerPoint** вторая учетная запись пользователя не блокируется, но действие политик защиты приложений на нее не распространяется.

  * Для **приложений OneDrive** и **Outlook** можно использовать только одну рабочую учетную запись.  Вы не можете добавить несколько рабочих учетных записей для этих приложений.  Однако вы можете удалить пользователя и добавить другого пользователя на устройстве.


* Если до развертывания политик защиты приложений на устройстве было несколько учетных записей пользователей, политики Intune будут управлять только первой учетной записью, в которой они были развернуты.


Чтобы лучше понять, что происходит в ситуации с несколькими учетными записями пользователей, ознакомьтесь с приведенным ниже примером.

Пользователь A работает в двух организациях — **организации X** и **организации Y**. У пользователя A есть рабочая учетная запись в каждой организации, и в каждой из них для развертывания политик защиты приложений используется Intune. **Организация X** развертывает политики защиты приложений **раньше, чем** **организация Y**. К учетной записи, связанной с **организацией X**, будет применена политика защиты приложений, а к учетной записи, связанной с организацией Y, — нет. Если нужно, чтобы политики защиты приложений управляли учетной записью пользователя, связанной с организацией Y, следует удалить учетную запись, связанную с организацией X.
### <a name="add-a-second-account"></a>Добавление второй учетной записи
####  <a name="android"></a>Android
При использовании устройства Android вы можете увидеть сообщение о блокировке с инструкциями по удалению существующей и добавлению новой учетной записи.  Чтобы удалить существующую учетную запись, выберите **Параметры &gt; Общие &gt; Диспетчер приложений &gt; Корпоративный портал**. А затем выберите **Очистить данные**.

![Снимок экрана: сообщение об ошибке и инструкции по удалению учетной записи](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Просмотр файлов мультимедиа с помощью приложения Azure Information Protection
Для просмотра корпоративных звуковых и видеофайлов, PDF-файлов и файлов изображений на устройствах Android используйте [приложение Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (которое ранее называлось приложением для управления доступом Rights Management).

Его можно скачать в магазине Google Play.  

Поддерживаются следующие типы файлов:

* **Звук:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (улучшенный AAC+), AAC ELD (улучшенный AAC с низкой задержкой), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Видео:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Изображения:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG
* **Документы:** PDF, PPDF


|**PFILE**|**Текст**|
|----|----|
|Pfile — это универсальный формат-"оболочка" для защищенных файлов, в котором объединяются зашифрованное содержимое и лицензии Azure Information Protection. Его можно использовать для защиты файлов любого типа.|Текстовые файлы, в том числе XML, CSV и т. д., можно открыть для просмотра в приложении, даже если они защищены. Типы файлов: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.|

## <a name="next-steps"></a>Дальнейшие действия
[Что происходит при управлении приложением iOS с помощью политик защиты приложений](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>См. также
[Создание и развертывание политик управления мобильными приложениями с помощью Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
