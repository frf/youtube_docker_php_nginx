FROM php:7.3-fpm-alpine

WORKDIR /var/www/html

RUN apk add \
        --update \
        --no-cache \
        zlib-dev \
        libpng \
        libpng-dev \
        libjpeg-turbo \
        libjpeg-turbo-dev \
        freetype \
        freetype-dev \
        poppler-utils \
        icu \
        icu-dev \
        libxml2 \
        libxml2-dev \
        libzip-dev \

    && docker-php-ext-install \
        pdo_mysql \
        mysqli \
        zip \
        gd \
        intl \
        xmlrpc \
        soap \
    && docker-php-ext-enable \
        pdo_mysql \
        mysqli \
        zip \
        gd \
    && echo "catch_workers_output = yes" >> /usr/local/etc/php-fpm.d/www.conf \
    && echo "php_flag[display_errors] = on" >> /usr/local/etc/php-fpm.d/www.conf \
    && echo "php_admin_flag[log_errors] = on" >> /usr/local/etc/php-fpm.d/www.conf \
    && apk del \
        --no-cache \
        freetype-dev \
        libpng-dev \
        libjpeg-turbo-dev
