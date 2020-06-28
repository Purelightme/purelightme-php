FROM php:7.2-fpm

ADD install-php-extensions /usr/local/bin/

#RUN chmod uga+x /usr/local/bin/install-php-extensions && sync \
#    && install-php-extensions pdo_mysql

RUN docker-php-ext-install pdo_mysql
