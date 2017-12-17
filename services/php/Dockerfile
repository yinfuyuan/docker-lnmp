FROM php:7.2.0-fpm-alpine3.7

MAINTAINER yinfuyuan <yinfuyuan@gmail.com>

WORKDIR /http

RUN docker-php-ext-install pdo_mysql

COPY ./composer.phar /usr/local/bin/composer

RUN chmod +x /usr/local/bin/composer

RUN composer config -g repo.packagist composer https://packagist.phpcomposer.com