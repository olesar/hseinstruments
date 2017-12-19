# Форматы данных и их валидация

## Текстовые форматы. Markup languages.
* txt  
* scv  
** tsv - tab-separated  
* rtf (текстовый сконвертированный формат для .doc, .xls, .ppt)  
* html  
* xml  
* json  
* protobuf  

## Что делать?

* Берете файл xml.  

* Копируете её в валидатор -- <http://codebeautify.org/xmlvalidator>. Смотрите, какие в вашем XML нашлись ошибки:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/validator.png)

Все эти ошибки нужно исправить. Все они по большей части касаются тэга `distinct`. Вот так он выглядит обычно:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/distinct1.png)

А вот таким должен быть:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/distinct2.png)

Такая же проблема для тэгов `span` и `noindex`. Такие они сейчас:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/noindex1.png)

Такими они должны стать:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/noindex2.png)

Всё это не нужно делать руками, а нужно делать с помощью регулярных выражений в редакторе (см. опцию "Найти и заменить" в редакторе Notepad++)

Ошибок больше нет, когда мы получили заветный вердикт:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/valid.png)

* Теперь нужно расставить тэги для говорящих, схематически это выглядит так: `<speach role="Дедушка" sex="муж"> Реплика </speach>`, где _Реплика_ -- это одно или более предложений, которые принадлежат одному говорящему. Например, сейчас в вашем тексте говорящий отмечен так:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/speach1.png)

А должно стать так:

![](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/images/speach2.png)

В начале реплики стоит открывающий тэг с атрибутами, а в конце -- закрывающий! (Что он именно `speach`, а не `speech` -- не ошибка.) Сделать это также можно в Notepad++: найти строку, в которой размечен ваш говорящий, например, `<w>Елена<ana lex="елена" gr="S,persn,f,anim=nom,sg"/></w>@` и заменить его на `<speach role="Елена" sex="жен">`. После этого добавить закрывающие тэги, заменив `<speach` на `</speach>\n<speach` (вставить закрывающий тэг перед открывающим, необходимо отметить опцию "Расширенные символы" в Notepad++).

* Сейчас последний шанс исправить те опечатки, которые у вас оставались с предыдущих этапов работы! Также удалите всякий мусор, если он у вас в расшифровке есть. На неснятую омонимию не обращайте внимания, неправильные тэги заново не удаляйте -- мы сами это доисправляем с помощью данных из брата.

* После этого ещё раз отвалидируйте готовый XML.

* Выложите на гитхаб.
