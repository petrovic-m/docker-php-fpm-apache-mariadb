FROM php:5.6-fpm

ARG WEB_USER
ARG WEB_GROUP
ARG PHP_ROOT_DIR

COPY Configuration/www.conf ${PHP_ROOT_DIR}/php-fpm.d/www.conf
COPY Configuration/php.ini-development ${PHP_ROOT_DIR}/php/php.ini.development
COPY Configuration/php.ini-production ${PHP_ROOT_DIR}/php/php.ini.production

RUN usermod -u 1000 ${WEB_USER} \
 && groupmod -g 1000 ${WEB_GROUP} \
 && chgrp -R staff ${PHP_ROOT_DIR}/php-fpm.d/www.conf