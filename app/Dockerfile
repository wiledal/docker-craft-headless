FROM php:7-apache

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
  php composer-setup.php --install-dir=/usr/bin --filename=composer

RUN apt-get update && \
  apt-get install git zip zlib1g-dev libjpeg-dev libpng-dev libicu-dev -y;

RUN docker-php-ext-install pdo pdo_mysql zip gd mysqli opcache intl;

RUN a2enmod rewrite expires;

# Make better memory limit
RUN { \
		echo 'memory_limit = 1024M'; \
	} > /usr/local/etc/php/conf.d/craft-optimized.ini
