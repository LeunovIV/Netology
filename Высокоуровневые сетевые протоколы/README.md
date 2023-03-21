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

7

## Задание 3.

Создайте свой корневой сертификат, добавьте его в систему.

Затем подпишите им свой сертификат.

1. Генерируем ключ

```
openssl genrsa -out ca.key 2048
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226341743-694cb164-83fb-4fc0-9f8c-ecb69d482216.png)


2. Генерируем корневой сертификат. Поля в сертификате указываем любые.

```
openssl req -x509 -new -nodes -key ca.key -sha256 -days 720 -out ca.pem
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226342451-3474c41c-ad02-4dee-ab4e-2706ce733ef8.png)


3. Сразу же сделаем сертификат в форме crt

```
openssl x509 -in ca.pem -inform PEM -out ca.crt
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226342609-60540885-b5d6-4b27-b903-fedcb32f07b1.png)

4. Далее установим сертификат в систему. Ниже пример для Ubuntu/Debian систем

```
sudo cp ca.crt /usr/local/share/ca-certificates/myca.crt && sudo update-ca-certificates
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226347169-5f75ac0d-e6d8-4123-8777-42e0fda4759d.png)

5. Приступим к выпуску самого сертификата:

5.1. Генерируем ключи

```
openssl genrsa -out certificate.key 2048
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226347447-c0ce83f2-c541-4da8-aefc-47b82eed1ecc.png)

5.2. На основе ключа создаем CSR

Обратите внимание, что subject конечного сертификата не должен совпадать с subject корневого. Хотя бы в одном поле нужно указать отличающееся значение, например в common Name или email. В противном случае конечный сертификат не будет верифицироваться, поскольку будет считаться самоподписным.

```
openssl req -new -key certificate.key -out certificate.csr
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226348048-a138bcf1-ec76-4ed4-8867-d851420f29fa.png)

5.3. Подписываем CSR нашим корневым сертификатом. Тем самым создаем конечный сертификат.

```
openssl x509 -req -in certificate.csr -CA ca.pem -CAkey ca.key -CAcreateserial -out certificate.crt -days 360 -sha256
```
Ответ:

![image](https://user-images.githubusercontent.com/121933872/226348299-a238ffb0-9374-4555-bf32-aa1c9038e52c.png)

6. Проверяем валидность сертификата

Эта проверка должна вернуть OK. Если вы видите failed, значит, где-то допущена ошибка.

```
openssl verify certificate.crt
```

В качестве ответа приложите снимки экрана с выводом информации о сертификатах и результатом верификации:

```
1 openssl x509 -subject -issuer -noout -in ca.pem
2 openssl x509 -subject -issuer -noout -in certificate.crt
3 openssl verify certificate.crt
```


#### Ответ: 

![image](https://user-images.githubusercontent.com/121933872/226521240-eaeffea8-c494-4d8c-8f66-634fc513b5e8.png)





