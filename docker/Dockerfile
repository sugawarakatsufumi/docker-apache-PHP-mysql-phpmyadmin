ARG PHP_IMAGE=default
FROM $PHP_IMAGE
RUN apt-get update && docker-php-ext-install mysqli pdo_mysql && a2enmod rewrite && docker-php-ext-install mysqli