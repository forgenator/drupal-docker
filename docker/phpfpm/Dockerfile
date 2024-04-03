FROM php:8.2-fpm

# Install required debian packages
RUN apt-get update && apt-get install -y \
		git vim wget curl unzip gnupg \
		libfreetype6-dev \
		libjpeg62-turbo-dev \
		libjpeg-dev \
		libpng-dev \
        libonig-dev \
		libcurl4-gnutls-dev \
		libc-client-dev libkrb5-dev \
		libldap2-dev \
		libzip-dev \
		libxml2-dev \
		libbz2-dev \
		zlib1g-dev libicu-dev g++

# Install and configure drupal's required php extensions
RUN docker-php-ext-configure gd
RUN docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install -j$(nproc) dom    
RUN docker-php-ext-install -j$(nproc) session
RUN docker-php-ext-install -j$(nproc) simplexml    
RUN docker-php-ext-install -j$(nproc) xml
RUN docker-php-ext-install -j$(nproc) mbstring
RUN docker-php-ext-install -j$(nproc) opcache
RUN docker-php-ext-install -j$(nproc) bz2
RUN docker-php-ext-install -j$(nproc) exif    
RUN docker-php-ext-install -j$(nproc) zip

# Install if you need mysql
#RUN docker-php-ext-install -j$(nproc) mysqli
#RUN docker-php-ext-install -j$(nproc) pdo
#RUN docker-php-ext-install -j$(nproc) pdo_mysql

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY php.ini /usr/local/etc/php
