FROM php:7.0-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev \
    libpq-dev \
    postgresql-client \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    && docker-php-ext-install mcrypt pdo_pgsql \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && apt-get clean