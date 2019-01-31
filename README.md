# Laravel Bootstrap

```
cp .env.example .env
docker-compose up
docker exec -it CORE_PHP bash
cd /var/www
composer install
chown -R $USER:$USER /var/www
php artisan key:generate
```