# FROM phpdockerio/php:8.2-fpm

# WORKDIR "/var/www/movie8"

# # install composer
# RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# # Install selected extensions and other stuff
# RUN apt-get update \
#     && apt-get -y --no-install-recommends install \
#     php8.2-intl \
#     php8.2-mysql \
#     php8.2-sqlite3 \
#     && apt-get clean \
#     && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# # copy project
# COPY cakephp /var/www/movie8

# # 将自定义的 PHP 配置文件复制到镜像中
# COPY docker/php-fpm/php-ini-overrides.ini /etc/php/8.2/fpm/conf.d/99-overrides.ini

# # 使用 nginx:alpine 作为基础镜像的部分
# RUN apt-get update \
#     && apt-get -y --no-install-recommends install nginx \
#     && apt-get clean \
#     && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# # 将自定义的 Nginx 配置文件复制到镜像中
# # COPY docker/nginx2/nginx.conf /etc/nginx/conf.d/default.conf
# # COPY docker/nginx2/nginx.conf /etc/nginx/site-available/default
# COPY docker/nginx2/nginx.conf /etc/nginx/nginx.conf



FROM richarvey/nginx-php-fpm:3.1.6

# Image config
ENV SKIP_COMPOSER 1
ENV WEBROOT /var/www/html/movie8/webroot
ENV PHP_ERRORS_STDERR 1
ENV RUN_SCRIPTS 1
ENV REAL_IP_HEADER 1

WORKDIR /var/www/html/movie8

COPY cakephp /var/www/html/movie8
COPY deploy/nginx.conf /etc/nginx/conf.d/default.conf
