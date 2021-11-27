# Image
FROM nginx:alpine

ENV HOST 0.0.0.0

WORKDIR /var/www

# Add config
COPY default.conf /etc/nginx/conf.d/default.conf


RUN apk add --no-cache git
RUN apk add --no-cache openssh
RUN apk add --no-cache php8 
RUN apk add --no-cache php8-curl 
RUN apk add --no-cache php8-zip
RUN apk add --no-cache bash
RUN apk add --no-cache curl

# INSTALL COMPOSER
RUN curl -s https://getcomposer.org/installer | php
RUN alias composer='php composer.phar'


RUN apk add --no-cache mysql-client
WORKDIR /data
RUN git clone https://github.com/familytree365/genealogy.git --depth 1 /data/app
WORKDIR /data/app

RUN composer install

# RUN mysqladmin create landlord --host="127.0.0.1" --user="root" --password="password" \
RUN php artisan key:generate
# RUN php artisan migrate --seed --force


EXPOSE 8000
