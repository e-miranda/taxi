FROM php:8.2-fpm

WORKDIR /app

RUN apt-get update && apt-get install -y \
    git curl zip unzip libpng-dev libonig-dev libxml2-dev libzip-dev

RUN docker-php-ext-install pdo pdo_mysql mbstring exif pcntl gd zip

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY composer.json ./

RUN composer install --no-interaction

COPY . .

EXPOSE 8000

CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]
