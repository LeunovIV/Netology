# Домашнее задание по теме: Обзор IT-систем cредства автоматизации и основные функции систем

## Кейс 1.
Какой вариант решения задач ниже (1.1-1.6) вы выберете? Коротко объясните, почему именно такой вариант вы выбрали.
Вариант решения:
А) делать вручную, B) использовать программу [1], C) написать скрипт [2].

### Задача: 
1.1 Обработать один текстовый файл, заменив в нём все слова “ООО Винни Пух” на “АО Пятачок”

#### Ответ: 
Почти в любом редакторе(если говорим о виндовс) образно назовём это «ctrl+f» и там будет заменить

### Задача: 
1.2 Найти строчки, содержащие слово “interface”, среди 10 000 текстовых файлов в одном каталоге 

#### Ответ: 
notepad++ «Ctrl+Shift+F» указываем слово 

### Задача: 
1.3 Найти повторяющиеся строки в текстовом файле, содержащем 10 строк вида:
192.168.0.1  
192.168.1.2

#### Ответ: 
grep –n '*' ./filename.txt

где * - шаблон поиска, например 192.168.0.1
./filename.txt – путь и имя файла в котором ищем

### Задача: 
1.4 Заменить все символы “$” на символ “€” в тексте на 1 страницу А4

#### Ответ: 
не понимаю чем данная задача отличается от 1.1. Ответ тот же.

### Задача: 
1.5 Посчитать количество файлов в папке

#### Ответ: 
я думаю вариантов тут множество, в виндовс самое простое нажать правой кнопкой мыши и посмотреть свойство папки, там будет информация о количестве файлов и подпапок.

### Задача: 
1.6 Найти повторяющиеся строки в текстовом файле, содержащем 10 000 строк вида:
192.168.0.1
192.168.1.2

#### Ответ: 
Аналогично 1.3
grep –n '*' ./filename.txt

где * - шаблон поиска, например 192.168.0.1
./filename.txt – путь и имя файла в котором ищем





## Кейс 2.
### Задача: 
Предположим, что вы не владеете инструментом автоматизации - например, языком программирования. Вам руководитель поставил задачу, которую можно решить как вручную, так и почитав статьи в интернете и написав скрипт по аналогии.
Вопрос: на основании чего вы будете решать - делать эту задачу вручную или попытаться автоматизировать решение задачи? Обоснуйте свой ответ.

#### Ответ: 
Из своего опыта я возьму решение подобной задачи из интернета и по аналогии напишу скрипт (на пример bat файл) потратив на это в три раза больше времени изначально, но в последующем на основе уже имеющихся знаний подобные задачи буду делать в несколько раз быстрее. 
Пример из молодости моей: поставили задачу копирования общей папки для возможности восстановления нечаянно удаленных файлов. Потратив несколько дней в интернете, я написал последовательность команд (bat файл) и в дальнейшем я начал копировать 1С и другое изменяя пару строк. Позже я узнал о существовании специальных программ для резервного копирования.


## Кейс 3.
### Задача: 
Как вы думаете, в чем причина популярности виртуальных серверов последнее время? В чем преимущество виртуальных серверов перед физическими серверами? Какие недостатки есть у виртуальных серверов?

#### Ответ:
Основные, но не все, преимущества:
1) есть возможность ограничивать\выделять ресурсы для виртуальным машин (меньше возможностей «простаивания» ресурсов, когда на железном сервере 1С использует почти всю оперативную память, при этом процессор почти не задействован и простаивает) 
2) нет привязки к железу, можно перенести на другой физический сервер, 0часто без остановки предоставления сервиса
3) упрощение резервирования серверов
4) экономия на железе (на одной железке поднять 10 серверов и не покупать 10 железок) 
5) безопасность от компрометации ОС
6) можно сделать шаблон виртуальной машины и развернуть новый сервис за минимальное количество времени


Недостатки:
1) необходим более квалифицированный IT специалист, который сможет не только виндовс поставить. 
2) общее дисковое пространство и увеличение нагрузки на канал связи
3) выход из строя железа влечёт остановку сразу всех сервисов, если нет резервного сервера.
4) необходимость для каждой виртуальной машины выделять дисковое пространство и минимальное кол-во ОЗУ под операционные сервисы. 






## Кейс 4.
Какой из вариантов решения вы выберете для каждой из ситуаций (4.1-4.7)? Коротко объясните, почему вы сделали такой выбор.[1]
Вариант решения:
A) Физический сервер, B) виртуальный сервер [2], C) контейнеры [3], D) SaaS [4], E) Прочее (предложите свой вариант).
Ситуации:

### Задача: 
4.1 Почтовый сервер для небольшой компании из 15 человек без постоянного администратора

#### Ответ:
SaaS – т.к. для такого не большого количества пользователей нет необходимости приобретать дорогостоящее оборудование и тратиться на IT специалиста, который будет сопровождать софт и железо. 

### Задача: 
4.2 Сервер для хранения старых резервных копий

#### Ответ:
Тут всё зависит от объёмов. У меня есть пример, когда проще купить облако 1 на ТБ и делать туда архивные копии. Тут мы упираемся в скорость интернета, но экономим на железе.
Когда же необходимы большие объёмы, то проще физический сервер или ленточная библиотека. Скорость выше, цена за гигабайт меньше.

### Задача: 
4.3 Сервер для тестирования приложений в разных окружениях (версиях ОС, версиях языка программирования, и т.д.)

#### Ответ:
Тут виртуализация. Т.к. есть возможность быстрого копирования состояния виртуальной машины(снапшот) или быстрого развертывания чистой системы для тестирования, а также сделать копию виртуалки для тест сервера.

### Задача: 
4.4 Web-сервер для размещения сайта компании

#### Ответ:
Тут всё зависит от сайта, но в подавляющем большинстве, по моему мнению достаточно SaaS, зачем покупать\содержать\поддерживать железо, если уже всё есть, только обновляй информацию через вэб

### Задача: 
4.5 Старое ПО, работающее только на Windows XP

#### Ответ:
Из практики – железный сервер, желательно на старом железе и образом системы на внешнем носителе

### Задача: 
4.6 Почтовый сервер в компании из 1500 человек и с собственным ИТ отделом

#### Ответ:
Сначала я подумал «Тут в самом вопросе, по моему, уже дан ответ – есть собственный ИТ отдел». При таком кол-ве пользователей уже проще поднять свой сервер. 
Но немного поразмыслив, я бы сравнил стоимость оборудования, сопровождения, защиты и т.д. со стоимостью аренды мощностей в облаке (IaaS) уже после взвешивания всех за и против принимал решение


### Задача: 
4.7 Несколько одинаковых серверов, позволяющих запускать и останавливать экземпляры программ по мере необходимости

#### Ответ:
Одинаковые сервера или сервера для тестирования обычно разворачиваются через контейнеры т.к. это максимальное масштабирование за минимальные сроки




## Кейс 5.
### Задача: 
Как вы думаете, что правильнее мониторить:
•	инфраструктуру изнутри (свободное место на диске, загрузку процессора и т.д.)
•	или сервисы снаружи (как их видит клиент - например, доступность сайта)?
Обоснуйте свой выбор.

#### Ответ:
Мониторить инфраструктуру нужно т.к. таким образом мы можем предугадать проблему и решить её до возникновения «падения сервиса», но если мы предоставляем сервисы внешним клиентам, то доступность таких сервисов, из вне, для нас приоритет имеют – мониторим сервисы снаружи, не забывая настроить забикс и на внутренние ресурсы.


## Кейс 6.
Какое из этих вариантов облачных решений вы бы выбрали под каждую из ситуаций (6.1-6.5)? Обоснуйте свой выбор.
Вариант решения:
A) SaaS, B) PaaS, C) IaaS
Ситуации:

### Задача: 
6.1 Сервер с типовой программой CRM для контроля взаимодействия менеджеров с клиентами

#### Ответ:
SaaS – зачем придумывать велосипед, когда уже всё написано и поднято за нас

### Задача: 
6.2 Почтовый сервер для небольшой компании, которой необходима тонкая настройка антиспам фильтров и антивируса для писем

#### Ответ:
По моему мнению в 99% случаев для маленькой компании достаточно того, что предоставляет гугл, яндекс и д.р. SaaS

Я понимаю, что верный ответ тут будет PaaS, но если прям хочется тонко настраивать, то арендуем\покупаем сервер в ЦОДе или IaaS и тратим много много денег на защиту, сопровождение и аренду мощностей, думаю посчитав все за и против, маленькая компания придёт к какому-нибудь гуглу и на этом остановится. 



### Задача: 
6.3 Веб-сервер для сайта-визитки (одностраничный лендинг) компании

#### Ответ:
Тут SaaS

### Задача: 
6.4 Территориально распределенный между несколькими датацентрами отказоустойчивый кластер почтовых серверов

#### Ответ:
IaaS – я так понимаю, покупаем инфраструктуру и настраиваем репликации

### Задача: 
6.5 Почтовый сервер для небольшой компании из 15 человек без постоянного администратора

#### Ответ:
Тут SaaS


## Кейс 7.
### Задача: 
Нужно ли делать резервное копирование в ситуациях ниже (7.1-7.6)? Коротко объясните, почему вы так решили.
•	7.1 Перед внесением изменений в конфигурационный файл на сервере
•	7.2 Перед удалением с сервера рабочей папки уволенного сотрудника
•	7.3 Перед применением обновления на работающее ПО на сервере
•	7.4 Перед изменением документа, лежащего в общем доступе, в режиме “только чтение”
•	7.5 Перед копированием файла из папки проекта на рабочий стол
•	7.6 Перед обновлением операционной системы

#### Ответ:
Есть такое правило: перед любыми работами сделай бэкап.
7.1 обязательное резервирование для возможности отката и минимизации простоя.
7.2 в таких случаях у меня есть укромная папка на файловом сервере которая называется «Уволенные» 
7.3 обязательное резервирование для возможности отката в предыдущей версии и минимизации простоя.
7.4 в данной ситуации в резервном копировании перед внесением изменений нет необходимости, у нас же все папки бэкапятся с определенной переодичностью.
7.5 мы создаём ещё одну копию имеющегося файла себе на рабочий стол, оригинал будет резервной копией
7.6 Перед такими глобальными работами делаем снапшот или полный образ системы на внешний носитель, если это не виртуальный компьютер
Админы делятся на 3 вида:
1) кто не делает бэкап
2) кто делает
3) тот кто проверяет сделанные бэкапы












