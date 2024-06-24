FROM richarvey/nginx-php-fpm:3.1.6

# Image config
# ENV SKIP_COMPOSER 1
# ENV WEBROOT /var/www/html/movie8
# ENV PHP_ERRORS_STDERR 1
# ENV RUN_SCRIPTS 1
# ENV REAL_IP_HEADER 1

WORKDIR /var/www/html/movie8/

COPY cakephp /var/www/html/movie8
COPY deploy/nginx.conf /etc/nginx/sites-available/default.conf
# COPY deploy/nginx.conf /etc/nginx/nginx.conf

# COPY deploy/php-ini-overrides.ini /etc/php/8.2/fpm/conf.d/99-overrides.ini