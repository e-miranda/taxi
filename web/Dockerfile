FROM php:8.2-apache

WORKDIR /app

RUN apt-get update && apt-get install -y \
    git curl zip unzip libpng-dev libonig-dev libxml2-dev libzip-dev

RUN docker-php-ext-install pdo pdo_mysql mbstring exif pcntl gd zip

RUN a2enmod rewrite

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY composer.json ./

RUN composer install --no-interaction

COPY . .

COPY vhost.conf /etc/apache2/sites-available/000-default.conf

RUN chown -R www-data:www-data /app

EXPOSE 80

CMD ["apache2-foreground"]
