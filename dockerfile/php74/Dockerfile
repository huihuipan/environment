ARG PHP_VERSION
FROM php:7.4-fpm

ARG TZ=UTC
ENV TZ Asia/Shanghai

ARG PHP_COMPOSER_URL
ENV PHP_COMPOSER_URL https://mirrors.aliyun.com/composer/composer.phar

ARG PHP_COMPOSER_REPO
ENV PHP_COMPOSER_REPO https://mirrors.aliyun.com/composer/

# 更改为阿里源
RUN sed -i 's/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list \
    && sed -i 's/security.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list \
    && sed -i 's/security-cdn.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list

RUN apt-get update -y \
  && apt-get install -y apt-utils libfreetype6-dev libjpeg-dev libpng-dev libwebp-dev libxpm-dev libzip-dev unzip \
  # composer
  && curl $PHP_COMPOSER_URL -o /usr/local/bin/composer \
  && chmod a+x /usr/local/bin/composer \
  && composer config -g repo.packagist composer $PHP_COMPOSER_REPO \
  # php 扩展
  && pecl channel-update pecl.php.net \
  && pecl install -o -f mongodb redis \
  && rm -rf /tmp/pear \
  && docker-php-ext-enable mongodb redis \
  && docker-php-ext-configure gd --with-webp --with-jpeg --with-xpm --with-freetype \
  && docker-php-ext-install bcmath gd mysqli pcntl pdo_mysql zip \
  # 时区
  && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

WORKDIR /var/www

EXPOSE 9000