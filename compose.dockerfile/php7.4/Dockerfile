FROM php:7.4-fpm


ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions xdebug redis mcrypt memcached swoole
RUN chmod uga+x /usr/local/bin/install-php-extensions && sync
RUN install-php-extensions imagick
RUN docker-php-ext-configure opcache --enable-opcache && docker-php-ext-install opcache

RUN docker-php-ext-install -j$(nproc) bcmath calendar exif gettext sockets dba pcntl shmop sysvmsg sysvsem sysvshm
RUN docker-php-ext-install -j$(nproc) mysqli pdo

# 安装系统依赖
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    libssl-dev \
    zip \
    unzip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install zip pdo_mysql

# 安装 MongoDB 扩展
RUN pecl install mongodb-1.13.0 \
    && docker-php-ext-enable mongodb

# 清理缓存以减小镜像大小
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# 安装 composer
WORKDIR /tmp
RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer
RUN composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/


# 容器启动时执行指令
CMD ["php-fpm"]
