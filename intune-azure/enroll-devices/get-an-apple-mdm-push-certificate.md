---
title: "Получение сертификата Apple MDM Push Certificate | Предварительная версия Intune Azure | Документация Майкрософт"
description: "Предварительная версия Intune Azure: инструкции по получению сертификата Apple MDM Push Certificate для управления устройствами iOS с помощью Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c0884ded1c8c55bb1b7968e483864b42f5bd6bde


---

# <a name="get-an-apple-mdm-push-certificate"></a>Получение сертификата Apple MDM Push Certificate 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune позволяет управлять мобильными устройствами iPad, iPhone и Mac OS X, а также предоставляет пользователям доступ к корпоративной электронной почте и приложениям. Для управления устройствами iOS и Mac с помощью Intune требуется сертификат службы push-уведомлений Apple (APNs). После тог как вы добавите этот сертификат в Intune, пользователи смогут установить приложение корпоративного портала для регистрации своих устройств. Или же вы сможете настроить управление корпоративными устройствами iOS.

**Получение сертификата MDM Push Certificate**<br>

На портале Azure выберите **Больше служб**, в текстовом поле введите **Intune**, а затем выберите **Другое** > **Intune**. В колонке Intune выберите **Регистрация устройств** > **Apple MDM Push Certificate** и следуйте инструкциям на портале Azure, которые приведены ниже.

**Шаг 1. Скачайте запрос на подписание сертификата Intune, необходимый для создания сертификата Apple MDM Push Certificate.**<br>
Выберите **Скачать CSR**, чтобы скачать CSR-файл и сохранить его локально. CSR-файл используется для запроса сертификата отношений доверия с портала сертификатов push-уведомлений Apple.

**Шаг 2. Создайте сертификат MDM Push Certificate.**<br>
Выберите **Создать собственный сертификат MDM Push Certificate**, чтобы перейти на портал сертификатов Apple Push. Войдите с помощью идентификатора Apple ID вашей организации, чтобы создать сертификат Push Certificate с помощью CSR-файла. Нажмите кнопку **Отправить** на портале сертификатов Apple Push Certificate, чтобы получить JSON-файл. Не используйте этот файл для сертификата Push Certificate. Завершите скачивание, вернитесь на страницу "Сертификаты сторонних серверов" портала сертификатов push-уведомлений Apple и нажмите кнопку **Скачать**. Скачайте Push Certificate (PEM-файл) и сохраните его локально.
Примечание

**Шаг 3. Введите идентификатор Apple ID, который вы использовали для создания сертификата Apple MDM Push Certificate.**

**Шаг 4. Перейдите к сертификату Apple MDM Push Certificate для отправки.**<br>
Перейдите к файлу сертификата (PEM) и щелкните **Открыть**, а затем выберите **Передать**. С помощью Push Certificate служба Intune может зарегистрировать устройства iOS и управлять ими, применяя политику к зарегистрированным мобильным устройствам.



<!--HONumber=Feb17_HO1-->


