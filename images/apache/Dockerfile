FROM php:8.2-apache

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

RUN apt-get update && apt-get install unzip wget libzip-dev libpng-dev libicu-dev libxml2-dev libxslt-dev libjpeg-dev libfreetype6-dev libfreetype-dev -y

RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install mysqli pdo pdo_mysql zip bcmath gd intl soap xsl sockets

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN a2enmod rewrite

WORKDIR /var/www/html/