FROM php:7.3-fpm

LABEL xuweidong="determined_xw@126.com"

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd xdebug redis mcrypt memcached swoole zip
RUN chmod uga+x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions imagick
RUN docker-php-ext-configure opcache --enable-opcache && docker-php-ext-install opcache

RUN docker-php-ext-install -j$(nproc) bcmath calendar exif gettext sockets dba pcntl shmop sysvmsg sysvsem sysvshm
RUN docker-php-ext-install -j$(nproc) mysqli pdo pdo_mysql

# 安装composer
WORKDIR /tmp
RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer
RUN composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/


# 容器启动时执行指令
CMD ["php-fpm"]
