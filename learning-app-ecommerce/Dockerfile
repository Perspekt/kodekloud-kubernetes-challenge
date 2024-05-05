FROM php:7.4-apache

# Install mysqli extension

RUN apt-get update -y 

#Per https://github.com/docker-library/php/issues/391
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli

# Copy application source code
COPY . /var/www/html/

# Update database connection strings (using environment variable)
RUN sed -i "s/172.20.1.101/mysql-service'/g" /var/www/html/*.php

# Expose web server port (default Apache port)
EXPOSE 80
