FROM php:8.3-fpm-alpine

# Paquetes y extensiones necesarias
RUN apk add --no-cache git unzip libzip-dev \
 && docker-php-ext-configure zip \
 && docker-php-ext-install pdo pdo_mysql bcmath zip

# Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
CMD ["php-fpm", "-F"]

