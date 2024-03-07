FROM php:8.2-apache
ENV COMPOSER_ALLOW_SUPERUSER 1

ADD 000-default.conf /etc/apache2/sites-available/000-default.conf

RUN apt-get update && apt-get install -y \
    libzip-dev \
    zip \
    unzip \
    && docker-php-ext-install zip pdo_mysql
