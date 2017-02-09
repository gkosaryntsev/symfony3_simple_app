# Тестовое окружение для разработки на Windows

#### Устанавливаем Docker Toolbox 
https://www.docker.com/products/docker-toolbox


## Запуск на Windows:
Папка с файлом docker-compose.yml должна находиться внутри директории пользователя (Например, C:\Users\vasya\dockerexample), потому что иначе volumes в docker не будут работать.
* Открыть консоль докер
* Создаем директорию:
```
mkdir ~/dockerexample
```
* Перейти в директорию
`cd /c/Users/vasya/dockerexample`
или `cd ~/dockerexample`

* Склонировать файлы

`git clone https://github.com/gkosaryntsev/docker_php_base.git`

* Запустить

```
cd docker
docker-compose up -d
```

#### Как открыть в браузере
С помощью команды
`docker-machine ip`
получить IP
и к этому IP подставить порт 9000, например:

http://192.168.99.100:9000/

#### Загрузка проектов
Заходим в контейнер с php:
 
`docker exec -it ex7-php-fpm /bin/bash`

Внутри контейнера перейти в директорию с проектом

`cd /var/www/ex7/web`

Если у нас уже есть какой-то проект, мы можем загрузить недостающие пакеты:
`composer install`

#### Инсталляция symfony:
`composer create-project symfony/framework-standard-edition my_project_name`

Во время установки попросит ввести параметры соединения к БД:
```
Some parameters are missing. Please provide them.
database_host (127.0.0.1): ex7-postgres
database_port (null): 5432
database_name (symfony): dbname
database_user (root): root
database_password (null): root
mailer_transport (smtp):
mailer_host (127.0.0.1):
mailer_user (null):
mailer_password (null):
secret (ThisTokenIsNotSoSecretChangeIt): lkjsdfklsdjal;sdfdl^[[D^H^H
```
