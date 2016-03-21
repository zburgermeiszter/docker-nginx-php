FROM php:7.0-fpm

RUN apt-get update && \
    apt-get install -y git && \
    docker-php-ext-install -j$(nproc) bcmath mbstring sockets

ADD https://raw.githubusercontent.com/php/php-src/master/php.ini-production /usr/local/etc/php/php.ini

WORKDIR /var/www/html

RUN usermod -u 1000 www-data

CMD ["php-fpm", "-F"]

EXPOSE 9000