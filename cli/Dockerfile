FROM php:7.2-cli

ADD install-php-extensions /usr/local/bin/

RUN chmod uga+x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions pdo pdo_mysql swoole

RUN apt-get update && apt-get install -y wget \
    && wget https://github.com/composer/composer/releases/download/1.8.6/composer.phar \
    && chmod u+x composer.phar \
    && mv composer.phar /usr/local/bin/composer \
    && composer config -g repo.packagist composer https://mirrors.aliyun.com/composer

RUN apt-get install -y git

RUN install-php-extensions redis

RUN apt-get update && apt-get install -y zip unzip

RUN install-php-extensions zip

ADD php.ini /usr/local/etc/php/

VOLUME /apps

WORKDIR /apps

CMD ["php","bin/hyperf.php","start"]
