FROM php:7.2-fpm-alpine
ENV ALPINE_SOURCE=/etc/apk/repositories
# ENV key=value

# RUN sed -i 's/^[^#]/#&/' $ALPINE_SOURCE \
#     echo -e 'http://mirrors.aliyun.com/alpine/v3.7/main\nhttp://mirrors.aliyun.com/alpine/v3.7/community' >> $ALPINE_SOURCE \
RUN echo -e 'http://mirrors.aliyun.com/alpine/v3.7/main\nhttp://mirrors.aliyun.com/alpine/v3.7/community' > $ALPINE_SOURCE \
    apk update \
    apk add --no-cache vim \
        gcc \
        g++ \
        make \
        autoconf \
        pcre \
        curl \
        openssl \
        # 
        # pecl install swoole \
        # docker-php-ext-enable swoole \
        cd /var/www/html \
        php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
        php composer-setup.php \
        mv composer.phar /usr/local/bin/composer 

# COPY . /usr/local/etc/php/
WORKDIR /var/www/html
EXPOSE 9000
CMD ["php-fpm"]