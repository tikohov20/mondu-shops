FROM php:8.2-fpm

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

RUN apt-get update && apt-get install unzip wget libzip-dev libpng-dev libicu-dev libxml2-dev libxslt-dev libjpeg-dev libfreetype6-dev libfreetype-dev -y

RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install mysqli pdo pdo_mysql zip bcmath gd intl soap xsl sockets

WORKDIR /usr/share/nginx/html/