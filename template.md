---
title: "ЗАГОЛОВОК СТАТЬИ | ИМЯ СЛУЖБЫ"
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: 02fb1274ae0dc11288f8bd9cd4799af144b8feae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2017
---
# <a name="metadata-and-markdown-template"></a>Метаданные и шаблон разметки

Этот шаблон docs.ms содержит примеры синтаксиса разметки, а также указания по настройке метаданных. Он расположен в корневом каталоге каждого репозитория пилотных проектов EM (например, ~/Azure-RMSDocs-pr /template.md) и может считываться как файл разметки. Чтобы просмотреть, как отображаются примеры, вы можете обратиться к [опубликованной версии](https://stage.docs.microsoft.com/en-us/rights-management/template).

При создании файла разметки следует скопировать шаблон в новый файл, заполнить метаданные в соответствии с приведенными ниже инструкциями, поместить заголовок H1 над названием статьи, а затем удалить содержимое. 


## <a name="metadata"></a>Метаданные 

Весь блок метаданных приведен выше. Он разделен на обязательные и необязательные поля. Дополнительные сведения см. в статье [OPS metadata cheatsheet](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) (Шпаргалка по метаданным OPS). Важные замечания.

- Между двоеточием (:) и значением элемента метаданных **должен** быть пробел.
- Если необязательный элемент метаданных не имеет значения, закомментируйте этот элемент с помощью символа # (не оставляйте значение пустым и не указывайте "Н/Д"). Когда вы добавляете значение для закомментированного элемента, не забудьте удалить символ #.
- Наличие двоеточия в значении (например, в заголовке) ведет к ошибке синтаксического анализатора метаданных. Вместо двоеточия используйте код HTML &#58; (например, "title: управление правами Azure&#58; основы | Azure RMS").
- **title**: это заголовок, который будет отображаться в результатах поиска. Заголовок должен заканчиваться символом "|", за которым следует имя службы (пример см. выше). Заголовок не обязательно должен (или вовсе не должен) совпадать с заголовком H1. Его длина должна быть примерно 65 символов (включая строку "| ИМЯ СЛУЖБЫ" в конце).
- **author**, **manager**, **reviewer**. В поле author указывается **имя пользователя Github** автора, а не псевдоним.  С другой стороны, в полях manager и reviewer используются псевдонимы. В поле ms.reviewer указывается имя менеджера, связанного со статьей или службой.
- **ms.assetid**: это идентификатор GUID статьи из CAP. Чтобы получить GUID при создании нового файла разметки, воспользуйтесь службой [https://www.guidgenerator.com](https://www.guidgenerator.com). 
- **ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: допустимые значения этих элементов указаны [здесь](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).

## <a name="basic-markdown-and-gfm"></a>Основная разметка и GFM

Поддерживаются все основные типы разметки и разметка для GitHub. Источники дополнительных сведений:

- [базовый синтаксис разметки Markdown](https://daringfireball.net/projects/markdown/syntax);
- [документация по синтаксису разметки Markdown для GitHub (GFM)](https://guides.github.com/features/mastering-markdown).

## <a name="headings"></a>Заголовки

Примеры заголовков первого и второго уровней приведены выше. 

Раздел может содержать **только один** заголовок первого уровня, который будет отображаться как заголовок страницы.  

Заголовки второго уровня участвуют в создании оглавления страницы, которое будет отображаться в разделе "В этой статье" под заголовком.

### <a name="third-level-heading"></a>Заголовок третьего уровня
#### <a name="fourth-level-heading"></a>Заголовок четвертого уровня
##### <a name="fifth-level-heading"></a>Заголовок пятого уровня
###### <a name="sixth-level-heading"></a>Заголовок шестого уровня

## <a name="text-styling"></a>Стиль текста

*Курсив* 

**Полужирный шрифт** 

~~Зачеркнутый~~



## <a name="links"></a>Links

Чтобы создать ссылку на файл разметки в том же репозитории, используйте [относительные ссылки](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2). 

- Пример: [Что такое управление правами Azure?](./understand-explore/what-is-azure-rights-management.md)

Чтобы создать ссылку на заголовок из того же файла разметки, просмотрите исходный код опубликованной статьи и найдите идентификатор заголовка (например `id="blockquote"`), после чего создайте ссылку с помощью конструкции # + идентификатор (например, `#blockquote`).

- Пример: [цитата](#blockquote).

Чтобы создать ссылку на заголовок из файла разметки в том же репозитории, используйте относительные ссылки и ссылки по хэш-тегам.

- Пример: [технический обзор процедуры регистрации](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process).

Чтобы создать ссылку на внешний файл, используйте полный URL-адрес.

- Пример: [GitHub](http://www.github.com).

Если в файле разметки встречается URL-адрес, он преобразуется в активную ссылку.

- Пример: http://www.github.com.

## <a name="lists"></a>Списки

### <a name="ordered-lists"></a>Упорядоченные списки

1. Это 
1. Представляет
1. Объект
1. Упорядоченный
1. Список  


#### <a name="ordered-list-with-an-embedded-list"></a>Список внутри упорядоченного списка

1. Здесь
1. будет
1. вставлен
1. встроенный
    1. Мисс Скарлет
    1. Профессор Плам
1. упорядоченный
1. список


### <a name="unordered-lists"></a>Неупорядоченные списки

- Это
- есть
- a
- маркированный
- список


##### <a name="unordered-list-with-an-embedded-lists"></a>Списки внутри неупорядоченного списка

- Это 
- маркированный 
- список
    - Миссис Пикок
    - Мистер Грин
- содержит  
- другой
    1. Полковник Муштард
    1. Миссис Уайт
- список


## <a name="horizontal-rule"></a>Горизонтальное правило

---

## <a name="tables"></a>Таблицы

| Таблицы        | это очень удобный           | инструмент  |
| ------------- |:-------------:| -----:|
| столбец 3      | выровнен по правому краю | 1600 долл. США |
| столбец 2      | выровнен по центру      |   12 долл. США |
| столбец 1 по умолчанию | выровнен по левому краю     |    1 долл. США |


## <a name="code"></a>код

### <a name="codeblock"></a>Блок кода

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a>Встроенный код

Это пример `in-line code`.

## <a name="blockquotes"></a>Цитата

> К этому моменту засуха длилась уже 10 миллионов лет, и царствование ужасных ящеров давно подошло к концу. Здесь, на экваторе, на континенте, который однажды получит название Африка, битва за выживание достигла новой кульминации жестокости, а о ее победителе еще нельзя было даже догадываться. На этих пустынных иссушенных землях могли выжить или, скорее, получить надежду на выживание только самые маленькие, самые хитрые или самые свирепые.

## <a name="images"></a>Образы

### <a name="static-image"></a>Статическое изображение

![это замещающий текст](./media/AzRMS_elements.png)

### <a name="linked-image"></a>Связанное изображение

[![это текст для связанного изображения](./media/AzRMS_elements.png)](https://azure.microsoft.com) 

### <a name="animated-gif"></a>Анимированный GIF

![анимированный GIF](./media/hololens.gif)

## <a name="alerts"></a>Предупреждения

### <a name="note"></a>Примечание

> [!NOTE]
> Это ПРИМЕЧАНИЕ

### <a name="warning"></a>Предупреждение

> [!WARNING]
> Это ПРЕДУПРЕЖДЕНИЕ

### <a name="tip"></a>Совет

> [!TIP]
> Это СОВЕТ

### <a name="important"></a>Важно

> [!IMPORTANT]
> Это ВАЖНО

## <a name="videos"></a>Видео

### <a name="channel-9"></a>Channel 9

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a>YouTube

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extentions"></a>расширения docs.ms

### <a name="button"></a>Кнопка

> [!div class="button"]
[кнопки со ссылками](/rights-management)

### <a name="selector"></a>Селектор

> [!div class="op_single_selector"]
- [иллюстрация](/rights-management/template.md)
- [панель](/rights-management/scratch.md)

### <a name="step-by-step"></a>Пошаговые инструкции

>[!div class="step-by-step"]
[Назад](https://www.example.com)
[Далее](https://www.example.com)