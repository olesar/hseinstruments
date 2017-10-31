# AntConc -- корпусный менеджер

* [Страница программы](http://www.laurenceanthony.net/software/antconc/), где её можно скачать и посмотреть инструкции
* [Мануал](http://www.laurenceanthony.net/software/antconc/resources/help_AntConc321_english.pdf) (на английском)
* [Видео-тьюториал от автора](https://www.youtube.com/playlist?list=PLiRIDpYmiC0Ta0-Hdvc1D7hG6dmiS_TZj)
* [Тьюториал для семинара](https://drive.google.com/file/d/0B6-5pzCmb8MOblpzRXI3elFFeFU/view?usp=sharing)

## Материал для работы на семинаре
Анна Каренина: [text](https://drive.google.com/file/d/0B6-5pzCmb8MOVFBjajZJUHhNNmM/view?usp=sharing), [xml](https://drive.google.com/file/d/0B6-5pzCmb8MOTktNVlpjaDdOY2M/view?usp=sharing)

Война и Мир: [text](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/Vojna%20i%20mir.%20Tom%201.txt)

Тихий Дон: [text](https://github.com/ElizavetaKuzmenko/Programming-and-computer-instruments/blob/master/tihiyd.txt)

### Задание
* Загрузите файл, проверьте, что он отображается нормально (вкладка FileView).  
* Постройте частотный список слов романа (вкладка Word List, нажмите кнопку Start). Кликнув на слово, вы сможете попасть в конкорданс, построенный для этого слова.  
* В Word List отсортируйте частотный список по алфавиту (Sort by Word внизу страницы).     
* Постройте частотный список двух-, трех- и т.д. -словных словосочетаний (вкладка Cluster/N-Grams, поставьте галочку на N-Grams, укажите, сколько слов в ngram-е вы хотите видеть, например, Min:3, Max:3, установите порог вхождений в корпусе, например, 10). Кликнув на n-грам, вы также можете попасть в его конкорданс.    
* Постройте списки коллокатов выбранного вами слова (вкладка Collocates), указав границы окна справа  / слева.  

### Задание для тех, кто все очень быстро успел (дополнительное)
* Построить тот же список, игнорируя теги xml (см. xml-файл)
* Построить список двубуквенных сочетаний (используя [файл](https://drive.google.com/file/d/0B6-5pzCmb8MONVN6ektrNzJZbDg/view?usp=sharing), сначала изучив, как он устроен)
* Разметьте файл Анны Карениной с помощью [Mystem](https://tech.yandex.ru/mystem/) и постройте частотный список а) частей речи б) лемм.



