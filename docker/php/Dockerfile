FROM php:7.0-fpm

COPY ./php.ini /usr/local/etc/php/

RUN apt-get update \
    && apt-get install -y libmcrypt-dev vim postgresql-client libpq-dev libmagickwand-dev --no-install-recommends \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install -j$(nproc) pdo pdo_pgsql pgsql \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && apt-get clean