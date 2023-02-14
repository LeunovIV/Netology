# Курсовая работа по итогам модуля "IT-системы и Linux"

Курсовая работа необходима для проверки практических навыков, полученных в ходе прохождения курса IT-системы и Linux.

Мы создадим и настроим виртуальное рабочее место. Позже вы сможете использовать эту систему для выполнения домашних заданий по курсу.

## Задание

Создайте виртуальную машину Linux.
Установите службу FTP (например, vsftpd).
Установите службу HTTP (например, nginx).
Добавьте в систему два накопителя.
Настройте RAID (зеркало) на этих накопителях.
Проверьте правильность работы сервера. Должны быть доступны:
SSH;
FTP;
HTTP.
Результат
Результатом курсовой работы должны быть снимки экрана:

работающих служб SSH, FTP, HTTP;
конфигурации RAID.


### Решение:



![image](https://user-images.githubusercontent.com/121933872/218639712-9f041477-3201-4df0-a592-d1aa9bb98467.png)


yum install nginx

systemctl enable nginx

systemctl start nginx

![image](https://user-images.githubusercontent.com/121933872/218640235-c0bec98a-81fb-403f-aef6-700f1a1eccf1.png)


yum install vsftpd

systemctl enable vsftpd

systemctl start vsftpd

![image](https://user-images.githubusercontent.com/121933872/218640343-f7357f5e-9032-43fd-a2b9-1173c8d83b3a.png)

Добавил 2 диска по 20ГБ, чтобы создать RAID 1

sudo yum install mdadm

