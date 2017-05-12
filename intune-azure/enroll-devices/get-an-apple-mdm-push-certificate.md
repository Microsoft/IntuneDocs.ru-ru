---
title: "Получение сертификата Apple MDM Push Certificate"
titleSuffix: Intune Azure preview
description: "Предварительная версия Intune Azure: инструкции по получению сертификата Apple MDM Push Certificate для управления устройствами iOS с помощью Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 91c6b063fbc17cf92aab50c4911e4bb33b76deb9
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Получение сертификата MDM Push Certificate

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune позволяет управлять мобильными устройствами iPad, iPhone и Mac, а также предоставляет пользователям доступ к электронной почте и приложениям организации. Для управления устройствами с iOS и Mac с помощью Intune требуется сертификат MDM Push Certificate. После добавления сертификата в Intune пользователи смогут установить приложение корпоративного портала для регистрации своих устройств. Также можно настроить управление корпоративными устройствами с iOS с помощью программы регистрации устройств Apple или регистрировать устройства, например с помощью Apple Configurator. Дополнительные сведения о вариантах регистрации см. в разделе [Выбор способа регистрации устройств с iOS](choose-ios-enrollment-method.md).

## <a name="steps-to-get-your-certificate"></a>Порядок получения сертификата
На портале Azure выберите пункты **Другие службы** > **Мониторинг и управление** > **Intune**. В колонке Intune выберите пункты **Регистрация устройств** > **Регистрация Apple** **Apple MDM Push Certificate** и следуйте инструкциям на портале Azure, которые приведены ниже.

**Шаг 1. Скачайте запрос на подписание сертификата Intune, необходимый для создания сертификата Apple MDM Push Certificate.**<br>
Выберите **Скачать CSR**, чтобы скачать CSR-файл и сохранить его локально. CSR-файл используется для запроса сертификата отношений доверия с портала сертификатов push-уведомлений Apple.

**Шаг 2. Создайте сертификат MDM Push Certificate.**<br>
Выберите **Создать собственный сертификат MDM Push Certificate**, чтобы перейти на портал сертификатов Apple Push. Войдите с помощью идентификатора Apple ID вашей организации, чтобы создать Push Certificate с помощью CSR-файла. Нажмите кнопку **Отправить** на портале сертификатов Apple Push Certificate, чтобы получить JSON-файл. Не используйте этот файл для сертификата Push Certificate. Завершите скачивание, вернитесь на страницу "Сертификаты сторонних серверов" портала сертификатов push-уведомлений Apple и нажмите кнопку **Скачать**. Скачайте Push Certificate (PEM-файл) и сохраните его локально.
Примечание

**Шаг 3. Введите идентификатор Apple ID, который вы использовали для создания сертификата Apple MDM Push Certificate.**

**Шаг 4. Перейдите к сертификату Apple MDM Push Certificate для отправки.**<br>
Перейдите к файлу сертификата (PEM) и щелкните **Открыть**, а затем выберите **Передать**. С помощью Push Certificate служба Intune может зарегистрировать устройства iOS и управлять ими, применяя политику к зарегистрированным мобильным устройствам.

