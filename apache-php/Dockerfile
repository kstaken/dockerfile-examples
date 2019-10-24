# A basic apache server with PHP. To use either add or bind mount content under /var/www

FROM kstaken/apache2

MAINTAINER Kimbro Staken version: 0.1

#Code from VinothKumar for PHp extentions installation 7 Configure

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
    
    CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]
