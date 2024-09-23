# **Домашнее задание к занятию «Работа с данными (DDL/DML)» SYS-32 - Кумышев Аслан**

# * Задание 1 *
Задание можно выполнить как в любом IDE, так и в командной строке.

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

 ![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/Скриншот%2022-09-2024%20020632.jpg)

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

 ![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/1.3.jpg)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/1%2C5.jpg)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.
 
 ![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/1%2C17.jpg)

 ![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/1%2C7.jpg)

`sudo -i`

`#mysql -u root -p`

`mysql> CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'sys_temp';`

`mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;`

`mysql> GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';`

`mysql> show grants for 'sys_temp'@'localhost';`

`mysql> exit`

`#mysql -u sys_temp -psys_temp -hlocalhost`

`mysql> SELECT user();`

`mysql> exit`

`#wget https://downloads.mysql.com/docs/sakila-db.zip`

`#apt install unzip`

`#unzip sakila-db.zip`

`#mysql -u sys_test -p`

`mysql> CREATE DATABASE `sakila`;`

`mysql> SHOW DATABASES;`

`mysql> exit`

`#export DBNAME=sakila`

`#mysql -u sys_temp -psys_temp -hlocalhost ${DBNAME} < /root/sakila-db/sakila-schema.sql`

`#mysql -u sys_temp -psys_temp -hlocalhost ${DBNAME} < /root/sakila-db/sakila-data.sql`

`#mysql -u sys_temp -psys_temp -hlocalhost`

`mysql> SHOW DATABASES;`

`mysql> USE sakila;`

`mysql> SHOW TABLES;`

- ![#c5f015](Единственное я не понял почему мне не удалось зайти без пароля, пробовал различные вариации. Несколько раз удалял и создавал по новой учетку, пробовал прописать в  nano /home/root/.my.cnf без толку. Буду благодарен услышать Вашу версию причины? Спасибо) `#c5f015`
 **************************************************************************

# * Задание 2 *

Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

Название таблицы | Название первичного ключа

customer         | customer_id


1. ![alt text](https://github.com/sAslank/-DDL-DML/blob/main/img/Скриншот%2023-09-2024%20030739.jpg)

# * Задание 3* *

Дополнительные задания (со звёздочкой*)

Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

3.1. Уберите у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila.

3.2. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.
