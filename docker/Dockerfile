FROM php:7.3-fpm
MAINTAINER Krac <dawid.kraczkowski@gmail.com>

RUN apt-get update

# Base php setup
RUN apt-get install -y autoconf pkg-config libzip-dev libssl-dev zlib1g-dev libpq-dev git libicu-dev libxml2-dev && \
    docker-php-ext-install pdo_mysql pdo_pgsql pgsql bcmath zip

# Swoole install
RUN pecl install swoole && \
    docker-php-ext-enable swoole && \
    pecl install xdebug && \
    docker-php-ext-enable xdebug

COPY xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

# Composer
RUN curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && \
    chmod +x /usr/bin/composer
