# Домашнее задание к занятию "DNS"

## Задание 1.

Может ли компьютер работать без DNS? Будет ли работать сеть если в ней нет DNS-сервера?

Приведите ответ в свободной форме.

### Ответ: 

Для работы компьютера DNS вообще не нужен, он нужен людям, компьютеры могут общаться между собой, скажем по IP.
Если не настроить DNS, то для открытия ресурсов необходимо будет указывать IP адрес.

## Задание 2.

Кто выдает DNS имена?

Приведите ответ в свободной форме.

### Ответ: 

Internet Corporation for Assigned Names and Numbers - сокращённо ICANN. Международная некоммерческая организация, созданная 18 сентября 1998 года при участии правительства США для регулирования вопросов, связанных с доменными именами, IP-адресами и прочими аспектами функционирования Интернета

В Российском сегменте - это Координационный центр доменов .RU/.РФ, КЦ. Полное название АНО «Координационный центр национального домена сети Интернет» — администратор национальных доменов верхнего уровня .RU и .РФ. Выполняет функции национальной регистратуры, занимается администрированием национальных доменов.

## Задание 3.

Где в Linux настраивается DNS-клиент в простейшем случае?

Приведите ответ в свободной форме.

### Ответ: 

в самом простом случае клиент смотрит в файле /etc/host 


## Задание 4.

Для чего служит ресурсная DNS запись типа MX?

Приведите ответ в свободной форме.

### Ответ: 

Ресурсная DNS запись типа MX служит для указания почтового шлюза для домена.
MX запись состоит из 2 частей:
1) приоритет - чем выше приоритет, тем меньше число (например 10 имеет больший приоритет, чем 20)
2) адрес узла


# Дополнительные задания (со звездочкой)*
# Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

## Задание 5.

Настройте кэширующий DNS сервер BIND.

С любого клиента отправьте запрос на преобразование адреса netology.ru.

С помощью утилиты dnstop посмотрите какие входящие и исходящие запросы обрабатывались DNS-сервером.

Пришлите скриншот, на котором в выводе команды dnstop будут отбражены внешние DNS-сервера, на которые были отправлены рекурсивные запросы для преобразования адреса netology.ru.


### Ответ: 


