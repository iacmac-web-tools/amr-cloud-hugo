---
title: Шаг 1 - Загрузка файла
linktitle: Шаг 1 - Загрузка файла
toc: true
type: docs
date: "2019-11-07T00:00:00Z"
draft: false
menu:
  import-data:
    parent: Импорт данных
    weight: 4

weight: 4
---

## Типы файлов

После ознакомления с разделом **Важная информация** пользователь может приступить к загрузке данных в <span style="color:#2BA2E6">**AMRcloud**</span>.

{{% alert warning %}}

Важно!

- Онлайн-платформа поддерживает загрузку таблиц в формате .xlsx и .csv 
- Предварительный просмотр таблицы включает от 5 до 30 строк
- Панель "Настройка для csv файла" настраивает отображение таблицы, если в поле предварительного просмотра - таблица неструктурированная (Несколько строк и отсутствуют столбцы) 

{{% /alert %}}

{{< figure library="true" src="tutorials/import-data/choice_file.png" title="Загрузка файла" numbered="true" lightbox="true" >}}

{{< figure library="true" src="tutorials/import-data/step1.png" title="Предварительный просмотр таблицы" numbered="true" lightbox="true" >}}


{{% alert note %}}

На заметку!

Как сохранить таблицу в формате .csv? 

Что значит UTF-8 и Windows-1251? Как и когда применять UTF-8 в исходной таблице?

{{% /alert %}}

## Сохранение в csv

Открыть необходимую таблицу в Microsoft Excel, перейти в раздел *Файл* (левый верхний угол), затем выбрать пункт *Экспорт* **&rarr;** *Изменить тип файла* **&rarr;** *Другие типы файлов* **&rarr;** CSV (разделители запятые)(*.csv) 

{{< figure library="true" title="Переход во вкладку *Файл*" src="tutorials/import-data/file_for_export.png"  numbered="true" lightbox="true" >}}
{{< figure library="true" title="Сохранение в формате csv" src="tutorials/import-data/export_csv.png"  numbered="true" lightbox="true" >}}

## Кодировка текста

- *UTF-8* - самая распространенная кодировка текста, включает более двух миллионов символов: все современные алфавиты, цифры, знаки препинания, математические и специальные символы. 
- *UTF-8* является стандартной кодировкой текста веб-страниц.
- *Windows-1251* — набор символов и кодировка текста, являющаяся стандартной для русских версий Microsoft Windows до 10-й версии. Менее 1% веб-страниц используют кодировку *Windows-1251*.

Почему пользователю <span style="color:#2BA2E6">**AMRcloud**</span> следует ориентироваться в кодировке?

Алгоритмы <span style="color:#2BA2E6">**AMRcloud**</span> распознают кодировку и настраивают по необходимым требованиям работы платформы.

Несмотря на эти меры, пользователь может столкнуться с ситуацией, когда в таблице данные открываются "непонятными знаками - иероглифами" вместо текста. Как настроить кодировку и вернуть текст?

{{< figure library="true" title="Запись по типу *иероглифы*" src="tutorials/import-data/wrong_letters.png"  numbered="true" lightbox="true" >}}

Разберем возможные варианты поэтапного процесса "исправления" на примерах.

Важно отметить, что использование текстового редактора Sublime Text носит рекомендательный характер, не является оплаченной формой неличной передачи информации. Пользователь может использовать любой имеющийся текстовый редактор с настройкой кодинга.

### Ситуация 1.

При загрузке таблицы в <span style="color:#2BA2E6">**AMRcloud**</span> на шаге 1, в окне предварительного просмотра появляется надпись **"Не могу прочитать файл"**

{{< figure library="true" title="Ошибка прочтения файла" src="tutorials/import-data/unread.png"  numbered="true" lightbox="true" >}}

**Алгоритм решения:**

1. Скачать и установить бесплатный текстовый редактор  [Sublime Text](https://www.sublimetext.com/)
{{< figure library="true" title="Загрузка текстового редактора" src="tutorials/import-data/sublime_download.png"  numbered="true" lightbox="true" >}}

2. В установленном редакторе выбираем раздел file **&rarr;** Open File. 
{{< figure library="true" title="Выбор файла для исправления" src="tutorials/import-data/sublime_open.png"  numbered="true" lightbox="true" >}}
Выбираем в появившемся окне таблицу, которую не удалось открыть в <span style="color:#2BA2E6">**AMRcloud**</span>. Открывшийся документ должен быть представлен в виде сплошного текста, т.е. нет структуры таблицы как в Microsoft Excel. Можно увидеть "иероглифы".

3. Необходимо поочередно менять различные кодировки и ориентироваться на текст ("иероглифы" должны исчезнуть).
Рекомендуется начинать с *UTF-8* и и *Windows-1251*.
Раздел File **&rarr;** Reopen with Encoding **&rarr;** необходимая кодировка.
{{< figure library="true" title="Кодировка таблицы" src="tutorials/import-data/sublime_reopen.png"  numbered="true" lightbox="true" >}}
После выполненных действий пользователь сможет прочитать текст. "Иероглифы" исчезнут.

4. Файл необходимо сохранить.
File **&rarr;** Save with Encoding **&rarr;** *UTF-8*.
{{< figure library="true" title="Сохранение файла с UTF-8" src="tutorials/import-data/save_utf8.png"  numbered="true" lightbox="true" >}}


### Ситуация 2.

При загрузке данных в окне предварительного просмотра на Шаге 1, проблем не было. Пользователь провел анализ данных, скачал таблицу из <span style="color:#2BA2E6">**AMRcloud**</span>, и Microsoft Excel открывает данные с "иероглифами".

**Способ №1**
 
Необходимо скачать таблицу с кодировкой  *Windows-1251*. Для этого **не** переключать параметры, которые уже установлены в <span style="color:#2BA2E6">**AMRcloud**</span>.
 
{{< figure library="true" title="Скачивание файла из AMRcloud с настройками по умолчанию" src="tutorials/import-data/change_code.png"  numbered="true" lightbox="true" >}}

**Способ №2**

1. Скачать и установить бесплатный текстовый редактор [Sublime Text](https://www.sublimetext.com/)
{{< figure library="true" title="Загрузка текстового редактора" src="tutorials/import-data/sublime_download.png"  numbered="true" lightbox="true" >}}

2. В установленном редакторе выбираем раздел File **&rarr;** Open File. 
{{< figure library="true" title="Выбор файла для исправления" src="tutorials/import-data/sublime_open.png"  numbered="true" lightbox="true" >}}

3. Файл необходимо сохранить с кодировкой *Windows-1251*.
File**&rarr;** Save with Encoding **&rarr;** Windows-1251.
{{< figure library="true" title="Сохранение файла с кодировкой Windows-1251" src="tutorials/import-data/save_1251.png"  numbered="true" lightbox="true" >}}

Теперь можно просматривать таблицу, которая была скачана из онлайн-платформы <span style="color:#2BA2E6">**AMRcloud**</span>, на локальном компьютере.