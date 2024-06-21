FROM phpdockerio/php:8.2-fpm

WORKDIR "/var/www/movie8"

# install composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install \
    php8.2-intl \
    php8.2-mysql \
    php8.2-sqlite3 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# copy project
COPY cakephp /var/www/movie8

# 将自定义的 PHP 配置文件复制到镜像中
COPY docker/php-fpm/php-ini-overrides.ini /etc/php/8.2/fpm/conf.d/99-overrides.ini