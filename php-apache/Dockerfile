FROM php:7.4-apache

RUN apt-get update && \
    apt-get -y install libmcrypt4 libfreetype6 libjpeg62-turbo libpng16-16 libxpm4 libwebp6 libzip4 wget zip mariadb-client msmtp && \
    apt-get -y install libmcrypt-dev libreadline-dev libicu-dev libpng-dev libjpeg-dev libfreetype6-dev libxpm-dev libwebp-dev libzip-dev && \
    pecl install mcrypt-1.0.4 && \
    docker-php-ext-enable mcrypt && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install sockets && \
    docker-php-ext-install opcache && \
    docker-php-ext-install gd && \
    docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ --with-webp=/usr/include/ --with-xpm=/usr/include/ && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install zip && \
    apt-get remove -y libmcrypt-dev libreadline-dev libicu-dev libpng-dev libjpeg-dev libfreetype6-dev libxpm-dev libzip-dev libwebp-dev gcc gcc-8 && \
    apt-get autoremove -y && apt-get clean && rm -rf /usr/src/*