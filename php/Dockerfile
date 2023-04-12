# Use the official PHP 8.2 image as the base image
FROM php:8.2-fpm



# Install necessary extensions
RUN apt-get update && \
    apt-get install -y \
        libzip-dev \
        libpq-dev \
        libonig-dev \
        libpng-dev \
        libjpeg-dev \
        libfreetype6-dev \
        && \
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) \
        zip \
        pdo \
        pdo_pgsql \
        mbstring \
        exif \
        pcntl \
        bcmath \
        gd \
        && \
    pecl install redis && \
    docker-php-ext-enable redis

# Install useful tools
#RUN apt-get -y install apt-utils nano wget dialog vim

# Install important libraries
#RUN echo "\e[1;33mInstall important libraries\e[0m"
#RUN apt-get -y install --fix-missing \
#    apt-utils \
#    build-essential \
#    git \
#    curl \
#    libcurl4 \
#    libcurl4-openssl-dev \
#    zlib1g-dev \
#    libzip-dev \
#    zip \
#    libbz2-dev \
#    locales \
#    libmcrypt-dev \
#    libicu-dev \
#    libonig-dev \
#    libxml2-dev
    
#RUN echo "\e[1;33mInstall important docker dependencies\e[0m"
#RUN docker-php-ext-install \
#    exif \
#    bcmath \
#    ctype \
#    curl \
#    iconv \
#    xml \
#    soap \
#    pcntl \
#    mbstring \
#    tokenizer \
#    bz2 \
#    zip \
#    intl

# Install Postgre PDO
#RUN apt-get install -y libpq-dev \
#    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
#    && docker-php-ext-install pdo pdo_pgsql pgsql
