FROM php:8.2-fpm

# Встановлення необхідних пакетів
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libpq-dev \
    libzip-dev \
    && docker-php-ext-install zip pdo_mysql

# Встановлення xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug

# Встановлення Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
