FROM php:7.2.0-fpm-alpine3.7

MAINTAINER yinfuyuan <yinfuyuan@gmail.com>

RUN addgroup -S php && adduser -S -G php php

ENV PHP_VERSION=7.2.0 \
    COMPOSER_VERSION=1.6.4

ENV COMPOSER_DOWNLOAD_URL="https://getcomposer.org/download/${COMPOSER_VERSION}/composer.phar" \
    COMPOSER_SHA="8d0d9246f68532cc8fd6a47a58d195f0c849d26430f93c397a3176fc2d971ded" \
    COMPOSER_PACKAGIST="https://packagist.phpcomposer.com"

RUN set -x; \
    \
    apk add --no-cache \
        bash; \
    \
    wget -O composer.phar "${COMPOSER_DOWNLOAD_URL}"; \
    echo "${COMPOSER_SHA} *composer.phar" | sha256sum -c; \
    mv composer.phar /usr/local/bin/composer; \
    chmod +x /usr/local/bin/composer; \
    composer config -g repo.packagist composer ${COMPOSER_PACKAGIST}; \
    \
    docker-php-ext-install pdo_mysql openssl

COPY ./config /usr/local/etc

WORKDIR /http