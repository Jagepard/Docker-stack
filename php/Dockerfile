FROM devilbox/php-fpm:8.2-prod

# FROM php:7.4-fpm
# RUN apt-get update && apt-get install -y \
#         curl \
#         wget \
#         git \
#         libfreetype6-dev \
#         libonig-dev \
#         libpq-dev \
#         libjpeg62-turbo-dev \
#         libmcrypt-dev \
#         libpng-dev \
#         libzip-dev \
#     && pecl install mcrypt-1.0.3 \
#     && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
#     && docker-php-ext-configure gd --with-freetype --with-jpeg \
#     && docker-php-ext-install -j$(nproc) gd \
#     && docker-php-ext-enable mcrypt

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini
WORKDIR /var/www
CMD ["php-fpm"]