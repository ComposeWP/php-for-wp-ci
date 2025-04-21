FROM php:8.2.28-fpm-alpine3.21

RUN apk add --no-cache \
    git curl mariadb-client \
    libzip-dev \
    libjpeg-turbo-dev libpng-dev freetype-dev libwebp-dev \
    icu-dev libxml2-dev oniguruma-dev zlib-dev \
    && docker-php-ext-configure gd \
    --with-freetype \
    --with-jpeg \
    --with-webp \
    && docker-php-ext-install \
    gd mysqli pdo pdo_mysql zip exif intl