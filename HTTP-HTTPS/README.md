# Домашнее задание к занятию "HTTP/HTTPS"

## Задание 1.

Какие коды ответов HTTP лучше соответствуют описанным ситуациям?

1) Данная страница не найдена;

2) Страница была перенесена на новый сайт;

3) Ресурс удален;

4) Пользователь не авторизован для просмотра страницы;

5) Превышен лимит запросов от пользователя.

Приведите ответ в свободной форме.


### Ответ: 

1) 404 - Not Found (не найдено);
2) 301 - Moved Permanently (Перемещено навсегда);
3) 410 - Gone (был, но сейчас недоступен);
4) 401 - Unauthorized (недоступен без авторизации);
5) 429 - Too Many Requests (слишком много запросов)



## Задание 2.

Установите Nginx.
sudo apt-get install nginx

Сгенерируйте сертификат для него указав localhost в качестве CN.
sudo openssl req -x509 -nodes -newkey rsa:4096 -keyout /etc/nginx/cert.key -out /etc/nginx/cert.pem -days 365
Отредактируйте модуль http в файле/etc/nginx/nginx.conf.

```
http {
    gzip on;
    server {
        listen 80 default_server;
        root   /var/www/public;
        listen  443 ssl http2 default_server;
        server_name  localhost;
        ssl_certificate  /etc/nginx/cert.crt;
        ssl_certificate_key /etc/nginx/cert.key;
        ssl_protocols   TLSv1 TLSv1.1 TLSv1.2;
        ssl_ciphers   HIGH:!aNULL:!MD5;
        location / {
            index index.html;
        }
    }
}
```

Создайте файл /var/www/public/index.html c содержимым.

<h>It works</h>

Зайдите на страницу в браузере, пропустив сообщение о неработающем сертификате.

Пришлите скриншот работающей страницы https://localhost.

### Ответ: 

![image](https://user-images.githubusercontent.com/121933872/224019430-0d7f897c-186b-4796-bf5c-e19386ae3082.png)



## Задание 3.

Измените конфигурацию сервера добавив переадресацию c Вашего сервера на сайт netology.ru.

```
location / {
  return 301 https://netology.ru;
}
```

Используя curl сделайте запрос к своему серверу и в качестве ответа пришлите скриншот с 301 ответом.

### Ответ: 

![image](https://user-images.githubusercontent.com/121933872/224021024-9c137274-43af-4843-9e0f-52b03de58db0.png)



# Дополнительные задания (со звездочкой)*

# Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

## Задание 4.

Используя документацию httpd.apache.org...s/current/ установите apache2 веб-сервер.

Сделайте задание 2, добившись аналогичной работы сервера.

Пришлите получившуюся конфигурацию в качестве ответа.


### Ответ: 



