---
title: "Включение и исключение назначений приложений"
titlesuffix: Microsoft Intune
description: "Сведения о том, как включать и исключать назначения приложений в Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Включение и исключение назначений приложений в Microsoft Intune

Intune позволяет вам определять, у кого есть доступ к приложению, назначая включаемые и исключаемые группы. Используйте сочетание групповых назначений, чтобы включать и исключать группы пользователей или устройств, которым назначаются приложения. После выбора приложения вы можете указать способ его назначения. Эта возможность может оказаться полезной, когда для ограничения доступа к приложению сначала включается большая группа, а затем из нее исключается группа меньшего размера. В качестве группы меньшего размера можно выбрать, например, группу тестирования или руководящую группу. 

Исключайте из назначения только группы пользователей или группы устройств, не смешивая эти группы. При исключении групп Intune не учитывает сопоставление пользователей с устройствами. Включение групп пользователей с одновременным исключением групп устройств вряд ли обеспечит нужный вам результат, так как включение будет иметь приоритет над исключением. Например, если выбрать **Все пользователи** в качестве целевой группы приложения iOS и исключить **Все устройства iPad**, то в результате пользователи с iPad по-прежнему будут иметь доступ к приложению. Однако если выбрать в качестве целевой группы **Все устройства** и исключить **Все устройства iPad**, такое развертывание будет работать должным образом.  

>[!NOTE]
>При указании назначения группы для приложения тип **Неприменимо** является нерекомендуемым. Он заменен функциями исключения групп. 
>
>В консоли Intune для вашего удобства доступны предварительно созданные группы **Все пользователи** и **Все устройства** со встроенной оптимизацией. Настоятельно рекомендуем использовать эти группы для охвата всех пользователей и всех устройств, а не создавать группы "Все пользователи" и "Все устройства" самостоятельно.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Включение и исключение групп при назначении приложений 
Чтобы назначить приложение группам, используя включения и исключения, выполните следующие действия:
1. В колонке Microsoft Intune выберите **Мобильные приложения**.
2. Выберите **Приложения** в колонке **Мобильные приложения**. Появится список добавленных приложений.
3. Выберите приложение, которое хотите назначить. Отобразится панель мониторинга для приложения. 
4. Выберите **Назначения** в разделе **Управление**. 

    ![Назначение приложений Intune](./media/apps-inc-exl-01.png)
5. Выберите **Добавить группу**, чтобы добавить группу пользователей, которым назначено приложение. 
6. Выберите **Тип назначения** из доступных типов назначения в колонке **Добавление группы**.
7. Выберите **Доступно с регистрацией или без регистрации** в качестве типа назначения.

    ![Назначение приложений Intune — добавление группы](./media/apps-inc-exl-02.png)
8. Выберите **Включенные группы**, чтобы выбрать группы пользователей, которым должно быть доступно это приложение.

    >[!NOTE]
    >Если при добавлении группы какая-то другая группа уже включена с выбранным типом назначения, этот тип станет для нее фиксированным и выбрать для нее какой-то другой тип назначения будет невозможно. Поэтому вы не сможете включить эту уже используемую группу.

9. Выберите **Да**, чтобы сделать это приложение доступным для всех пользователей.

    ![Назначение приложений Intune — включение групп](./media/apps-inc-exl-03.png)
10. Нажмите кнопку **ОК**, чтобы задать включаемые группы.
11. Выберите **Исключенные группы**, чтобы выбрать группы пользователей, которым это приложение будет недоступно. 
12. Выберите группы для исключения. Пользователям в этих группах приложение будет недоступно.

    ![Назначение приложений Intune — исключение групп](./media/apps-inc-exl-04.png)
13. Щелкните **Выбрать**, чтобы произвести выбор групп.
14. Нажмите кнопку **ОК** в колонке **Добавление группы**. Отобразится список **Назначения** для приложения.
15. Щелкните **Сохранить**, чтобы активировать выбранные для приложения назначения групп.

При назначении групп уже назначенные или выбранные группы отключаются. Если вы хотите выбрать группу, которая сейчас отключена, удалите ее из списка назначений для приложения. Вы можете изменять назначения приложения в списке **Назначения**, выбрав в нем нужную строку. Кроме того, вы можете удалить назначение, щелкнув многоточие (…) в конце строки и выбрав **Удалить**. Представление списка **Назначения** можно изменить, сгруппировав его по **Типу назначения** или по состоянию **Включено/Исключено**.

![Назначение приложений Intune — завершение](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Дальнейшие шаги

* Дополнительные сведения о включении и исключении назначений групп для приложений см. в [блоге о Microsoft Intune](https://aka.ms/new_app_assignment_process).