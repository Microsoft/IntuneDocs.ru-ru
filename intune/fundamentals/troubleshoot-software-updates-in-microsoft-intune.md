---
title: Устранение неполадок с обновлениями программного обеспечения в Microsoft Intune в Azure | Документация Майкрософт
description: Сведения о решении проблем с обновлениями программного обеспечения в Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ad8d904f72df169eea136c625a2f44d645cafbc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509755"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Устранение неполадок с обновлениями программного обеспечения в Microsoft Intune

Помощь в устранении проблем с обновлениями программного обеспечения в Microsoft Intune. Список и описание кодов ошибок см. в документации по [кодам ошибок агента обновления программного обеспечения в Microsoft Intune](../protect/software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Устройства Windows 7 с несколькими замененными обновлениями больше не отправляют отчеты в Intune

Клиенты Microsoft Intune могут демонстрировать один или несколько следующих симптомов:

- Устройства внезапно перестают отвечать в Intune.  
- Устройства характеризуются высоким потреблением ресурсов ЦП.
- Установка приложений в Intune выполняется медленно.
- Microsoft Intune Center отображает следующую ошибку: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- "Консоль администрирования Intune" > "Группы" > "Все устройства" > состояние: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Эта проблема может возникать, если замененные обновления (обновления, которые были заменены другим обновлением) не отклонялись в течение длительного периода. Во время определенных процессов, таких как установка приложения, Windows по очереди проверяет все замененные обновления, чтобы можно было правильно сопоставить эти обновления и их последователи. Если список замененных обновлений становится слишком большим, эта задача проверки может привести к высокой загрузке ЦП из-за рабочей нагрузки и увеличению требуемого времени. Это в первую очередь затрагивает устройства Windows 7 из-за большого количества заменяемых обновлений для Windows 7. Так как более новые операционные системы не имеют столько доступных заменяемых обновлений, эта проблема касается их в меньшей степени.

**Решение**

1. Войдите в [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Выберите **Обновления программного обеспечения**.
3. Отклоните все замененные обновления, которые могут применяться для Windows 7 или приложений (например, Microsoft Office), установленных на затронутых клиентах.
4. Перезапустите затронутые клиенты.

Если вы используете Windows 7, убедитесь, что установлено обновление [3050265 — клиент Центра обновления Windows для Windows 7 за июнь 2015 г.](https://support.microsoft.com/kb/3050265)

## <a name="next-steps"></a>Дальнейшие шаги

Получите [поддержку от корпорации Майкрософт](get-support.md) или обратитесь на [форумы сообщества](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).