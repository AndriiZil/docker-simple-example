FROM php:7.3-fpm
MAINTAINER AZilnyk <andrii.zilnyk@gmail.com>

RUN docker-php-ext-install mbstring json

WORKDIR /app
CMD ["php-fpm"]
