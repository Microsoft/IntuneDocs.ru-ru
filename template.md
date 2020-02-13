---
title:
- ЗАГОЛОВОК СТАТЬИ | ИМЯ СЛУЖБЫ
description: ''
keywords: ''
author:
- GITHUB USERNAME
manager:
- ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: ''
ms.service: ''
ms.technology: ''
ms.assetid:
- GET ONE FROM guidgenerator.com
ms.openlocfilehash: ed2d00541c2d89efd0f8cd6aa60f29c527656fc0
ms.sourcegitcommit: 5178aec0244e023e73546f3d10f1a76eaf1f4a3e
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "76971824"
---
# <a name="metadata-and-markdown-template"></a>Метаданные и шаблон разметки

Этот шаблон docs.ms содержит примеры синтаксиса Markdown, а также указания по настройке метаданных. Он расположен в корневом каталоге каждого репозитория пилотных проектов EM (например, ~/Azure-RMSDocs-pr /template.md) и может считываться как файл разметки. Чтобы просмотреть, как отображаются примеры, вы можете обратиться к [опубликованной версии](https://stage.docs.microsoft.com/en-us/rights-management/template).

При создании файла разметки следует скопировать шаблон в новый файл, заполнить метаданные в соответствии с приведенными ниже инструкциями, поместить заголовок H1 над названием статьи, а затем удалить содержимое. 


## <a name="metadata"></a>Метаданные 

Весь блок метаданных приведен выше. Он разделен на обязательные и необязательные поля. Дополнительные сведения см. в статье [OPS metadata cheatsheet](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) (Шпаргалка по метаданным OPS). Важные примечания:

- Между двоеточием (:) и значением элемента метаданных **должен** быть пробел.
- Если необязательный элемент метаданных не имеет значения, закомментируйте этот элемент с помощью символа # (не оставляйте значение пустым и не указывайте "Н/Д"). Когда вы добавляете значение для закомментированного элемента, не забудьте удалить символ #.
- Двоеточия в значении (например, title) разделяют элементы в средстве синтаксического анализа метаданных. На их месте используйте HTML-код &#58; (например, "title: Управление правами Azure&#58; основы| Azure RMS").
- **title**: заголовок, который отображается в результатах поисковой системы. Этот заголовок должен заканчиваться символом вертикальной черты ("|"), за которым следует имя службы (пример см. выше). Заголовок может не совпадать (возможно, и не должен совпадать) с заголовком H1. Он должен содержать примерно 65 символов, включая элемент "| ИМЯ СЛУЖБЫ".
- **author**, **manager**, **reviewer**: поле author должно содержать **имя пользователя GitHub** автора статьи, а не псевдоним.  Поля manager и reviewer, напротив, должны содержать псевдонимы. В поле ms.reviewer указывается имя руководителя проекта, связанного со статьей или службой.
- **ms.assetid**: это идентификатор GUID статьи с использованием прописных букв. При создании нового файла Markdown получите GUID на сайте [https://www.guidgenerator.com](https://www.guidgenerator.com). 
- **ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: допустимые значения для этих элементов можно найти [здесь](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).

## <a name="basic-markdown-and-gfm"></a>Базовая разметка Markdown и GitHub Flavored Markdown

Поддерживается вся базовая разметка Markdown и GitHub Flavored Markdown. Дополнительные сведения об этих разметках см. в следующих источниках:

- [документация по синтаксису базовой разметки Markdown](https://daringfireball.net/projects/markdown/syntax);
- [документация по GitHub Flavored Markdown (GFM)](https://guides.github.com/features/mastering-markdown).

## <a name="headings"></a>Заголовки

Примеры заголовков первого и второго уровня приведены выше. 

В статье **должен** быть только один заголовок первого уровня, который будет отображаться как заголовок страницы.  

Из заголовков второго уровня создается оглавление страницы, которое отображается в разделе "В этой статье" под заголовком страницы.

### <a name="third-level-heading"></a>Заголовок третьего уровня
#### <a name="fourth-level-heading"></a>Заголовок четвертого уровня
##### <a name="fifth-level-heading"></a>Заголовок пятого уровня
###### <a name="sixth-level-heading"></a>Заголовок шестого уровня

## <a name="text-styling"></a>Стиль текста

*Курсив* 

**Полужирный** 

~~Зачеркнутый~~



## <a name="links"></a>Links

Чтобы создать ссылку на файл Markdown в том же репозитории, используйте [относительные ссылки](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2). 

- Пример: [Что такое управление правами Azure?](./understand-explore/what-is-azure-rights-management.md)

Чтобы создать ссылку на заголовок раздела в том же файле Markdown, просмотрите исходный код опубликованной статьи, найдите идентификатор заголовка (например, `id="blockquote"`) и создайте ссылку в формате # + идентификатор (например, `#blockquote`).

- Пример: [Цитаты](#blockquote)

Чтобы создать ссылку на заголовок в файле Markdown в том же репозитории, используйте относительные ссылки и ссылки с хэштегами.

- Пример: [Технический обзор процедуры регистрации](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)

Чтобы создать ссылку на внешний файл, используйте в качестве ссылки полный URL-адрес.

- Пример: [Github](http://www.github.com)

Если URL-адрес указан в файле Markdown, он преобразуется в активную ссылку.

- Пример: http://www.github.com

## <a name="lists"></a>Списки

### <a name="ordered-lists"></a>Упорядоченные списки

1. Этот. 
1. Список.
1. Является.
1. Упорядоченный
1. Список  


#### <a name="ordered-list-with-an-embedded-list"></a>Список внутри упорядоченного списка

1. Здесь.
1. Приведен.
1. Встроенный.
1. Список:
    1. Мария Сазонова;
    1. Юрий Богданов.
1. упорядоченный
1. список


### <a name="unordered-lists"></a>Неупорядоченные списки

- Этот.
- есть
- a
- Маркированный.
- список


#### <a name="unordered-list-with-an-embedded-lists"></a>Списки внутри неупорядоченного списка

- Этот. 
- маркированный 
- список
  - Миссис Пикок
  - Мистер Грин
- содержит  
- другой
    1. Василий Бутусов;
    1. Ольга Зуева.
- Списки.


## <a name="horizontal-rule"></a>Горизонтальное правило

---

## <a name="tables"></a>Таблицы

| Таблицы        | это очень удобный           | Хорошо  |
| ------------- |:-------------:| -----:|
| Столбец 3 выровнен      | по правому краю | 1600 руб. |
| Столбец 2 выровнен      | по центру      |   12 руб. |
| Столбец 1 по умолчанию выровнен | по левому краю     |    1 долл. США |


## <a name="code"></a>код

### <a name="codeblock"></a>Блок кода

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a>Встроенный код

Это пример встроенного кода: `in-line code`.

## <a name="blockquotes"></a>Цитаты

> Засуха продолжалась десять миллионов лет, и царству ужасных ящеров уже давно пришел конец. Здесь, близ экватора, на материке, который позднее назовут Африкой, с новой яростью вспыхнула борьба за существование, и еще не ясно было, кто выйдет из нее победителем. На этих пустынных иссушенных землях могли выжить или, скорее, получить надежду на выживание только самые маленькие, самые хитрые или самые свирепые.

## <a name="images"></a>Образы

### <a name="static-image"></a>Статическое изображение

![Это замещающий текст](./media/AzRMS_elements.png)

### <a name="linked-image"></a>Связанное изображение

[![Замещающий текст для связанного изображения](./media/AzRMS_elements.png)](https://azure.microsoft.com) 

### <a name="animated-gif"></a>Анимационный GIF

![анимированный GIF](./media/hololens.gif)

## <a name="alerts"></a>Предупреждения

### <a name="note"></a>Примечание

> [!NOTE]
> Это ПРИМЕЧАНИЕ

### <a name="warning"></a>Предупреждение

> [!WARNING]
> Это предупреждение.

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

## <a name="docsms-extensions"></a>Расширения docs.ms

### <a name="button"></a>Кнопка

> [!div class="button"]
[кнопки со ссылками](/rights-management)

### <a name="selector"></a>Селектор

> [!div class="op_single_selector"]
- [иллюстрация](/rights-management/template.md)
- [bar](/rights-management/scratch.md)

### <a name="step-by-step"></a>Пошаговые инструкции

>[!div class="step-by-step"]
[Назад](https://www.example.com)
[Далее](https://www.example.com)
