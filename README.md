# Laravel Bootstrap

Quickly Bootstrap Laravel Project - using docker, nginx, mysql

## Table of contents

- [Getting Started](#getting-started)
- [Quick Lookup](#quick-lookup)
  - [Routing](#routing)

## Getting Started

* clone the project

``` shell
export PROJECT_NAME=laravel-project
git clone https://github.com/alamin-mahamud/laravel-arena.git $PROJECT_NAME
cd $PROJECT_NAME
```

* create an `.env` file

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

## Quick Lookup

### Routing

```php
Route::get('foo', function() {
        return 'Hello World';
});
```

```php
Route::get('/user', 'UserController@index')
```

Multiple `HTTP verbs`.

```php
Route::match(['get', 'post'], '/', function() {
        //
});
```

- CSRF Protection

```php
<form method="POST" action="/profile">
        @csrf
</form>
```

- Redirect Routes; returns a `302`

```php
Route::redirect('/here', '/there');
```

- Redirect Routes; returns custom status code

```php
Route::redirect('/here', '/there', 301);
```

- View Routes

```php
Route::view('/welcome', 'welcome');
Route::view('<path>', '<view-name>', [
        '<variable-name>' => '<variable-value>',
]);
```