FROM php:7-apache

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
  php composer-setup.php --install-dir=/usr/bin --filename=composer

# PHP CORE LIBRARIES
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

    RUN apt-get update && \
      apt-get install git zip zlib1g-dev libicu-dev -y;

RUN docker-php-ext-install pdo pdo_mysql zip mysqli opcache intl;

RUN a2enmod rewrite expires headers;

# Make better memory limit
RUN { \
		echo 'memory_limit = 1024M\nmax_input_vars = 8192\npost_max_size = 256M\nupload_max_filesize = 256M'; \
	} > /usr/local/etc/php/conf.d/craft-optimized.ini
