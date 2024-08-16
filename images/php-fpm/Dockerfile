FROM php:8.2-fpm

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

RUN apt-get update && apt-get install unzip wget libzip-dev libpng-dev libicu-dev libxml2-dev libxslt-dev libjpeg-dev libfreetype6-dev libfreetype-dev -y

RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install mysqli pdo pdo_mysql zip bcmath gd intl soap xsl sockets
RUN docker-php-ext-install opcache

RUN curl -o /usr/local/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
    && chmod +x /usr/local/bin/wp

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini
WORKDIR /usr/share/nginx/html/