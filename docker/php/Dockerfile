FROM php:8.1-fpm-alpine

WORKDIR /var/www

COPY . .

RUN docker-php-ext-install pdo pdo_mysql

RUN addgroup -g 1000 symfony && adduser -G symfony -g symfony -s /bin/sh -D symfony

USER symfony

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
