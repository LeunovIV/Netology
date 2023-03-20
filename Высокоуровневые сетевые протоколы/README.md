# Домашнее задание к занятию "Высокоуровневые сетевые протоколы"

## Задание 1.

Какие порты используются протоколами:

1) Telnet;
2) SSH;
3) FTP;
4) SNMP.
Приведите ответ в виде списка портов.

#### Ответ: 

1) Telnet - 23TCP;
2) SSH - 22 TCP;
3) FTP - 20 и 21 TCP;
4) SNMP - 161 b 162 UDP.



## Задание 2.

Какой по счету уровень модели OSI называется прикладным (application layer)?

Зашифруйте ответ с помощью ключа: {5, 21}.

#### Ответ: 





## Задание 3.

Создайте свой корневой сертификат, добавьте его в систему.

Затем подпишите им свой сертификат.

1. Генерируем ключ

```
1 - openssl genrsa -out ca.key 2048
```

2. Генерируем корневой сертификат. Поля в сертификате указываем любые.

```
1 - openssl req -x509 -new -nodes -key ca.key -sha256 -days 720 -out ca.pem
```

3. Сразу же сделаем сертификат в форме crt

```
1 - openssl x509 -in ca.pem -inform PEM -out ca.crt
```

4. Далее установим сертификат в систему. Ниже пример для Ubuntu/Debian систем

```
1 - sudo cp ca.crt /usr/local/share/ca-certificates/myca.crt && sudo update-ca-certificates
```

5. Приступим к выпуску самого сертификата:

5.1. Генерируем ключи

```
1 - openssl genrsa -out certificate.key 2048
```

5.2. На основе ключа создаем CSR

Обратите внимание, что subject конечного сертификата не должен совпадать с subject корневого. Хотя бы в одном поле нужно указать отличающееся значение, например в common Name или email. В противном случае конечный сертификат не будет верифицироваться, поскольку будет считаться самоподписным.

```
1 - openssl req -new -key certificate.key -out certificate.csr
```

5.3. Подписываем CSR нашим корневым сертификатом. Тем самым создаем конечный сертификат.

```
1 - openssl x509 -req -in certificate.csr -CA ca.pem -CAkey ca.key -CAcreateserial -out certificate.crt -days 360 -sha256
```

6. Проверяем валидность сертификата

Эта проверка должна вернуть OK. Если вы видите failed, значит, где-то допущена ошибка.

```
1 - openssl verify certificate.crt
```

В качестве ответа приложите снимки экрана с выводом информации о сертификатах и результатом верификации:

```
1 openssl x509 -subject -issuer -noout -in ca.pem
2 openssl x509 -subject -issuer -noout -in certificate.crt
3 openssl verify certificate.crt
```


#### Ответ: 






