FROM php:7.4-fpm

ENV PHP_MEMORY_LIMIT 2G

RUN pecl install xdebug-3.0.1 && docker-php-ext-enable xdebug

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libicu-dev \
        libxslt1-dev \
        libzip-dev \
        zip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-configure zip

RUN docker-php-ext-install -j$(nproc) \
  bcmath \
  gd \
  intl \
  pdo_mysql \
  soap \
  xsl \
  zip \
  sockets
