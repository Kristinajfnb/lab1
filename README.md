# Отчет по лабораторной работе №1

## 1. Инструкции по запуску проекта

Для запуска проекта потребуется браузер с доступом к инструментам разработчика и возможность использования инструмента `curl` или Postman для отправки HTTP-запросов.

## 2. Описание индивидуальной работы

В ходе работы был выполнен анализ HTTP-запросов и ответов с использованием инструментов разработчика. Были отправлены несколько запросов на сервер для проверки различных ситуаций (успешная и неуспешная аутентификация).

## 3. Краткая документация к проекту

Проект основан на анализе запросов HTTP, отправляемых на сервер для различных операций (аутентификация, создание и обновление данных). В проекте использованы методы:

GET: для получения данных с сервера.
POST: для отправки данных на сервер (например, логин и пароль).
PUT: для обновления существующих данных на сервере.
Каждый запрос включает в себя заголовки и тело запроса, которые можно анализировать с помощью инструментов разработчика или специализированных программ.

## 4. Примеры использования проекта с приложением скриншотов или фрагментов кода
1. Зайдите на сайт http://sandbox.usm.md/login.
2. Откройте вкладку Network в инструментах разработчика браузера.
3. Введите неверные данные для входа (например, username: student, password: studentpass).![1](https://github.com/Kristinajfnb/lab1/blob/main/1.png)
4. Повторите шаги, введя верные данные для входа (username: admin, password: password).![2](https://github.com/Kristinajfnb/lab1/blob/main/2.png)
5. Составьте GET-запрос к серверу по адресу http://sandbox.com, указав в заголовке User-Agent ваше имя и фамилию. curl -X GET http://sandbox.com -H "User-Agent: Тихонюк Кристина" ![3](https://github.com/Kristinajfnb/lab1/blob/main/3.png)
6. Составьте POST-запрос к серверу по адресу http://sandbox.com/cars, указав в теле запроса следующие параметры:
make: Toyota
model: Corolla
year: 2020

curl -X POST http://sandbox.com/cars -H "Content-Type: application/x-www-form-urlencoded" -d "make=Toyota&model=Corolla&year=2020"

7. Составьте PUT-запрос к серверу по адресу http://sandbox.com/cars/1, указав в заголовке User-Agent ваше имя и фамилию, в заголовке Content-Type значение application/json и в теле запроса следующие параметры: json { "make": "Toyota", "model": "Corolla", "year": 2021 }

curl -X PUT http://sandbox.com/cars/1 -H "User-Agent: Тихонюк Кристина" -H "Content-Type: application/json" -d '{"make": "Toyota", "model": "Corolla", "year": 2021}'

8. Напишите один из возможных вариантов ответа сервера следующий запрос. http POST /cars HTTP/1.1 Host: sandbox.com Content-Type: application/json User-Agent: John Doe model=Corolla&make=Toyota&year=2020 Предположите ситуации, когда сервер может вернуть HTTP-коды состояния 200, 201, 400, 401, 403, 404, 500.
   
HTTP 200 OK
Ситуация: Сервер успешно обработал запрос и вернул подтверждение об успешной обработке данных.
HTTP 201 Created
Ситуация: Запрос был успешно обработан, и новый ресурс был создан на сервере.
 HTTP 400 Bad Request
Ситуация: Запрос содержит неверный формат данных или неполные/ошибочные параметры.
HTTP 401 Unauthorized
Ситуация: Запрос требует аутентификации, а авторизация не была предоставлена или была неверной.
HTTP 403 Forbidden
Ситуация: Запрос был признан корректным, но пользователь не имеет прав для выполнения этого действия.
HTTP 404 Not Found
Ситуация: Запрашиваемый ресурс не был найден на сервере.
HTTP 500 Internal Server Error
Ситуация: Произошла ошибка на стороне сервера при обработке запроса.

9. Отправьте POST-запрос на сервер по адресу http://sandbox.usm.md/quest, указав в заголовке User-Agent вашу фамилию и имя. 
10. Следуйте инструкциям на сервере, выполняя их по порядку.![4](https://github.com/Kristinajfnb/lab1/blob/main/4.png)![5](https://github.com/Kristinajfnb/lab1/blob/main/5.png)![6](https://github.com/Kristinajfnb/lab1/blob/main/6.png)![7](https://github.com/Kristinajfnb/lab1/blob/main/7.png)
## 5. Ответы на контрольные вопросы
### Неверные данные
Какой метод HTTP был использован для отправки запроса?

Метод POST был использован для отправки запроса. Это стандартный метод для передачи данных (логина и пароля) на сервер.
Какие заголовки были отправлены в запросе? В запросе были отправлены следующие заголовки:

accept: */*
accept-encoding: gzip, deflate
accept-language: ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7
content-length: 37
content-type: application/x-www-form-urlencoded; charset=UTF-8
host: sandbox.usm.md
origin: http://sandbox.usm.md
referer: http://sandbox.usm.md/login/
user-agent: Mozilla/5.0...
x-requested-with: XMLHttpRequest
Какие параметры были отправлены в запросе?

Были отправлены следующие данные:
username: student
password: studentpass
Какой код состояния был возвращен сервером?

Сервер вернул код состояния 401 Unauthorized, что означает, что данные для входа неверны, и доступ к системе запрещён.
Какие заголовки были отправлены в ответе? В ответе сервер отправил следующие заголовки:

connection: keep-alive
content-type: text/plain;charset=UTF-8
date: Wed, 18 Sep 2024 18:07:56 GMT
server: nginx/1.24.0 (Ubuntu)
transfer-encoding: chunked

### Верные данные
Какой метод HTTP был использован для отправки запроса?

Метод POST был использован для отправки данных (логина и пароля) на сервер.
Какие заголовки были отправлены в запросе? В запросе были отправлены следующие заголовки:

accept: */*
accept-encoding: gzip, deflate
accept-language: ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7
content-length: 32
content-type: application/x-www-form-urlencoded; charset=UTF-8
host: sandbox.usm.md
origin: http://sandbox.usm.md
referer: http://sandbox.usm.md/login/
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
x-requested-with: XMLHttpRequest
Какие параметры были отправлены в запросе? Параметры запроса (введённые данные):

username: admin
password: password
Какой код состояния был возвращён сервером?

Сервер вернул код состояния 200 OK, что означает успешную обработку запроса и успешный вход в систему.
Какие заголовки были отправлены в ответе? В ответе сервер отправил следующие заголовки:

connection: keep-alive
content-type: text/plain;charset=UTF-8
date: Wed, 18 Sep 2024 18:33:12 GMT
server: nginx/1.24.0 (Ubuntu)
transfer-encoding: chunked

## Использованные источники

1. [Документация GitHub][github-docs]
2. [Руководство по Markdown][markdown-guide]
