FROM php:8.2-apache

RUN apt-get update && apt-get install -y \
    libpng-dev libjpeg-dev libfreetype6-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd

RUN sed -i 's/Listen 80/Listen 8081/' /etc/apache2/ports.conf
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf

COPY site/ /var/www/html/

EXPOSE 8081
