FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libicu-dev \ 
    zip \
    unzip
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install -j$(nproc) gd intl opcache
RUN pecl install xdebug-3.1.2 \
    && docker-php-ext-enable xdebug intl opcache

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

WORKDIR /var/www/app
CMD ["php-fpm"]
EXPOSE 9003