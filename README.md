# Laravel Bootstrap

Quickly Bootstrap Laravel Project - using docker, nginx, mysql

## Getting Started

* clone the project

``` shell
export PROJECT_NAME=laravel-project
git clone https://github.com/alamin-mahamud/laravel-arena.git $PROJECT_NAME
cd $PROJECT_NAME
```

* create an env

```shell
cp .env.example .env
```

* docker-compose up (stop nginx, mysql if they are running locally or use different port)

```shell
docker-compose up
```

* go inside the container and run this commands

```shell
docker exec -it CORE_PHP bash
cd /var/www
composer install
chown -R $USER:$USER /var/www
php artisan key:generate
```
