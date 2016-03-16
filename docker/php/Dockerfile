FROM php:5.6-fpm

RUN apt-get update \
  && apt-get install -y unzip vim telnet \
  && rm -rf /var/lib/apt/lists/*

COPY ./config/php-fpm.conf /usr/local/etc/

WORKDIR "/var/www"