# Разметка ранее затранскрибированного файла в системе ELAN

Для работы понадобится ELAN и файл транскрипции вашей записи LiveCorpus ...2.txt (то есть последняя версия транскрипции, в которой вы выверяли хезитации и вставляли теги о нестандартном произношении и т.п.)  

### 1. Уберите в файле транскрипции все xml теги  
* Создайте копию файла (например, rockclub2.txt -- Сохранить как -- rockclub3.txt)
* Удалите все теги в угловых скобках (регулярное выражение для замены: <.*?> )  

<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/TextWrangler_delete_tags.png" width="400" />

Было:
```
Валера@ Ну <distinct form="чё">что</distinct> их читать-то <distinct form="вапще">вообще</distinct>?
```

Стало:
```
Валера@ Ну что их читать-то вообще?
```

* Разделите метку говорящего и саму реплику знаком табуляции. В итоге у вас должен получиться файл с разделителем-табуляцией для двух столбцов.  

* Разбейте файл на реплики (минимальные диалогические единицы), ориентируясь на точку, `!`, `?` или знаки `\\` в вашей транскрипции. В начале каждой реплики должна идти метка говорящего.  
Используйте регулярные выражения для замены, чтобы сохранять метку говорящего в начале строки.

<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/TextWrangler_split_utterances.png" width="500" />

Было:  
```
Валера@	Ну что их читать-то вообще?
Наташа@	Ну как это? Зрители. Комментарии зрителей читать надо. Что нет?
Валера@	Если б они дело писали, а всякую муру...
```
Стало:  
```
Валера@ 	Ну что их читать-то вообще?
Наташа@ 	Ну как это?
Наташа@ 	Зрители.
Наташа@ 	Комментарии зрителей читать надо.
Наташа@ 	Что нет?
Валера@ 	Если б они дело писали, а всякую муру...
```
* Не забудьте сохранить отредактированный файл.  

### 2. В ELAN создайте новый проект (File -- New), привяжите к нему файл с вашей видео- (или аудио-) записью.  

### 3. Импортируйте текстовый файл в проект (File -- Import -- CSV/Tab-delimited file)  
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN_import_csv.png" width="400" />

* Как вы догадываетесь, теперь метка говорящего будет представлять имя слоя, а реплика -- аннотацию ELAN-а.  
* Укажите параметры импорта:
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN_import_csv1.png" width="600" />

Теперь проект должен выглядеть так:
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN3.png" />

### 4. Импортируйте типы слоев из шаблона [LiveCorpus_template](http://hseinstruments.wikispaces.com/file/detail/LiveCorpus_template_1speaker.etf) 
* Type -- Import...

### 5. Переименуйте слои в вашей аннотации по образцу Валера@text, Наташа@text, присвойте им тип Paragraph   
* Tier -- Change Tier Attributes...  
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN_change_tier.png" width="400" />

### 6. Перейдите в режим Выделения аннотаций и измените время начала и конца каждой реплики согласно времени звучания в записи.
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN_segmentation_mode.png" width="700" />

* Чтобы сдвинуть реплику, активируйте слой, в котором она располагается (двойным кликом на имени слоя) и двигайте мышкой саму реплику влево-вправа или ее границы.  
Вот так в результате выглядит мой файл:  

<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN4.png" width="800" />

* Если вы хотите объединить две аннотации в одну (сделать единую реплику):  
** выделите аннотацию, Right Click -- Merge with Next Annotation /Ctrl+A/ (или Merge with Previous Annotation /Ctrl+B/)

* Если вы хотите разделить аннотацию на две: наведите мышкой на точку разбиения и Right Click -- Split Annotation 

### 7. Токенизируйте каждый текстовый слой (необязательное задание)   
* Перейдите в режим аннотации (Option -- Annotation)  
* Для каждого говорящего создайте новый слой вида ...@word, связанный с родительским слоем ...@text отношением subdivision:  
<img src="https://github.com/olesar/hseinstruments/blob/master/FIGURES/ELAN_new_tier.png" width="400" />

* Токенизируйте каждый слой: Tier -- Tokenize tier... Подробности [тут](http://www.mpi.nl/corpus/html/elan/ch05s10.html).   

* Выставлять временные метки для каждого слова не нужно.   

### 8. В конце работы сохраните проект, загрузите .eaf файл в папку LiveCorpus вашего репозитория. 
