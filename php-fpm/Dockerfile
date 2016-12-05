FROM alpine:edge

RUN apk --update add \
        php7 \
        php7-dom \
        php7-ctype \
        php7-curl \
        php7-fpm \
        php7-gd \
        php7-intl \
        php7-json \
        php7-mbstring \
        php7-mcrypt \
        php7-mysqlnd \
        php7-opcache \
        php7-pdo \
        php7-pdo_mysql \
        php7-posix \
        php7-session \
        php7-xml \
        php7-iconv \
        php7-phar \
        php7-openssl \
    && rm -rf /var/cache/apk/*

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/*

ADD symfony.ini /etc/php7/fpm/conf.d/
ADD symfony.ini /etc/php7/cli/conf.d/

ADD symfony.pool.conf /etc/php7/php-fpm.d/

RUN ln -s /usr/bin/php7 /usr/bin/php

EXPOSE 9001

CMD ["php-fpm7", "-F"]
