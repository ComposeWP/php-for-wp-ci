FROM php:8.4-fpm-alpine3.21

# Install runtime dependencies
RUN apk add --no-cache \
    git curl mariadb-client \
    ghostscript \
    libzip icu zlib oniguruma libxml2 openssl \
    libheif libavif \
    imagemagick imagemagick-libs

# Build & install missing PHP extensions + PECL extensions
RUN apk add --no-cache --virtual .build-deps \
    autoconf g++ make \
    libzip-dev icu-dev libxml2-dev oniguruma-dev zlib-dev imagemagick-dev libheif-dev libavif-dev \
    && pecl install imagick igbinary timezonedb \
    && docker-php-ext-enable imagick igbinary timezonedb \
    && docker-php-ext-install \
    mysqli pdo pdo_mysql zip exif intl bcmath shmop \
    && apk del .build-deps