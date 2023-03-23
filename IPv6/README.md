# Домашнее задание к занятию "IPv6"

## Задание 1.

Какая нотация используется для записи IPv6-адресов:

1) какие и сколько символов?
2) какие разделители?

Приведите ответ в свободной форме.

### Ответ:

1) размер адреса IPv6 составляет 128 бит, записывается в шестнадцатиричном формате, состоит из 8 групп по 4 символа

2) разделителями используются двоеточия

## Задание 2.

Какой адрес используется в IPv6 как loopback?

Приведите ответ в свободной форме.

### Ответ:

Адрес логического интерфейса loopback ::1/128 или ::1 протокола IPv6 аналогичен адресу 127.0.0.1 протокола IPv4. Он служит для самотестирования, когда проверяется, установлен ли стек протоколов TCP/IP.

Неопределенный адрес ::/128 или :: протокола IPv6 в некоторых случаях используется в качестве адреса источника в пакете, когда источнику еще не назначен постоянный индивидуальный адрес.


## Задание 3.

Что такое Unicast, Multicast, Anycast адреса?

Приведите ответ в свободной форме.

### Ответ:

Существует три типа IPv6-адресов:

Unicast (индивидуальный) - служит для определения интерфейса на устройстве под управлением протокола IPv6

Multicast (групповой) - используется для отправки пакетов по нескольким адресам назначения

Anycast (произвольный) - любой индивидуальный адрес, который может быть назначен нескольким устройствам. Пакет, отправляемый на адрес произвольной рассылки, направляется к ближайшему устройству с этим адресом




## Задание 4.

Используя любую консольную утилиту в Linux, получите IPv6-адрес для какого либо ресурса.

В качестве ответа приложите скриншот выполнения команды.

### Ответ:

![image](https://user-images.githubusercontent.com/121933872/227263285-67f6e182-97fd-43e3-89cc-f6b815c64e7a.png)




## Задание 5.

Как выглядят IPv6-адреса, которые маршрутизируются в интернете?
Как выглядят локальные IPv6 адреса?
Приведите ответ в свободной форме.

### Ответ:


Глобальный юникаст (Global unicast) – это аналог публичных адресов в IPv4. Большая часть всех адресов относятся именно к этому классу. Эти адреса должны быть уникальными в пределах всего интернета, они выдаются IANA региональным регистраторам, те выдают их провайдерам, а провайдеры – выдают клиентам.

IPv6 google.ru 2a00:1450:4010:c1c::5e

ink-local
Local IPv6-адрес канала позволяет устройству обмениваться данными с другими устройствами под управлением IPv6 по одному и тому же каналу и только по данному каналу (подсети). Пакеты с локальным адресом канала источника или назначения не могут быть направлены за пределы того канала, в котором пакет создаётся. В отличие от локальных IPv4-адресов канала, локальные адреса канала IPv6 играют важную роль в различных аспектах сети. Глобальный индивидуальный адрес не обязателен. Однако для содержания локального адреса канала необходим сетевой интерфейс под управлением протокола IPv6. Если локальный адрес канала не настроен вручную на интерфейсе, устройство автоматически создаёт собственный адрес, не обращаясь к DHCP-серверу. Узлы под управлением IPv6 создают локальный IPv6-адрес канала даже в том случае, если устройству не был назначен глобальный IPv6-адрес. Это позволяет устройствам под управлением IPv6 обмениваться данными с другими устройствами под управлением IPv6 в одной подсети, в том числе со шлюзом по умолчанию (маршрутизатором). Локальные IPv6-адреса канала находятся в диапазоне FE80::/10. /10

например fe80::a00:27ff:fea2:f840/64